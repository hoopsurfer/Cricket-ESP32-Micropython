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
