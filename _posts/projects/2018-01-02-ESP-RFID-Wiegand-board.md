---
layout: post
title:  "ESP RFID Wiegand board V1"
date:   2018-01-01 05:40:41 +0100
categories: projects
tags: ESP8266 ESP12 Arduino relay RFID Wiegand PCB
thumbnail: /assets/posts/projects/esp-rfid-wiegand-board-v1/esp-esp12-esp8266-rfid-wiegand.jpg
excerpt_separator: <!--more-->
---

Although it wasn't planned to server this purpose, somewhere in the middle of design i realized that this board with few more resistors would be perfect for very popular Wiegand RFID readers that you can get all around Ebay and other Chinese stores.
Those readers are often completely dummy bricks which can only read code from a chip and pass it by [wiegand](https://www.robotshop.com/media/files/pdf/wiegand-protocol-format-pr25.pdf) on two data lines.

Basically it's a ESP12 breakout board which can accept 12V input and at the same time powers up the Wiegand reader with same 12V input and accepts all possible pins from the most common readers.

You can get eagle cad schematics and BOM at github and also you can buy this board at [My Tindie Store](https://www.tindie.com/products/nardev/esp-rfid-board-for-wiegand-readers-at-5v-to-12v/)

In addition to that, it often has buzzer, LED and sometimes keypad, which also just sends the numbers it gets. One of versions i got also have simple bell button which just makes a connection on two wires. So it's simple tactile switch there.

I implemented the support for all of those input/output lines so all you need is to program your board and read cards.
I have one version of firmware which i would not be able to share at this point but i can gladly suggest eps-rfid project, which is open-source and great for the first hand to use.

[![](/assets/posts/projects/esp-rfid-wiegand-board-v1/esp-rfid-wiegand-board.png)](/assets/posts/projects/esp-rfid-wiegand-board-v1/esp-rfid-wiegand-board.png){:data-lightbox="Wiegand RFID Reader"}

In this setup, you can make your Wiegand reader as simple work hours registration device. However, next version with relay and few more features are on it's way so, please be patient.

Also, there is a version of wiegand reader which has enough space to place this tiny board in it.
[![](/assets/posts/projects/esp-rfid-wiegand-board-v1/wiegand-rfid.jpg)](/assets/posts/projects/esp-rfid-wiegand-board-v1/wiegand-rfid.jpg){:data-lightbox="Wiegand RFID Reader"}
