# Cricket-ESP32-Micropython
Experiments with Adafruit Cricket and ESP32 Feather with Micropython

# Setup your environment
Install Python - recommend custom install, install for everyone checkbox, add/expand path

Download [micropython firmware for ESP32](https://micropython.org/download/#esp32)  

On Windows: from CMD window with Administrator privs, upgrade PIP, install esptool, clear flash, write the micropython image:

`python -m pip install --upgrade pip`

`pip install esptool`

`esptool.py --chip esp32 erase_flash`

`esptool.py --chip esp32 --port com6 write_flash -z 0x1000 esp32-20180627-v1.9.4-204-gb9ec6037.bin`

Once this is done use a terminal like PuTTY with 115200 serial connection and you should see the REPL prompt

`>>> print("Hello MicroPython on Cricket/ESP32")`
`Hello MicroPython on Cricket/ESP32`

Now that you've confirmed it is operating get familiar with the hardware.  First you can reset with either the Feather's reset button or the Cricket reset button.

Now you can either type code into the REPL terminal, or you can use an IDE like 


OK, after trying to hand build ESP32 support for Crickit by hand crafting the files, I've backed off to getting ESP8266 to work first (which is supported via CircuitPython - a fork of MicroPython.  After downloading the proper .bin file:

C:\> esptool.py --port COM3 --baud 115200 erase_flash
esptool.py v2.4.1
Serial port COM3
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
MAC: 18:fe:34:d4:0a:73
Uploading stub...
Running stub...
Stub running...
Erasing flash (this may take a while)...
Chip erase completed successfully in 11.4s
Hard resetting via RTS pin...

C:\esptool.py --port COM3 --baud 460800 write_flash --flash_size=detect 0 adafruit-circuitpython-feather_huzzah-2.3.1.bin
esptool.py v2.4.1
Serial port COM3
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
MAC: 18:fe:34:d4:0a:73
Uploading stub...
Running stub...
Stub running...
Changing baud rate to 460800
Changed.
Configuring flash size...
Auto-detected Flash size: 4MB
Flash params set to 0x0040
Compressed 599708 bytes to 390468...
Wrote 599708 bytes (390468 compressed) at 0x00000000 in 10.5 seconds (effective 456.6 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...

C:\

Then reset the board and you should see:

Press any key to enter the REPL. Use CTRL-D to soft reset.

Adafruit CircuitPython 2.3.1 on 2018-05-07; ESP module with ESP8266
>>>
>>> print("Hello World!")
Hello World!
>>>
