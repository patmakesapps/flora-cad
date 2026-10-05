# FLORA v1 — first enclosure concept

Design session 2026-10-04. A first idea to react to, not a release. Modelled in
`Blender/FLORA_v1.blend` (1 unit = 1 mm), collection **FLORA ASSEMBLY**, built at the origin.
Print parts are in `FLORA PRINT PARTS`; linked copies of the electronics are in
`FLORA PLACED PARTS`. The Lumalien L mark is parked beside it in `LOGOS`, not yet used.

**Nothing has been exported.** No STL or STEP files exist yet.

## Concept

An upright white pod, 108 x 76 mm footprint, 128 mm tall, plan corners R16. A purple collar
band separates the body from a white cap. The NeoPixel ring sits in the cap as an
upward-facing halo under a lens, with the lux sensor's window beside it. The front carries a
leaf-shaped grille of vertical slits: it lets air reach the temperature sensor and sound
reach the microphones. Each side has two rows of slits over a speaker.

Axes: X = width (right = +X), Y = depth (front = -Y), Z up, base on z = 0.

## Layout (pod coordinates, mm)

| Item | Position | Notes |
|---|---|---|
| Sled | plate x -28.9..-26.5, full depth, z 2.4..110 | slides down into channels on the front and rear walls; carries the Pi, hub and SHT41 |
| Pi 5 + audio HAT | board in the YZ plane, underside at x -22.5; SD edge at z 26, USB/Ethernet end at z 111..114; HDMI/USB-C edge 0.5 behind the rear wall | parts face +X. 4 mm bosses, M2.5 inserts |
| USB-C power | rear wall opening 8.6 x 14.6 at x -19.3, z 37.2 | sized for the plug overmold, since the sled drops in vertically |
| SHT41 | on the sled under the Pi, y -30..-4.6, z 4.4..22.2 | lowest and furthest forward, in the incoming air |
| QT hub | on the sled under the Pi, y 3.5..28.9, z 4.4..22.2 | connectors point +X |
| Soil cable | rear wall slot 8.5 x 4.2 at x -8, z 13 | thread the small SH plug through from outside |
| Speakers | against each side wall, body z 9.9..109.9, y +/-22.5 | driver toward the wall; rest on 7.5 mm ledges. Left one is backed by the sled, right one by two lips |
| NeoPixel ring | cap, centre (0, 0), LEDs up, 3 mm below the lens flange | lens + retainer on 3 x M2 |
| VEML7700 | cap, sensor under a window at (33, 0), board top 3.6 below the ceiling | 2 x M2 inserts + 2 pins |
| Cap fixing | lip plugs 4.5 mm into the body; 2 x M3 through the rear wall at x +/-35.5, z 112.75 | no screws visible from the front or top |
| Vents | leaf grille front z 13..97, stem to z 5; rear intake z 6..20; rear exhaust z 88..106 | |

## Print parts (7 + test coupon)

| Part | Size | Colour | Orientation |
|---|---|---|---|
| FLORA_BODY | 108 x 76 x 115 | white | upright, open top |
| FLORA_COLLAR | 108 x 76 x 4 | purple | flat |
| FLORA_CAP | 108 x 76 x 20 (9 + lip and pillars) | white | upside down, top face on the bed |
| FLORA_SLED | 70.6 x 107.6 x 7.8 | white | flat, bosses up |
| FLORA_HALO_LENS | dia 45.6 x 3.2, 1 mm front skin | clear, or white | front face down |
| FLORA_HALO_RETAINER | dia 46 (53.8 over ears) x 8.1 | white | floor down |
| FLORA_LUX_WINDOW | dia 13.7 x 3.4 | clear | small end down |
| insert test coupon | 30 x 12 x 7 | any | not in the Blender file; holes 2.9 / 3.2 / 4.6 |

Walls, floor and ceiling 2.4 mm. All parts fit the Bambu A1 with room to spare. The cap's top
edge is a 6 mm 45 degree chamfer, not a round, so it prints top-down without supports.

## Hardware

- Heat-set inserts: 9 x M2 (OD 3.2), 4 x M2.5 (OD 3.5), 2 x M3 (OD 5.0). Hole sizes are
  modelled at 2.9 / 3.2 / 4.6 mm, 5 mm deep.
- Screws: 9 x M2x5, 4 x M2.5x6, 2 x M3x8.
- 4 x 10 mm stick-on feet (recessed).
- Speakers: glue, or a zip tie through an ear.

## Assembly order

1. Set the inserts: 8 in the sled, 7 in the cap.
2. Speakers down into their pockets.
3. On the sled: SHT41, hub, then the Pi with the HAT. Plug in the speaker lead, the hub
   cables and the ring jumpers.
4. Thread the soil cable through the rear slot and into the hub.
5. In the cap: lens, ring, retainer; lux window, lux board.
6. Lower the sled with the cap still tethered to it by its cables.
7. Collar on the rim, cap on, two screws at the back.

## Checked

- Sampled every placed electronics part against every print part: no part sits inside
  plastic.
- No two print parts overlap.

## Not checked, or guessed

- Cables and plugs are not modelled. Room for the socket cable on the HAT header, the
  speaker plug and the USB-C plug was worked out by hand.
- Insert hole sizes are untested against the actual insert kit.
- The microphones face sideways toward a speaker, not forward. The leaf grille is their
  path to the room; pickup needs a real test.
- The SHT41 will still read warm: it shares the enclosure with the Pi.
- No fan, and the audio HAT covers the CPU.
- The front of the cap is held only by the lip fit.
- SD card: cap off, lift the sled.
- Speaker and cable models are partly estimated, see `README.md`.
- The soil sensor's default I2C address is 0x36, the same address the Flora software reads
  for the X1200 battery gauge.

## Open questions for review

- Ring on top (as built) or on the front as an eye.
- Where the L logo goes.
- Halo centred with the lux window off to one side: acceptable, or re-arrange.
