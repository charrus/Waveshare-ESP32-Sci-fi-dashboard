# Waveshare 7" Touch screen ESP32S3

I am not the original author, but I've removed some of the AI "mistakes"
(lots of repetition, long lambda's with more appropriate code that uses styles)
and changed the colours a bit as well as giving visual feedback when a button
is pressed.

I chose the [Waveshare ESP32 7" Touchscreen](https://www.waveshare.com/esp32-s3-touch-lcd-7.htm)
due to its price and size.  My goal was to create a esphome touch panel
similar to what you see in Sci Fi series.  

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
