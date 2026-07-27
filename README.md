# USB-C Lightning Bolt PCB Keychain

A USB-C powered light-up PCB keychain shaped like a chunky lightning bolt. Plug it into a USB-C charger, power bank, or powered port and the amber LEDs light the bolt.

## Design

- USB-C power-only input, 5 V VBUS
- Correct USB-C sink detection with 5.1k pull-downs on CC1 and CC2
- 500 mA resettable fuse footprint on VBUS
- Five amber 0603 LEDs arranged down the lightning bolt
- One 1k current-limit resistor per LED branch
- Matte black solder mask with ENIG finish recommended
- Reinforced plated keyring hole
- Flat bottom edge for the USB-C receptacle

## Electrical Design

```text
USB-C VBUS -> F1 polyfuse -> VLED
CC1 -> 5.1k -> GND
CC2 -> 5.1k -> GND
VLED -> 1k resistor -> amber LED -> GND  (five branches)
```

The board is intentionally power-only. It does not route USB data. The CC pull-down resistors are what make a USB-C source provide default 5 V to the board.

## Files

- `hardware/lightning-bolt-keychain.kicad_pro` - KiCad project file
- `hardware/lightning-bolt-keychain.kicad_sch` - USB-C powered schematic
- `hardware/lightning-bolt-keychain.kicad_pcb` - lightning-bolt PCB layout
- `bom/lightning-bolt-keychain-bom.csv` - parts list
- `fabrication/fab-notes.md` - PCB fab and assembly notes

## Build Notes

- Use a USB-C power-only receptacle matching the KiCad footprint, currently `GCT USB4125` family.
- Use 5.1k 0603 resistors for `RCC1` and `RCC2`; these are required for USB-C power input.
- Start with 1k LED resistors for gentle brightness from USB 5 V. Lower values such as 680 ohm are brighter; higher values such as 1.5k or 2.2k are softer.
- Confirm the USB-C connector orientation before ordering boards.

## Visual Direction

Recommended finish:

- PCB: matte black solder mask
- Copper finish: ENIG / gold
- LEDs: amber / warm yellow
- Thickness: 1.6 mm

Keep the bolt chunky. Thin points look cool in renders but keychains get abused.
