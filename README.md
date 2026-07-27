# Lightning Bolt PCB Keychain

A small, wizard-inspired light-up PCB keychain shaped like a chunky lightning bolt.

This is a first-pass KiCad hardware project designed to be realistic to fabricate:

- 12 mm 3 V coin-cell power, e.g. CR1220/CR1225 with Keystone 3000 retainer
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
12 mm coin cell + -> switch -> three parallel LED branches -> coin cell -

Each branch:
VLED -> 220 ohm resistor -> amber LED -> GND
```

Amber LEDs are a better fit than white LEDs for a small coin cell because their forward voltage is lower. With a fresh 3 V coin cell and a 220 ohm resistor, each LED branch should run in a gentle low-current range suitable for a keychain.

## KiCad Notes

Open `hardware/lightning-bolt-keychain.kicad_pro` in KiCad 7 or newer.

Before fabrication:

- Confirm all footprints exist in your KiCad library install.
- Run ERC and DRC.
- Tune LED brightness by changing `R1`, `R2`, and `R3`.
- The PCB currently matches a Keystone 3000 style 12 mm coin-cell retainer. For CR2032, swap to a 20 mm holder such as Keystone 3002/3034 and reroute BT1.
- Consider adding test points if you want easier debugging.

## Visual Direction

Recommended finish:

- PCB: matte black solder mask
- Copper finish: ENIG
- Silkscreen: minimal or none on the front
- LEDs: amber / warm yellow
- Thickness: 1.6 mm

Keep the lightning bolt chunky. Thin sharp points look cool in a render, but keychains live a rough life.

## Parts Availability Notes

Checked 2026-07-27:

- BT1: Keystone 3000 is active and available, but it is a 12 mm coin-cell retainer for cells such as 1216/1220/1225, not CR2032. DigiKey showed 20k+ in stock. Mouser/DigiKey also have Keystone 3002/3034 20 mm CR2032 retainers in stock if the design is changed to CR2032.
- SW1: Panasonic EVQP2-family tactile switches are active and available. DigiKey showed EVQ-P2R02W in stock; Mouser showed multiple EVQP2 options in stock. The PCB uses the KiCad footprint name `Button_Switch_SMD:SW_SPST_EVQP2_ShortPushTravel_H2.1mm`; confirm the exact switch variant before ordering.
- D1-D3: 0603 amber LEDs are broadly available. Broadcom/Avago HSMA-C191/C190 style 0603 amber LEDs showed large distributor stock.
- R1-R3: 0603 220 ohm resistors are commodity parts and widely available. Mouser showed hundreds of 0603 220 ohm options.

Sources checked: DigiKey and Mouser search/product pages.