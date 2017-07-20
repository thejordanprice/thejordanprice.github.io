---
layout: post
title: Raspberry Pi EEPROM flashing.
header-img: "images/posts/2017-7-16/IMG_20170716_125745.jpg"
---

Recovering or playing around with EEPROMBIOS is pretty fun and handy. An EEPROM is [E]lectrically [E]rasable and [P]rogrammable [R]ead [O]nly [M]emory. A BIOS is the software stored inside the EEPROM that handles the entire boot process of any computer or fancy device. The BIOS software on the chip is important because it is the first software to take control of your computer when you turn it on. The software has been specifically programmed for the hardware available in the device. It is responsible for initializing all of the sub-devices and finding the bootloader upon all successful (POST) tests.

Reasons to flash  do this.

- Flashing open source BIOS. (coreboot, libreboot)
- Failed flashing attempts. (bricked motherboard)
- Soft-modding old school xbox.
- Curiosity.

## Requirements

- Raspberry Pi
- 10k Resistor
- BIOSEEPROM
- Wire
- Breadboard

## Prep the Pi

The Pi, or raspbian, comes with SPI (Serial via GPIO) disabled. Luckily they have made it extremely easy to enable SPI.

    sudo nano bootconfig.txt

Uncomment the following line.

    #dtparam=spi=on

Reboot and you should be able to see the driver loaded and the device devspidev0.0 is available.

## GPIO Pinout

You will need to grab the jumper wires and get the following 6 pins hooked up.

    25 -- GND
    24 -- CS
    23 -- CLK
    21 -- DO
    19 -- DI
    17 -- 3.3v (HOLD, WP)

## BIOSEEPROM Pinout

In my case it was the Winbond 25q64fv, which seems to be a very common chip in decent motherboards.
Of course, this could vary and you should always check your spec sheets for the chip in question.

    1 -- CS
    2 -- DO
    3 -- WP
    4 -- GND
    5 -- DI
    6 -- CLK
    7 -- HOLD
    8 -- +3.3v

Again, this is for the Winbond 25q64fv, look at your spec sheet to confirm or change.

       ______
    1   --   8
    2        7
    3        6
    4 ______ 5


## Finally

You can now run the following to look at a chip.

    flashrom -p devspidev0.0 -r filename.bin

Writing to the flash is just as simple.

    flashrom -p devspidev0.0 -w filename.bin

## Examining the dump

I don't know why you would want to do this besides just looking, not much plaintext is on this level. If you would like to view it with a hex editor via the terminal you can do something like the following.

    xxd filename.bin  hex-plaintext.txt

## Final notes

Following this and examining the spec sheet for the chip in question I feel that about anyone should be able to write an EEPROM.

Have fun, don't break your stuff...

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/posts/2017-7-16' %}
{::nomarkdown}
<img class='lightbox' src="{{ site.baseurl }}{{ image.path }}" onclick="lightbox(this)">
{:/}
    {% endif %}
{% endfor %}

{::nomarkdown}
<script src="/js/lightbox.js"></script>
{:/}