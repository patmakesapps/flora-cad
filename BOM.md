# FLORA bill of materials

Everything to buy for one FLORA flat console. Part numbers are the exact boards the enclosure
was modelled around (see the parts tables in `README.md`). Screws and inserts per printed
part are in `HARDWARE.md`.

## Electronics

| Qty | Part | Notes |
|---|---|---|
| 1 | Raspberry Pi 5 | Four M2.5 bosses in the base |
| 1 | Raspberry Pi 5 USB-C power supply | Through the rear wall opening, sized for the plug overmold |
| 1 | microSD card | Raspberry Pi OS |
| 1 | Waveshare WM8960 Audio HAT | Seated on the Pi; built-in microphones |
| 2 | Waveshare 8 ohm 5 W speaker | Flat in the wings, drivers up; glue or zip tie |
| 1 | Adafruit 1643 NeoPixel Ring, 12 LEDs | Under the halo lens |
| 1 | Adafruit 4026 STEMMA soil sensor | Capacitive probe, I2C 0x36 |
| 1 | Adafruit 4162 VEML7700 lux sensor | Behind the lux window, I2C 0x10 |
| 1 | Adafruit 5776 SHT41 temperature and humidity sensor | Base floor, front left, I2C 0x44 |
| 1 | Adafruit 5625 STEMMA QT 5-port hub | Under the spine top, at the rear |

## Cables

| Qty | Part | Connects |
|---|---|---|
| 1 | Adafruit 4397 STEMMA QT to female sockets | Pi I2C header pins to the hub |
| 1 | Adafruit 4424 JST PH to STEMMA QT | Soil sensor to the hub (out through the rear notch) |
| 2 | Adafruit 4401 STEMMA QT cable, 200 mm | Lux sensor and SHT41 to the hub |
| 3 | Female jumper wires | NeoPixel ring: 5 V (pin 4), GND (pin 6), DIN (GPIO12, pin 32) |

## Hardware

| Qty | Part |
|---|---|
| 9 | Heat-set insert, M2, 3.2 mm wide, 4 mm long |
| 4 | Heat-set insert, M2.5, 3.5 mm wide, 4 mm long |
| 4 | Heat-set insert, M3, 5 mm wide, 4 mm long |
| 9 | Screw, M2 x 5 |
| 4 | Screw, M2.5 x 5 or 6 (standard Pi screw) |
| 2 | Screw, M3 x 30 button head |
| 2 | Screw, M3 x 6 button head |
| 4 | Stick-on bumper foot, 12.7 mm wide, 3.5 mm tall (Bumper Specialties BS01) |

## Filament

| Colour | Parts |
|---|---|
| White | Base, deck, spine, halo retainer |
| Purple | Collar, logo inlay, FLORA and LUMALIEN lettering |
| Clear (or white) | Halo lens |
| Clear | Lux window |

## Also needed

- An OpenAI API key for voice (see the [FLORA](https://github.com/patmakesapps/FLORA) README).
- Glue for the inlays, the lux window and the speakers.
