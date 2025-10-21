# Waveshare 7" Touch screen ESP32S3

I am not the original author, but I've removed some of the AI "mistakes"
(lots of repetition, long lambda's with more appropriate code that uses styles)
and changed the colours a bit as well as giving visual feedback when a button
is pressed.

### Board/Config History

The configuration for the device has gone through a lot of iterations and previously
relied on lots of custom `platformio_options` and a long list of `sdkconfig_options`
I got from the original AI config and the examples in the [Waveshare wiki](https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-7#Precautions)
which made this fragile and not very future proof.

### Newer Boards Config

By using a different board (previously this was the default [`esp32-s3-devkitc-1`](https://github.com/pioarduino/platform-espressif32/blob/main/boards/esp32-s3-devkitc-1.json))
it looks like [`esp32s3_120_16_8-qio_opi`](https://github.com/pioarduino/platform-espressif32/blob/main/boards/esp32s3_120_16_8-qio_opi.json)
is a better match as it's for an ESP32-S3 with 16MB QIO Flash and 8MB OPI PSRAM running at 120MHz. The `build.f_boot` which I suspect is similar to
the `CONFIG_ESPTOOLPY_FLASHFREQ_120M: y` in `sdkconfig_options` was introduced with
[Platformio: S3 QIO 120Mhz Flash speed not possible #9351](https://github.com/espressif/arduino-esp32/issues/9351) 

There's also a [`esp32-s3-devkitc1-n16r8`](https://github.com/pioarduino/platform-espressif32/blob/main/boards/esp32-s3-devkitc1-n16r8.json) board for the
Espressif ESP32-S3-DevKitC-1-N16R8V (16 MB Flash Quad, 8 MB PSRAM Octal), but this doesn't include the PSRAM running at 120MHz (I think is defaults to 80MHz).

These new boards were added in [Arduino 3.1.x based on IDF 5.3.x #74](https://github.com/pioarduino/platform-espressif32/pull/74)
and https://github.com/sivar2311/platformio_boards merged with [Commit e247f2e](https://github.com/pioarduino/platform-espressif32/commit/e247f2ed0c2df6453d9618d514841c2d75cafede).

### Where to get it

The [Waveshare ESP32 7" Touchscreen](https://www.waveshare.com/esp32-s3-touch-lcd-7.htm) is available from the usual online stores
([The PI Hut](https://thepihut.com/products/esp32-s3-development-board-with-7-capacitive-touch-display-800-x-480), [AliExpress](https://www.aliexpress.com/item/1005009051165419.html),
[Amazon](https://www.amazon.co.uk/Waveshare-ESP32-S3-Capacitive-Development-Assistant/dp/B0D2NMCY7K/261-0321974-2800367) etc).



### The following is from the origin README in the repo this is forked from

The automations for brightness/presence control I use a
[Shelly BLU Motion](https://shellystore.co.uk/product/shelly-blu-motion/),
however you can connect any precense/motion detector onto the board itself and
expose that to home assistant, or as an exercise left for the reader move the
automations onto the device itself.

This is not supported out of the box and requires soldering a wire on the back
of the device to gain that funtionality.  There is a great post here
https://community.home-assistant.io/t/esp32-s3-7inch-capacitive-touch-display-adjust-brightness/771030
that gives you instructions on doing that.

I have also included a modified background image.  Feel free to modify that anyway you wish.

Finally, thanks to Michael Okuda for the original design of the LCARS graphics.

 *"This is a fan-made project inspired by the LCARS interface design from Star Trek.
 It is not affiliated with or endorsed by Paramount Pictures or the Star Trek franchise. This project is for personal, non-commercial use only."*  
