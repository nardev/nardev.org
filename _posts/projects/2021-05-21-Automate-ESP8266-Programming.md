---
layout: post
title:  "Automate ESP8266 Programming"
date:   2021-05-21 07:40:41 +0100
categories: projects
tags: ESP8166 ESP12F ESP-12F ESP32 ESP-12E
thumbnail: /assets/posts/projects/automate-esp8266-programming/automate-esp8266-programming.jpg
excerpt_separator: <!--more-->
---

From time to time i need to program several hundred ESP-12F modules for my projects. First time i did it, i was changing the module on the programmer and then repeating the command.

However, by doing that it was hard to do programming at several programmers at once and also it required all my attention when the script finished etc.

So i had to automate it a bit, but i didn't want to throw myself into codding so much. Just the most simple way to do it was an option.

So here we are. The whole solution is just a simple udev rule which sets the programming script to execute. As i said "it sets the script". Because, udev just triggers and doesn't handle the runtime environment as when you run a program in terminal. So for that purpose, i used "at now".

<!--more-->

### Pre-required:
 - esptool.py (https://github.com/espressif/esptool/blob/master/esptool.py)
 - Install "at" with (apt-get install at)
 - Get your firmware.bin and if you need spiffs.bin files
 - UART programmer, I used this one [Frogboard Frogo ESP-12F](https://www.tindie.com/products/fred_iot/esp8266-frogboard-frogo-pins-esp-12e-dev-board/)

   ** Be careful about the programmer, another one that i was using had very poor construction, i had to hold module by hand and also the button on it was just turning on/off the ESP-12F module not the programmer so i had to plug/unplug the programmer in order to trigger the udev rule. Maybe it was possible to load/unload the module differently but i would make some other problems. **


### Step 1:  
   
  Set udev rule:

  Make file "/etc/udev/rules.d/esptool.rules"

  Paste following into the file and change accordingly the path for the script and also check the vendor number for your programmer. You can probably find out more once you plug your device and monitor it like this "udevadm monitor --kernel --property --subsystem-match=usb"

{% highlight bash %}
 # esptool auto programmer
 ACTION=="add", KERNEL=="ttyUSB[0-1]", SUBSYSTEM=="tty", ATTRS{vendor}=="0x8086", RUN+="/opt/auto-esptool-run.sh /dev/%k %n | at now"
{% endhighlight %}

### Step 2:  
  
  Copy/Paste/Edit the following script with appropriate data and also set it executable by the same user as the one who has esptool.py set in it's environment.

{% highlight bash %}
 #!/bin/bash  
 exit 0 # comment if you want to use the auto procedure  
 ESPTOOL_PATH=""  
 FIRMWARE_PATH=""  
 SPIFFS_PATH=""  
 # If you want to get sound notification once the script exits or finish programming.  
 OUTPUT_TERMINAL="/dev/pts/0"  
 # the user under which the python and esptool is set  
 BASH_USER=""  
 USB_DEVICE=$1  
 # As i was using multiple programmers, i separated the log into different files.  
 # However, it's just distinguished per the device number at the moment.  
 # The programmer will usually be registered at the first available number.  
 #ESPTOOL_LOG="/tmp/auto-esptool.log"  
 ESPTOOL_LOG="/tmp/auto-esptool-$2.log"  
 su - [your-user-name] -c 'echo -e "\n----------------------------------------\nPORT: 	$USB_DEVICE\n----------------------------------------\n >> $ESPTOOL_LOG"'  
 su - $BASH_USER -c "$ESPTOOL_PATH --baud 1500000 --port $USB_DEVICE write_flash 0x00000000 $FIRMWARE_PATH 0x00200000 $SPIFFS_PATH >> $ESPTOOL_LOG"  
 echo -ne '\007' > $OUTPUT_TERMINAL  
{% endhighlight %}


Feel free to adjust the script according to your needs. There is nothing complex, just simple calling the esptool.py with parameters and passing the output to a log file.

Change [your-user-name] part of the script to your user. The reason was that esptool and the enviromnet was available only for that particular user. I believe it's gonna be the case with you. The script is initiated by the system so unless you have the env set for root, you would not be able to run the esptool.

The execution is set under the same user so that there is no permission problem when the log is printed.

After you finish, you can grep your logs, catch all MAC addresses in order to track the devices. It would be nice to add some timestamp, maybe even to use esptool.py to burn in your serial into the chip at the same time.

That's about all.


