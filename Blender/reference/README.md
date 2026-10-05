# FLORA reference material

## Bench photos — 2026-10-04

Photos of the working bench setup, in `bench_photos/`. Renamed from the original
`ChatGPT Image Oct 4, 2026, 08_xx_xx PM.jpg` downloads.

| File | View |
|---|---|
| `2026-10-04_bench_01_overview_front_high.jpg` | Three-quarter view from the front, above. Whole setup. |
| `2026-10-04_bench_02_front_usbc_hdmi_edge.jpg` | Straight on at the USB-C / HDMI edge, power cable plugged in. |
| `2026-10-04_bench_03_top_down.jpg` | Top down. Best view of the footprint and wire runs. |
| `2026-10-04_bench_04_usb_ethernet_end_low.jpg` | Low angle from the USB / Ethernet end. Shows stack height against the speakers. |
| `2026-10-04_bench_05_sd_card_end_speaker_wiring.jpg` | From the SD-card end. X1200 visible under the Pi; speaker leads into the HAT. |
| `2026-10-04_bench_06_pi_stack_only_no_speakers.jpg` | Pi stack on its own, speakers removed. |
| `2026-10-04_bench_07_front_ring_lit_purple.jpg` | Front view with the ring lit (idle purple). |

### Read these photos with one caveat (Pat, 2026-10-04)

**The Geekworm X1200 UPS HAT under the Pi 5 will not be in the real build.** It is only on the
bench. It does put the Pi 5 at a height where the USB-C is above the speakers, which is worth
keeping in mind. Actual placement of everything is still to be decided.

### What else the photos show (observations, not decisions)

- Speakers lie flat, drivers up, one along each long edge of the Pi (the USB-C / HDMI edge and
  the GPIO edge). The stack sits between them, overlapping their inner edges.
- The white power cable in photos 02 and 07 goes into the USB-C port on the X1200 (centre of
  that edge, below the Pi), not the Pi's own USB-C, which is the empty port to its left. With
  the X1200 gone, power has to reach the Pi's own port.
- The speaker model is 22 mm tall lying flat, so a plug in the Pi's USB-C clears a speaker in
  front of it only if the port sits above that height, or the speaker moves.
- NeoPixel ring hangs on three jumper wires from the HAT's pass-through header: 5 V on pin 4,
  ground on pin 6, DIN on GPIO12 / pin 32 (per the Flora README).
- Speaker leads plug into the HAT's white 4-pin JST at the SD-card end.

## Vendor CAD — `vendor_cad/`

Source files for the sensor models in `FLORA_v1.blend`. Reference only.

| Folder | What | Licence |
|---|---|---|
| `adafruit_4026/` | STEMMA Soil Sensor STEP + CAD render | MIT, `LICENSE-Adafruit_CAD_Parts.txt` |
| `adafruit_5625/` | STEMMA QT 5-Port Hub STEP + CAD render | MIT, same file |
| `adafruit_4885/` | SHT40 STEP + CAD render (SHT40 / SHT41 / SHT45 share the PCB) | MIT, same file |
| `adafruit_4162/` | VEML7700 STEMMA QT Eagle board file (no 3D model exists) | CC BY-SA 3.0, `adafruit_4162/license.txt`. Designed by Kattni Rembor for Adafruit Industries. |

STEP and board files come from <https://github.com/adafruit/Adafruit_CAD_Parts> and
<https://github.com/adafruit/Adafruit-VEML7700-PCB>.
