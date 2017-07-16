---
layout: post
title: Raspberry Pi EEPROM flashing.
comments: false
---

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

## GPIO

    25 <--> GND
    24 <--> /CS
    23 <--> CLK
    21 <--> DO
    19 <--> DI
    17 <--> 3.3v (/HOLD, /WP)

## BIOS/EEPROM Pinout

In my case it was the Winbond 25q64fv, which seems to be a very common chip in decent motherboards.
Of course, this could vary and you should always check your spec sheets for the chip in question.

    1 <--> /CS
    2 <--> DO
    3 <--> /WP
    4 <--> GND
    5 <--> DI
    6 <--> CLK
    7 <--> /HOLD
    8 <--> +3.3v

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