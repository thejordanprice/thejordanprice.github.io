---
layout: post
title: Raspberry Pi EEPROM flashing.
comments: false
---

Recovering or even playing around with BIOS is pretty fun and handy. :D

## Requirements

- [ ] Raspberry Pi
- [ ] 10k Resistor
- [ ] BIOS/EEPROM
- [ ] Wire
- [ ] Breadboard

## Prep the Pi

You need to enable SPI before anything.

    sudo nano /boot/config.txt

Uncomment the following line.

    #dtparam=spi=on

Reboot and you should be able to see the driver loaded and the device /dev/spidev0.0 is available.

## GPIO Pinout

    25 <--> GND
    24 <--> /CS
    23 <--> CLK
    21 <--> DO
    19 <--> DI
    17 <--> 3.3v (/HOLD, /WP)

## BIOS/EEPROM Pinout

In my case it was the Winbond 25q64fv, which seems to be a very common chip in decent motherboards.
Of course, this could vary and you should always check your spec sheets for the chip in question.
It seems that most people put a 10k resistor on pin 1 of the EEPROM, I'm not 100% why; the spec sheet did not specify anything of the sort when I was researching.

    1 <--> /CS
    2 <--> DO
    3 <--> /WP
    4 <--> GND
    5 <--> DI
    6 <--> CLK
    7 <--> /HOLD
    8 <--> +3.3v

Again, this is for the Winbond 25q64fv, look at your spec sheet to confirm or change.
       ______
    1 |  --  | 8
    2 |      | 7
    3 |      | 6
    4 |______| 5


## Finally

You can now run the following to look at a chip.

    flashrom -p /dev/spidev0.0 -r filename.bin

Writing to the flash is just as simple.

    flashrom -p /dev/spidev0.0 -w filename.bin

## Examining the dump.

I don't know why you would want to do this besides just looking, not much plaintext is on this level. But if you would like to view it with a hex editor via the terminal you can do something like the following.

    xxd filename.bin >> hex-plaintext.txt

Have fun, don't break your stuff...

## Album

{% for image in site.static_files %}
    {% if image.path contains 'images/post/2017-7-16' %}
{::nomarkdown}
<center>
    <div class="gallery">
    <a target="_blank" href="{{ site.baseurl }}{{ image.path }}">
        <img src="{{ site.baseurl }}{{ image.path }}" width="300" height="200">
    </a>
    </div>
</center>
{:/}
    {% endif %}
{% endfor %}