# ESPHome-Froeling-Lambdatronic_3200
### ESHome RS232 to TTL - ESP8266 - Read data from Froeling / Lambdatronic 3200

I'm testing this with my Fröling SP Dual. But I assume it should also work for other models which have the Lambdatronic 3200 control unit. Feedback appreciated.

#### Parts:
Wemos D1 Mini ESP8266:
https://www.amazon.de/dp/product/B0CB85Q78G

MAX3232 DB9 RS232 TTL converter:
https://www.amazon.de/gp/product/B0BNQ41QKQ

![wiring diagram](wemos-rs3232-ttl.png)

|  Wemos | D7  | D8  | 5V  | G  |
|---|---|---|---|---|
| MAX3232  | RX  |  TX |  VCC | GND  |

Connect a RS232 (DB9) cable between "MAX3232 DB9 RS232 TTL converter" and you boilers mainboard (COM2).

#### Boiler Settings:
- Click on the user icon
- Enter code "-7"
- Boiler > Modbus Protokoll RTU(1)
- Boiler > use Modbus Protokoll 2014
