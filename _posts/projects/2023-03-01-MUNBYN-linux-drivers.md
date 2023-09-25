---
layout: post
title:  "MUNBYN WiFi With Linux"
date:   2023-03-01 15:31:00 -0400
categories: projects
tags: label printer linux munbyn
thumbnail: /assets/posts/projects/munbyn-linux-drivers/munbyn-wifi-printer.png
excerpt_separator: <!--more-->
---

Other than being affordable, this little printer has served me quite well, especially with Linux. However, the support isn't available out of the box. The drivers which you can find on "manufacturer's" web simply do not work. The PPD supplied simply doesn't seem to work well, and I didn't put any effort into trying to debug it.

Fortunately, I figured out that this is yet another company that is simply using existing hardware with their own enclosure and intense marketing. So, I bet there must be another printer with a PPD available online that would work. And I was right.

Mainly because I spent quite some time trying to get it to work, I'm sharing that find. Also, keep in mind that I had the printer already set up with Windows, as that's the only way for Wi-Fi to be set for this printer right now. Well, I don't know if another way exists, but this is good enough.

So, the printer which has the same firmware/hardware is BY-426 by [https://www.beeprt.com](https://www.beeprt.com)

You can get the PPD that works for me here [Beeprt.ppd](/assets/posts/projects/munbyn-linux-drivers/Beeprt.ppd)