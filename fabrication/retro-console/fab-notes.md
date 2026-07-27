# Retro Console PCB Keychain Fabrication Notes

## Board

- Design: BMO-inspired retro handheld PCB keychain
- This is an original retro-console style board, not an exact character copy.
- PCB thickness: 1.6 mm FR4
- Copper layers: 2
- Finish: ENIG recommended
- Solder mask: teal/blue-green recommended
- Connector: USB-C receptacle, cable-powered, not a male plug

## Electrical

- USB-C CC1/CC2 use 5.1k Rd pull-downs to request default 5 V from USB-C sources.
- F1 protects VBUS before the LED branches.
- Five amber LEDs use individual current-limiting resistors.

## Mechanical

- Keyring hole is near the top area.
- Confirm the GCT USB4125-GF-A-0190 connector orientation and shell stakes before ordering parts.
- Order as a prototype first and inspect connector fit, keyring strength, and visual alignment.

## Checks

- KiCad DRC: 0 violations
- KiCad ERC: 0 violations
- Unconnected items: 0
