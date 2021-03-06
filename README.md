# Luchtlichtje

Source code and hardware spec of the ESP8266 driven Air Quality Indicator "Luchtlichtje" (Dutch for 'air light')

A small ESP/Arduino Project, showing lights indicating the air quality, based on data from luftdaten.info

![Pic](https://raw.githubusercontent.com/pietervdvn/Luchtlichtje/master/2018-06-09%2017.20.08.jpg)
![Moving Pic](https://raw.githubusercontent.com/pietervdvn/Luchtlichtje/master/2018-06-16%2023.11.13.gif)

## API

Get your sensor data at http://api.luftdaten.info/v1/sensor/7245/

## Bill of Materials

- A Luchtlichtje PCB
- 4 LEDS of each colour (RED, YELLOW, GREEN) of 5mm (or some other colours)
- 3 resistors of around 10ohm (use higher such as 220ohm for less brightness)
- 1 photoresistor of a pretty high resistance, in combination with a 1Mohm resistor*

*If you don't like the brightness settings or have a different photoresistor, you can change the code to have other settings*

## Flashing a Luchtlichtje


- Install platformio
- Open the console
- cd to the desired directory (v0.2/firmware)
- `sudo platformio run --target upload`
- Use `platformio run --target monitor` to see what is happening




## Assembly instructions

- Start with placing the resistors. The resistor 'R1 Different'-resistor (bottom right) takes the 1-mega-ohm resistor
- The other three have 10-ohm resistors (upper and left side).
- Next, place the leds. Be carefull, they have to be oriented correctly: the flattened sides go in the middle. Green leds down, red leds up - just like traffic lights. Solder them neatly and straight.
- Place and solder the header pins on the backside of the board.
- Flash the software on the nodemcu and place it on the backside (see above).
- Gently break the board along the cutlines on the right. If they don't come off, use a knife on the back side of the board.
- These small rectangular break-off pieces can be slided in the main board, to place it on your desk.
- The break-off parts easily fall of the board when lifted. To prevent this, place a piece of wire through the holes in the break-off part and the main board.
- All done! Enjoy your Luchtlichtje.


## Troubleshooting

When booting, the board will test all leds blinking from up to down.
If a led does not blink, check the soldering.
If more then the desired leds burn, some LEDS are soldered in the wrong direction.

If the orange leds start blinking one after another; the board is connecting to the wifi. This will always happen for a few seconds when booting.

If the reds leds are blinking, either luftdaten or your sensor is down. 

## Versions

The first version (v1.0) is dated 2018-05-15
The second version (v2.0) is dated 2018-08-24. Changes are: removal of unused transistors, addition of a brightness sensor, fancier placement of resistors.
