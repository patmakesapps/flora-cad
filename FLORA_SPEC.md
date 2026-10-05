# FLORA enclosure concepts

Two concepts, both in the one file `Blender/FLORA_v1.blend` (1 unit = 1 mm), both built at
the origin. Ideas to react to, not releases. Only one is shown at a time; the other
collection is excluded from the view layer (tick its checkbox in the outliner to see it).

| Concept | Collection | State |
|---|---|---|
| Flat console, 188 x 118 x 46 | **FLORA FLAT ASSEMBLY** | current, shown |
| Tall pod, 108 x 76 x 128 | **FLORA TALL POD ASSEMBLY** | backup, hidden |

The Lumalien L mark is parked beside them in `LOGOS`, not yet used.

**Nothing has been exported.** No STL or STEP files exist yet.

# Flat console (2026-10-05)

Print parts are in `FLORA FLAT PRINT PARTS`, linked copies of the electronics in
`FLORA FLAT PLACED PARTS`.

## Concept

The bench layout, boxed: the speakers lie flat with their drivers up, one on each side, and
the Pi sits between them. A low white tray 188 x 118 mm, 27.4 mm tall at the wings, plan
corners R6.4. Down the middle runs a raised spine, 100 mm wide and 46 mm tall, standing on a
purple collar band. The NeoPixel halo and the lux window are on top of the spine, toward
the front. Each wing has two groups of five slots over its speaker.

Axes: X = width (right = +X), Y = depth (front = -Y), Z up, base on z = 0.

## Layout (mm)

| Item | Position | Notes |
|---|---|---|
| Speakers | flat on the floor, drivers up, x +/-46.3..91.3, y +/-56, z 2.4..24.4 | dome driver toward the front, passive radiator toward the rear. Held between the floor and the deck (0.6 gap for foam), located by the walls and two floor ribs each |
| Pi 5 + audio HAT | flat on 4 mm bosses, board x -41.5..43.5, y -1.5..54.5, underside z 6.4 | USB-C / HDMI edge 0.5 from the rear wall, SD end toward +X, USB / Ethernet toward -X. M2.5 inserts |
| USB-C power | rear wall opening 14.6 x 8.6 at x 32.3, z 9.4 | sized for the plug overmold |
| SHT41 | floor, front left, x -32..-6.6, y -53..-35.2 | 3 mm bosses: 2 x M2 inserts + 2 pins. Behind the front slot |
| QT hub | hangs upside down under the spine top at the rear, x 12..37.4, y 30.5..48.3, board at z 37.2..38.8, connectors pointing down | 2 x M2 inserts + 2 pins on bosses under the top. Moved here from the front floor so the soil cable reaches: 9.5 clear above the HAT |
| Soil cable | open notch 8.5 x 4.2 in the bottom edge of the spine's rear wall, at x 32 | about 28 mm of the 200 mm cable is inside. Modelled as `FLAT \| Soil cable 4424 \| 200 mm`: 166 mm to where the sensor stands, 34 spare |
| NeoPixel ring | spine top, centre (0, -24.5), LEDs up | same lens, retainer and 3 x M2 as the tall pod |
| VEML7700 | spine top, window at (-33, -24.5) | same window and mounting as the tall pod |
| L logo | recess in the spine top, rear half, x -13.4..20.4, y 10.7..48, 1.8 deep | where Pat placed the mark. Pocket is the logo outline + 0.15 all round; the top is thickened underneath so the floor stays 2.4. Purple inlay glued in |
| Lettering | "FLORA" on the tray front face, cap height 9, 54 wide, centred at z 18, above the slot; "LUMALIEN" on the spine top under the L mark, cap height 6.5, 59 wide, centred at (3.4, 4.4) | custom wide single-weight font drawn for this (A without a crossbar; O, R, U round-cornered). FLORA: pocket 1.2 deep, stroke 1.3, with purple inlay letters 1.0 thick, 0.1 smaller all round. LUMALIEN: pocket 1.0 deep, stroke 0.94, with purple inlay letters 0.8 thick, only 0.05 smaller all round so their strokes are 0.84 (two lines from a 0.4 nozzle) |
| Lux window | spine top at (-33, -24.5) | plugs in from inside. Now a cup: 0.4 mm face, 6.5 mm clear bore, so clear filament stays see-through. Can also be left out (open hole) |
| Spine fixing | 2 x M3 x 30 up through the base posts at (+/-42, -50.5) into inserts in the spine | no screws visible from the top. A skirt under the spine drops through the collar and deck and locates all three |
| Vents | wings: 20 slots in the deck; front: 1 slot at z 10 (tray) and 1 at z 39 (spine); rear: intake 2 slots at z 15, 21 (tray), exhaust 2 slots at z 39 (spine) | all slots 34 x 2.4 with round ends |

## Print parts (10)

| Part | Size | Colour | Orientation |
|---|---|---|---|
| FLAT_LOGO_INLAY | 33.2 x 36.8 x 1.5, two pieces (L and triangle) | purple | flat |
| FLAT_FLORA_INLAY | 5 letters, 8.8 tall x 1.0 thick, strokes 1.1 | purple | flat |
| FLAT_LUMALIEN_INLAY | 8 letters, 6.4 tall x 0.8 thick, strokes 0.84 | purple | flat |
| FLAT_BASE | 188 x 118 x 27.2 | white | upright |
| FLAT_DECK | 188 x 118 x 5.4 (2.4 plate + lip) | white | upside down, top face on the bed |
| FLAT_COLLAR | 100 x 118 x 3 | purple | flat |
| FLAT_SPINE | 100 x 118 x 20.8 | white | upside down, top face on the bed |
| FLAT_HALO_LENS, FLAT_HALO_RETAINER | as the tall pod | | same meshes as the tall pod's |
| FLAT_LUX_WINDOW | dia 13.7 x 3.4, 0.4 face | clear | small face down on a smooth plate |

Walls, floor and top 2.4 mm. Everything fits the Bambu A1. The ring and lux mounting under
the spine top is the tall pod cap's, cut out and reused, so the lens and
retainer are shared. The lux window has the same outside shape but is hollowed out.

## Hardware

- Heat-set inserts: 9 x M2, 4 x M2.5, 2 x M3 (same hole sizes as the tall pod).
- Screws: 9 x M2x5, 4 x M2.5x6, 2 x M3x30.
- 4 x 10 mm stick-on feet (recessed).

## Assembly order

1. Set the inserts: 6 in the base, 7 in the spine top, 2 in the spine posts.
2. SHT41 onto the floor, then the Pi with the HAT. Speakers down either side.
3. Plug in the speaker lead.
4. Deck on. Collar on.
5. In the spine: lens, ring, retainer; lux window, lux board; hub. Plug the ring jumpers
   into the HAT, and the lux, SHT41, Pi and soil cables into the hub.
6. Lay the soil cable in the rear notch, lower the spine, two screws from underneath.

## Checked

- Sampled every placed electronics part against the four big print parts: nothing sits
  inside plastic.
- The four big print parts do not overlap each other, and each is a closed solid.

## Not checked, or guessed

- Only the soil cable is modelled. With the hub in the spine, four cables tie the spine to
  the base while it is being closed.
- Other cables and plugs are not modelled. The jumper sockets on the HAT header are the tallest
  thing inside: estimated top at z 37 plus the wire bend, under a ceiling at z 43.6.
- Speaker leads have to reach the HAT's JST from the front end of each speaker: not routed.
- The deck's outer edges are held only by the lip fit; the spine clamps its inner edges.
- The rear of the spine is located by its skirt but not screwed down.
- The step inside the spine wall (1.4 mm, at z 36) prints as a small unsupported ledge.
- Cooling: less vent area than the tall pod's first version, no fan, HAT over the CPU.
- Microphones face up under the spine top; the front spine slot is their path to the room.
- SD card: spine off.
- Same sensor, insert and I2C address caveats as the tall pod, below.

# Tall pod (2026-10-04, backup)

Print parts are in `FLORA PRINT PARTS`; linked copies of the electronics are in
`FLORA PLACED PARTS`.

## Concept

An upright white pod, 108 x 76 mm footprint, 128 mm tall, plan corners R16. A purple collar
band separates the body from a white cap. The NeoPixel ring sits in the cap as an
upward-facing halo under a lens, with the lux sensor's window beside it. Vents are kept to a
minimum and every one is the same horizontal slot, 30 x 2.4 mm with round ends, centred on
its wall. The front is blank apart from one slot near the base: the air path to the
temperature sensor and the only path to the microphones. Each side has five slots over the
speaker driver. Cooling air enters and leaves through the rear.

Vents reworked 2026-10-05; the first version used slits in three different sizes. That body
is kept in the file as `FLORA_BODY_v1_original_vents`, next to `FLORA_BODY_blank` (no vents,
for recutting a pattern), in the hidden collection `FLORA BACKUP`.

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
| Vents | front: 1 slot at z 10; sides: 5 slots at z 72..96, 6 mm pitch, over the driver (centre z 84); rear exhaust: 3 slots at z 92, 98, 104; rear intake: 2 slots at z 20, 26 | all slots 30 x 2.4, centred on the wall. 16 in total, about 70 mm2 each |

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
