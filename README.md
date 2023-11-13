# ESPHome-Froeling-Lambdatronic_3200

![wiring diagram](docs/ha_dashboard_01.png)

### ESHome RS232 to TTL - ESP8266 - Read data from Froeling / Lambdatronic 3200

I'm testing this with my Fröling SP Dual. But I assume it should also work for other models that have the Lambdatronic 3200 control unit. Feedback appreciated.

#### Parts:
Wemos D1 Mini ESP8266:
https://www.amazon.de/dp/product/B0CB85Q78G

MAX3232 DB9 RS232 TTL converter:
https://www.amazon.de/gp/product/B0BNQ41QKQ

![wiring diagram](docs/wemos-rs3232-ttl.png)

|  Wemos | D7  | D8  | 5V  | G  |
|---|---|---|---|---|
| MAX3232  | RX  |  TX |  VCC | GND  |

Connect a RS232 (DB9) cable between "MAX3232 DB9 RS232 TTL converter" and you boiler's mainboard (COM2).

#### Boiler Settings:
- Click on the user icon
- Enter code "-7"
- Boiler > Modbus Protokoll RTU(1)
- Boiler > use Modbus Protokoll 2014



#### Home Assistant Dashboard
##### prerequisites:
- https://experiencelovelace.github.io/ha-floorplan/
- copy all files from /ha_dashboard/* to your Home assistant instance /config/www/froeling/*
- create a card in your dashboard and add the content of "ha_dashboard.yaml"
<span style="color:red">!! Currently, only one Panel is provided!!</span> I'm working on the rest. An update will follow.