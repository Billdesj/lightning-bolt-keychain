# Lightning Bolt PCB Keychain

A small, wizard-inspired light-up PCB keychain shaped like a chunky lightning bolt.

This is a first-pass KiCad hardware project designed to be realistic to fabricate:

- CR2032 coin-cell power
- On/off SPST switch
- Three amber 0603 LEDs
- One current-limit resistor per LED
- Matte black PCB with ENIG/gold copper artwork
- Plated keyring hole near the top bend
- Durable widened lightning-bolt outline

## Files

- `hardware/lightning-bolt-keychain.kicad_pro` - KiCad project file
- `hardware/lightning-bolt-keychain.kicad_sch` - schematic starter
- `hardware/lightning-bolt-keychain.kicad_pcb` - PCB starter with board outline, footprints, and simple routing/art traces
- `bom/lightning-bolt-keychain-bom.csv` - parts list
- `fabrication/fab-notes.md` - PCB fab settings and assembly notes

## Electrical Design

The circuit is intentionally simple:

```text
CR2032 + -> switch -> three parallel LED branches -> CR2032 -

Each branch:
VLED -> 220 ohm resistor -> amber LED -> GND
```

Amber LEDs are a better fit than white LEDs for a CR2032 because their forward voltage is lower. With a fresh 3 V coin cell and a 220 ohm resistor, each LED branch should run in a gentle low-current range suitable for a keychain.

## KiCad Notes

Open `hardware/lightning-bolt-keychain.kicad_pro` in KiCad 7 or newer.

Before fabrication:

- Confirm all footprints exist in your KiCad library install.
- Run ERC and DRC.
- Tune LED brightness by changing `R1`, `R2`, and `R3`.
- Verify the CR2032 holder footprint matches the exact part you order.
- Consider adding test points if you want easier debugging.

## Visual Direction

Recommended finish:

- PCB: matte black solder mask
- Copper finish: ENIG
- Silkscreen: minimal or none on the front
- LEDs: amber / warm yellow
- Thickness: 1.6 mm

Keep the lightning bolt chunky. Thin sharp points look cool in a render, but keychains live a rough life.
