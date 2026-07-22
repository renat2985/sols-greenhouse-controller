# 🚀 Прошивка устройства

Язык: [English](FLASHING.md) | Русский

## ✨ Рекомендуемый способ

Откройте веб-установщик:

👉 [https://sols.lv/upgrade](https://sols.lv/upgrade)

Рекомендуемый браузер:

- ✅ Chrome
- ✅ Edge

Safari обычно не поддерживает WebSerial.

Шаги:

1. 🔌 Подключите экран к компьютеру через USB.
2. 🌐 Откройте установщик.
3. 🧭 Выберите serial port.
4. ⚡ Установка начнется автоматически.
5. ⛔ Не отключайте USB во время записи.
6. ✅ Когда прошивка завершится, отключите и снова подключите питание, если устройство не перезапустилось само.

## 🧰 Ручная прошивка

Ручная прошивка нужна только продвинутым пользователям.

Используйте файлы из папки [firmware](firmware/):

| Файл | Адрес |
| --- | ---: |
| `greenhouse.bootloader.bin` | `0x0` |
| `greenhouse.partitions.bin` | `0x8000` |
| `boot_app0.bin` | `0xe000` |
| `greenhouse.app.bin` | `0x10000` |

Параметры:

- Chip: ESP32-S3
- Baud: 921600
- Flash size: 16 MB
- PSRAM: OPI PSRAM
- Flash mode: QIO 80 MHz
- Partition: No OTA, 2 MB APP / 2 MB SPIFFS

## 🔐 Контрольные суммы

SHA-256:

```text
f94c5d786a7a8fab06ac5d10e33bf37711a6697636dc037559ea19cc410a17f0  boot_app0.bin
8800ad4e48b506eefe4c6fae73d20c2bfb5c44f86e60b120ee298cf340361e7d  greenhouse.app.bin
1051ac3e564bb9368a635af94a219d01c6263dc7a89a5e132bd01fef925026a2  greenhouse.bootloader.bin
1992e7122a5ed6829844bcce1f43d37b0ccaa41856dc22759741833e0c30c948  greenhouse.full.bin
6a88d59601a83a16a19a08114b59d338324b8dec267d8b43e5d61ad56ec92102  greenhouse.partitions.bin
824866b95c25843725112742cd470742e9a3bb6f125dbb0179a3afe075695ba0  manifest.json
```
