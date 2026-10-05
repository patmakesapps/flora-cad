# Flora flat console — hardware

What goes into each printed part. STL files are in `STL/`, already turned to print orientation.

## Shopping list

| Item | Size | Qty |
|---|---|---|
| Heat-set insert | M2, 3.2 mm wide, 4 mm long | 9 |
| Heat-set insert | M2.5, 3.5 mm wide, 4 mm long | 4 |
| Heat-set insert | M3, 5 mm wide, 4 mm long | 4 |
| Screw | M2 x 5 | 9 |
| Screw | M2.5 x 5 or 6 (standard Pi screw) | 4 |
| Screw | M3 x 30 button head | 2 |
| Screw | M3 x 6 button head | 2 |
| Stick-on foot | 12.7 mm wide, 3.5 mm tall | 4 |

## By printed part

### FLAT_BASE

| Inserts | Where | Screws that go in | What they hold |
|---|---|---|---|
| 4 x M2.5 | four bosses on the floor | 4 x M2.5 x 5 or 6 | Raspberry Pi |
| 2 x M2 | two of the four small bosses at the front left | 2 x M2 x 5 | temperature sensor (the other two bosses are locating pins) |

Plain holes, no inserts:

- 2 holes up through the front posts, head recess underneath: 2 x M3 x 30, into the spine.
- 2 holes through the back wall, head recess on the outside: 2 x M3 x 6, into the spine.
- 4 round recesses underneath: the stick-on feet.

### FLAT_SPINE

| Inserts | Where | Screws that go in | What they hold |
|---|---|---|---|
| 2 x M3 | bottom of the two front posts | 2 x M3 x 30, from under the base | spine front |
| 2 x M3 | the two tabs that hang down at the back | 2 x M3 x 6, through the base's back wall | spine rear |
| 3 x M2 | bosses around the halo opening | 3 x M2 x 5 | halo retainer (which holds the ring and lens) |
| 2 x M2 | bosses beside the lux opening | 2 x M2 x 5 | lux sensor board (plus two locating pins) |
| 2 x M2 | two of the four hub bosses at the rear | 2 x M2 x 5 | hub (the other two bosses are locating pins) |

### No hardware

| Part | How it is held |
|---|---|
| FLAT_DECK | clamped between the base and the collar and spine |
| FLAT_COLLAR | clamped between the deck and the spine |
| FLAT_HALO_LENS | trapped by the halo retainer |
| FLAT_HALO_RETAINER | the 3 x M2 x 5 listed under the spine |
| FLAT_LUX_WINDOW | pushed in from inside the spine before the lux board goes on; a dab of glue |
| FLAT_LOGO_INLAY, FLAT_FLORA_INLAY, FLAT_LUMALIEN_INLAY | glued into their pockets |

Speakers: glue or zip tie. Nothing printed holds them.

## Notes

- Insert hole sizes in the model: 2.9 mm for M2, 3.2 mm for M2.5, 4.6 mm for M3. Not yet
  tested against the insert kit; print a test hole before the big parts.
- M2 and M2.5 insert holes are 4.5 to 5 mm deep, so keep those screws to 6 mm or shorter.
