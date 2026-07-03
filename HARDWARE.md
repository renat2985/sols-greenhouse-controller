# Hardware And Wiring

## Main Board

This project is based on the `JC3248W535` ESP32-S3 display board.

Use a stable external power supply for normal work. During testing we noticed that powering the device only from a computer USB port can make the UI slower, depending on the USB port and cable.

## Connector Plan

### Big GPIO Connector P2

| Pin | GPIO | Use |
| ---: | ---: | --- |
| P2-1 | IO5 | Spare. Avoid for relay output because the schematic uses it for battery sense. |
| P2-2 | IO6 | Exhaust fan relay |
| P2-3 | IO7 | Intake fan relay |
| P2-4 | IO15 | Water valve / pump relay |
| P2-5 | IO16 | Spare |
| P2-6 | IO46 | Avoid for relay outputs |
| P2-7 | IO9 | Soil moisture analog input |
| P2-8 | IO14 | LDR light sensor analog input |

### Small 4-Pin Sensor Connector

| Signal | Use |
| --- | --- |
| GND | Sensor ground |
| 3.3V | Sensor power |
| IO17 | I2C SDA |
| IO18 | I2C SCL |

I2C speed: 100 kHz.

## Climate Sensors

### Indoor Sensor

Recommended module:

- AHT20 + BMP280
- I2C
- AHT20 address: `0x38`
- BMP280 address: usually `0x76` or `0x77`

Used values:

- temperature
- humidity

Pressure from BMP280 is reserved for future use.

### Outdoor Sensor

Recommended module:

- SHT40
- I2C
- address: `0x44`

Using AHT20 indoors and SHT40 outdoors is useful because they have different I2C addresses and can share the same SDA/SCL wires.

## Relays

Use a 3-channel relay module or three separate relay modules.

| GPIO | Relay | Example load |
| ---: | --- | --- |
| IO6 | Exhaust relay | Fan pushing air out |
| IO7 | Intake relay | Fan pulling air in |
| IO15 | Water relay | Water valve or pump |

Default relay mode is active-low:

```text
relay_active_low=true
```

If your relay module turns on with HIGH level, set:

```text
relay_active_low=false
```

Important: mains voltage wiring must be done safely. Use proper relay isolation, fuses, cable strain relief and an enclosure.

## Optional Soil Moisture Sensor

Analog input:

```text
IO9
```

The firmware can work without this sensor. In that mode watering is controlled by schedule.

## Optional Light Sensor

Analog input:

```text
IO14
```

Use an LDR voltage divider powered from 3.3V.

## Relay Board Concept

![Relay and sensor board](images/greenhouse-relay-board.jpg)

The manufacturable PCB files are included as [Gerber.zip](Gerber.zip).

Read [PCB.md](PCB.md) for ordering notes and important safety warnings.
