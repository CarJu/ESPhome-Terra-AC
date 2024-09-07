# ESPhome-Terra-AC

I own an ABB Terra AC wallbox (TAC-W11-G5-R-0) and I wanded to control the outputpower to load my ev most cost efficient. 

I will save me explaining flashing ESPhome or using variables in Home assistant.

But I will give an example how I solved my problem:

My Hardware
- Wemos D1 Mini Pro (Esp8266) or any else ESP-Chip with 3,3 and 5V Power Pin
- TTL to RS485 converter with automatic flow control
- Some jumpercables and solder iron

Connecting
Ground and 3,3V you can get from jtag connector in the upper right of the wallbox.
Because the D1 Mini Board has no second Ground-Pin I needed to solder an 3-Way ground-jumper-cable (1-Wallbox, 2-ESP,3-RS485)
5V for the RS485 converter I got from D1 Mini Board.

Usage in Node-Red
I send my PV-surpus to the topic tac11/carport/max_power and the wallbox will regulate round about to that value. If you dont want to import energy from grid, may you reduce that value to be save. In fact you can only limit amperes in the wallbox and the calculation from ampere to watt not 100% accurate.  

Please notice that my code is and will be tested with my type of wallbox.
