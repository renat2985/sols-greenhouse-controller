# 🛠️ PCB Manufacturing Files

This repository includes:

```text
Gerber.zip
```

The archive contains Gerber and drill files for the relay/sensor add-on board.

## 📦 What Is Included

The archive includes:

- top and bottom copper layers,
- top and bottom solder mask,
- top and bottom silkscreen,
- board outline,
- drill files,
- assembly/document layers.

## 🛒 How To Order

Upload `Gerber.zip` to a PCB manufacturer that accepts standard Gerber files.

Common services:

- JLCPCB
- PCBWay
- Aisler
- Eurocircuits
- other local PCB factories

Typical order flow:

1. 📤 Upload `Gerber.zip`.
2. 👀 Preview the board in the manufacturer's Gerber viewer.
3. 📐 Check board size, outline and holes.
4. 🎨 Choose PCB color and quantity.
5. ✅ Order only the bare PCB unless you also have a BOM and assembly files.

## 🧪 Important Notes

This file is for PCB manufacturing only. It does not include a full assembly/BOM guide yet.

Before ordering many boards:

- order a small prototype batch first,
- visually check the Gerber preview,
- verify connector orientation,
- verify relay footprints,
- verify sensor connector labels,
- test one assembled board with low voltage first.

## ⚠️ Mains Voltage Warning

The board may be used to control relays connected to 220V/230V AC loads such as fans or valves.

Mains voltage is dangerous. Assembly and installation must be done by a qualified person using:

- proper isolation,
- correct wire gauge,
- fuses or breakers,
- strain relief,
- protected enclosure,
- safe distance between low-voltage and mains wiring.

Do not touch or modify mains wiring while powered.

## 🔒 Repository Policy

PCB manufacturing files are public so users can order their own relay/sensor board.

Firmware source code remains private. Firmware binaries are provided in [firmware](firmware/).
