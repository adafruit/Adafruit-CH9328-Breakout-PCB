## Adafruit CH9328 UART to HID Keyboard Breakout PCB

<a href="http://www.adafruit.com/products/5973"><img src="assets/5973.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit CH9328 UART to HID Keyboard Breakout. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/5973

### Description

We love using chips with 'native USB' peripherals - that's the magic silicon that lets a microcontroller act like an HID keyboard or mouse or disk drive or MIDI synth. It's a standard addition on SAMD21, RP2040, and even the latest ESP32-S2 and ESP32-S3 boards. But what about when you have a classic ATmega328 Uno? or an original ESP32 or ESP8266? Maybe even a single-board computer like a Raspberry Pi? We would say "sorry...that's not possible"  UNTIL NOW!

The CH9328 is a funky chip that is basically a programmed microcontroller that enumerates as an every-day HID keyboard and can convert ASCII or 8-byte raw reports, read over a standard serial port UART, into keypresses. So, you can emulate a keyboard even if your chip doesn't have native USB! You do need a hardware or software serial port: some way to generate 9600 baud 3V-logic signal that the CH9328 can read.

We added all the support circuitry to make this chip easy to use, you may not even need to do any soldering. The CH9328 is connected to a USB Type C port so it's easy to plug into any computer, laptop or even phone/tablet. Then, you can get 5V power from the 5V and Ground pads. There's a UART RX receive input plus a reset line if you want to perform a hard reset. If you want 'solderless' functionality, grab one of our JST SH cables: the red line will provide 5V, black is Ground, and the white wire is data in. 

You can configure the 'Mode' using the 4 on-board switches, do that before powering it up:

* Switch #1 is used to configure the "Upload speed" - for most cases it doesn't matter which way its set
* If Switch #2, #3 and #4 are all 'ON' the chip is in Mode 0:
Visible ASCII characters are sent as-is: if you send ASCII "A", an "A" is typed. If 0x1B is received, it is converted to the Enter key
* If Switch #2 and #4 are 'ON' and Switch #3 is 'OFF' the chip is in Mode 1:
Visible ASCII characters are sent as-is: if you send ASCII "A", an "A" is typed
* If Switch #2 and #3 are 'ON' and Switch #4 is 'OFF' the chip is in Mode 2:
Visible ASCII characters are sent as-is: if you send ASCII "A", an "A" is typed. If 0x28 is received, it is converted to the Enter key
* If Switch #3 and #4 are 'ON' and Switch #2 is 'OFF' the chip is in Mode 3:
This is the mode for sending raw 8-byte HID reports. This is also good if you want more control over the keypresses, or keyholds, or to mimic a non-US keyboard because you can control exactly what control codes are sent and when.

We recommend using mode 3 if possible, but you'll want to use our CH9328 library to do so.

This is a nice and easy way to emulate a keyboard without having to worry about native USB support, gadget mode, or maybe you just want to emulate more than one kind of device. You can also do 'funky' things like have one desktop or single-board computer 'type' into a device such as a computer or mobile device by running our Python code and having it send UART data via a USB-to-UART converter. Either way, the CH9328 will make it easy to keeb away.

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
