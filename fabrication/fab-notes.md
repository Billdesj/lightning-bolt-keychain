# Fabrication Notes

## Recommended PCB Settings

- Layers: 2
- Thickness: 1.6 mm
- Material: FR4
- Solder mask: matte black
- Surface finish: ENIG
- Copper weight: 1 oz
- Minimum trace/space: 6/6 mil or better
- Minimum drill: 0.3 mm or fab standard
- Edge cuts: rounded/chamfered lightning bolt outline

## Assembly Notes

- Place LEDs on the front side so the glow is visible.
- Keep the 12 mm coin-cell retainer on the back side if possible.
- Keep the switch accessible from the edge or back.
- Use amber LEDs for reliable operation from a small 3 V coin cell.
- If the LEDs are too bright or battery life is poor, increase `R1`-`R3` to 330 ohm or 470 ohm.

## Mechanical Notes

- Do not make the bolt tips too thin. Keep at least 6 mm of board width around narrow sections.
- Add copper around the keyring hole on both sides.
- Consider via stitching around the keyring hole for durability.
- Add small corner radii where your fab supports it, or approximate them with chamfered outline segments.

## Part Compatibility

- Current PCB footprint is Keystone 3000 style for 12 mm coin cells, not CR2032.
- To use CR2032, change BT1 to a 20 mm holder footprint such as Keystone 3002 or 3034 and reroute the battery pads.
