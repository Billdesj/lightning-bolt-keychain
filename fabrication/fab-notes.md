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
- Edge cuts: chunky lightning bolt with a flat USB-C connector edge

## Assembly Notes

- Place the USB-C receptacle at the flat bottom edge. Confirm connector overhang/orientation against the datasheet before ordering.
- `RCC1` and `RCC2` must be 5.1k pull-downs to GND for USB-C sink/default-power behavior.
- `F1` protects VBUS; 500 mA hold current is more than enough for this LED keychain.
- Start with 1k LED resistors. Lower values increase brightness and current draw.
- Use amber LEDs for a warm lightning-bolt look.

## Mechanical Notes

- Keep the bolt outline chunky enough for pocket/keyring abuse.
- Keep at least 0.5 mm copper clearance from Edge.Cuts.
- The USB-C connector shell stakes provide mechanical support, but the flat connector edge should be reviewed in the 3D viewer before fab.
- The keyring hole should remain plated and reinforced with copper on both sides.

## Part Compatibility

- Current USB-C footprint targets the GCT USB4125-style 6-pin power-only receptacle.
- Equivalent USB-C connectors are fine only if their pad and shell-stake geometry match.
- This board is power-only and intentionally does not route D+/D- or high-speed USB signals.

## Fabrication Package

- Final fab zip: `fabrication/lightning-bolt-keychain-fab-package.zip`
- KiCad ERC report: `fabrication/erc-report.txt` reports 0 violations.
- KiCad DRC report: `fabrication/drc-report.txt` reports 0 violations and 0 unconnected items.
- Gerbers are in `fabrication/gerbers/`; drill output is in `fabrication/drill/`.
- USB-C connector target: GCT USB4125-GF-A-0190 / USB4125 family, power-only 6-pin top-mount receptacle.