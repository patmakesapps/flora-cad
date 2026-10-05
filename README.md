# flora-cad

CAD for Flora, the Raspberry Pi 5 desk voice companion. This is the hardware side: real
electronics modelled at real size, ready to design an enclosure around.

Current state: **parts library plus two enclosure concepts** (a flat console, shown, and a
tall pod kept as backup). See `FLORA_SPEC.md`. STL files exist for the flat console only.

```
STL/                        print files for the flat console, in print orientation, mm
HARDWARE.md                 inserts and screws for each printed part
Blender/FLORA_v1.blend      the model (Blender 5.1)
Blender/reference/          bench photos, vendor CAD sources, notes
FLORA_SPEC.md               the enclosure concepts: layout, print parts, open questions
```

Read `Blender/reference/README.md` before using the bench photos: the X1200 UPS HAT in them
is not part of the real build.

## Design brief (Pat, 2026-10-04)

- **Printer:** Bambu Lab A1. Every printed part has to fit its 256 x 256 x 256 mm build volume.
- **Colours:** mostly white, with purple accents. White and purple are the Lumalien colours;
  a little black is fine. Flora lives with plants, and white stands out against the green.
- **Sensors:** soil moisture, light, temperature and humidity, all on one I2C bus through the
  5-port hub.
- **Speakers:** held with zip ties and/or glue. No screw mounts needed.
- **Power:** no X1200 UPS HAT in the real build.
- **Placement:** not decided yet.

## Conventions

Same as the Lumalien hardware library (`MASTER HARDWARE - PARTS REFERENCE.md`).

| Thing | Rule |
|---|---|
| Units | 1 Blender unit = 1 mm (unit scale 0.001). All dimensions below are mm. |
| Structure | One collection per part, numbered `NN - Part Name`. |
| Object naming | `PART \| descriptor \| key dimension`. |
| Board datum | Origin = PCB bottom face at the board's minimum corner; board extends +X / +Y, components +Z. The Pi 5 is the exception (legacy origin). |
| Metadata | Parts 18 to 22 carry custom properties on the object: `source`, `source_url`, `datum`, `envelope_mm`, `mount_pattern`, `connector`, `approximations`. Read `approximations` before trusting a number. |
| Shading | Smooth, with edges over 30 degrees marked sharp. |
| Parking | Parts rest on z = 0 in a block at x 227 to 597, y -122 to 114. The origin is left clear for the build. |
| Viewport | Solid mode. |

## Parts

### Brought in from `C:\Lumalien\LX-5\Blender\LX-5.blend`

| Collection | Part | Size |
|---|---|---|
| 11 | Raspberry Pi 5 (official STEP, decimated) | board 85 x 56; envelope 88.5 x 57.6 x 19 |
| 14 | Waveshare WM8960 Audio HAT, seated on the Pi and parented to it | 65 x 30 |
| 14 | Waveshare 8 ohm 5 W speakers, L and R, with leads | 100 x 45 x 21 (112 over the ears) |
| 16 | NeoPixel Ring 12, Adafruit 1643 (one) | OD 36.8 |

### Sensor order, added 2026-10-04

| Collection | Part | Envelope | Mounting | Connector | Source |
|---|---|---|---|---|---|
| 18 | STEMMA Soil Sensor, Adafruit 4026 | 76.2 x 13.97 x 6.37 | 2 x dia 2.54 at (22.86, 2.54) and (22.86, 11.176) | JST PH 4-pin, side entry, at the x = 0 end | Adafruit STEP |
| 19 | VEML7700 Lux Sensor, Adafruit 4162 | 25.4 x 17.78 x 4.53 | 4 x dia 2.5, pattern 20.32 x 12.70, 2.54 in from the edges | 2 x JST SH 4-pin, side entry, left and right | Built from Adafruit's Eagle board file |
| 20 | STEMMA QT 5-Port Hub, Adafruit 5625 | 25.4 x 17.78 x 5.87 | same as 19 | 5 x JST SH 4-pin, **vertical**, 5.08 pitch | Adafruit STEP |
| 21 | SHT41 Temp + Humidity, Adafruit 5776 | 25.4 x 17.78 x 4.53 | same as 19 | 2 x JST SH 4-pin, side entry, left and right | Adafruit SHT40 STEP (same PCB) |
| 22 | QT to 4 female sockets cable, Adafruit 4397 | 169 long | | SH plug 5.0 (7.0 over ears) x 5.0 x 2.8; sockets 2.54 x 2.54 x 14 each | Parametric |
| 22 | JST PH to QT cable, Adafruit 4424 | 212 long | | PH plug 9.8 x 6.85 x 4.5 | Parametric |
| 22 | QT to QT cable 200 mm, Adafruit 4401 (two) | 210 long | | flat black jacket 4.8 x 1.5 | Parametric |

Hole positions are board-local, from the datum corner.

### What is measured and what is guessed

- **18, 20, 21** are vendor geometry. Only the colours were changed (PCB and connector
  housings) to match the real boards.
- **19** has no vendor 3D model. Outline, holes and part positions come from Adafruit's Eagle
  file; the connector and small-part solids are reused from the SHT40 STEP, which shares the
  board format. The sensor itself is a plain 6.8 x 3.0 x 2.35 block at board-local
  x 9.3 to 16.1, y 12.2 to 15.2, top face at z 3.92, looking +Z. That is the area an
  enclosure window has to sit over.
- **21** assumes the SHT41 on hand is Adafruit's #5776. Not checked against the real board.
- **22** cables are blockouts in a straight parking pose. Plug sizes are from the JST SH and
  PH datasheets. Wire diameter (0.8), socket length (14) and the 4401 jacket section are
  estimates. To route one, move its `| end B` child and edit its `| wires` curve.
- The hub's connectors are vertical: a plugged-in cable needs room above the board.

## Converting vendor STEP

STEP files were tessellated with OpenCascade (`cadquery-ocp`) at 0.05 mm / 0.5 rad into one
merged vertex and face list with a per-face colour, then built as a single mesh. Each board
is 4,000 to 12,000 triangles. No build scripts are kept in this repo, on purpose.
