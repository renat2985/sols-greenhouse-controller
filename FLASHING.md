# 🚀 Flashing Firmware

Language: English | [Русский](FLASHING.ru.md)

## ✨ Recommended Method

Open the web installer:

👉 [https://sols.lv/upgrade](https://sols.lv/upgrade)

Recommended browser:

- ✅ Chrome
- ✅ Edge

Safari usually does not support WebSerial.

Steps:

1. 🔌 Connect the display to the computer with USB.
2. 🌐 Open the installer.
3. 🧭 Select the serial port.
4. ⚡ The installer starts flashing automatically.
5. ⛔ Do not disconnect USB during writing.
6. ✅ When flashing is complete, disconnect and reconnect power if the device does not restart automatically.

## 🧰 Manual Flashing

Manual flashing is only for advanced users.

Use files from [firmware](firmware/):

| File | Address |
| --- | ---: |
| `greenhouse.bootloader.bin` | `0x0` |
| `greenhouse.partitions.bin` | `0x8000` |
| `boot_app0.bin` | `0xe000` |
| `greenhouse.app.bin` | `0x10000` |

Settings:

- Chip: ESP32-S3
- Baud: 921600
- Flash size: 16 MB
- PSRAM: OPI PSRAM
- Partition: No OTA, 2 MB APP / 2 MB SPIFFS

## 🔐 Checksums

SHA-256:

```text
f94c5d786a7a8fab06ac5d10e33bf37711a6697636dc037559ea19cc410a17f0  boot_app0.bin
4d13cfc5961904e70b45bb07ba5a51a5d1eb1be66f36ed9df65ffbbdc1ac3763  greenhouse.app.bin
1051ac3e564bb9368a635af94a219d01c6263dc7a89a5e132bd01fef925026a2  greenhouse.bootloader.bin
fd45bfb5285343fd6ff3648b8d70d8b0609a245fef22f74314304292c6b8c711  greenhouse.full.bin
6a88d59601a83a16a19a08114b59d338324b8dec267d8b43e5d61ad56ec92102  greenhouse.partitions.bin
e0919fa0c6d6d3f53d3a7ec87c15b7289d7b387bcfc3cacf95595a318e77a4e4  manifest.json
```
