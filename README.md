# LaskaKit MyMeatMeter Customized

Hardware from DIY kit [LaskaKit MyMeatMeter](https://www.laskakit.cz/laskakit-mymeatmeater--stavebnice-teplomeru-do-grilu-s-wifi/?variantId=17126), variant with BW e-ink display ([GDEY029T94](https://www.laskakit.cz/good-display-gdey029t94-2-9--296x128-epaper-displej-grayscale/) 2.9" 296x128).

## Modifications

- Added custom image on the website header (Base64 encoded string in `page.h` file)
- Added last measurement time info to the website to verify that the measurements are up to date.

## Hardware Setup

1. Solder terminal to `MAX31856` board for smoker temperature probe.
2. Solder one header pin at 90 angle up to `CS3`, see image below.
3. Solder `JP2` and `JP5` pads on `MAX31865` board to enable reading using 2-wire PT1000 probe.
4. At the time of writing, there is an error in manufaturing of the `MAX31865` board (see [here](https://www.laskakit.cz/laskakit-max31865-prevodnik-pro-termoclanek-pt100-1000/)), so no further pad soldering is not required.
5. Connect boards using μŠup connectors.

## Software setup

1. Download Arduino IDE.
2. Set board type to `ESP32 Dev Module`.
3. Set `Tools` -> `Upload Speed` to `115200` baud.
4. Open arduino project and change lines with WiFi SSID and password to your router. 💡TIP: You can use your phone hotspot instead, allowing for remote use anywhere.
5. Make sure the switch on the main board is set in ON position.
6. Upload code (this takes a long time, to see the progress, enable `Show verbose output during` ☑️compile and ☑️upload in the Arduino IDE Preferences.)
7. Serial monitor shows if the board is sucessfully connected to your WiFi and displays the temperature readings.
8. Visit [smokehouse.local](smokehouse.local) in your browser on a device that is connected to the same network.
