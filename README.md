# ESPHome-Froeling-Lambdatronic_3200

![Dashboard - Kessel](docs/ha_dashboard_kessel.png)
![Dashboard - Heizkörper](docs/ha_dashboard_heizkoerper.png)
![Dashboard - Boiler 01](docs/ha_dashboard_boiler01.png)
![Dashboard - Puffer 01](docs/ha_dashboard_puffer01.png)
![Dashboard - Austragung](docs/ha_dashboard_austragung.png)
![Dashboard - Zirkulationspumpe](docs/ha_dashboard_zirk-pumpe.png)

## ESHome RS232 to TTL - ESP32 - Read data from Froeling / Lambdatronic 3200

I'm testing this with my Fröling SP Dual. But I assume it should also work for other models that have the Lambdatronic 3200 control unit. Feedback appreciated.

### Parts
  
Wemos D1 Mini ESP32:
<https://www.amazon.de/dp/product/B08BTRQNB3>

MAX3232 DB9 RS232 TTL converter:
<https://www.amazon.de/gp/product/B0BNQ41QKQ>

![wiring diagram](docs/wemos-rs3232-ttl.png)
  
|  Wemos | TX  | RX  | 5V  | G  |
|---|---|---|---|---|
| MAX3232  | RX  |  TX |  VCC | GND  |

Connect a RS232 (DB9) cable between "MAX3232 DB9 RS232 TTL converter" and you boiler's mainboard (COM2).

### Boiler Settings

- Click on the user icon
- Enter code "-7"
- Boiler > Modbus Protokoll RTU(1)
- Boiler > use Modbus Protokoll 2014

### Home Assistant Dashboard

- required: <https://experiencelovelace.github.io/ha-floorplan/>
- copy all files from /ha_dashboard/*to your Home assistant instance /config/www/froeling/*
- create a new Dashboard and add the content of "ha_dashboard.yaml"
- The SVG files contains for image and text objects "ID's" which has to match the entity. Therefore I recommend not to change the device name of your ESP32.

### ESPHome

For an better overview I split the yaml file into multiple pieces and included them in the main file as a remote package.
  
Just use the example from "froeling.yaml" and flash it to your ESP32.

### Contribution
  
I'm aware that currently not all entities are available. And also some available ones are not displaying the correct values. Feel free to let me know if you've found the correct Modbus register to retrieve the correct data.
