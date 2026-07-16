# 🧾 Configuration File

Language: English | [Русский](CONFIG.ru.md)

Create a file named:

```text
/config.txt
```

Place it in the root directory of the MicroSD card.

Lines starting with `#` are comments.

The firmware reads:

- 📡 Wi-Fi credentials
- 💡 screen brightness
- 🌡️ climate thresholds
- 💧 watering schedule
- 🌱 soil sensor settings
- ⚡ relay mode
- ☁️ cloud connection settings

See [config.example.txt](config.example.txt) or [config.example.ru.txt](config.example.ru.txt).

## 📡 Wi-Fi

```text
ssid=YourRouterName
password=YourRouterPassword
```

## ☁️ Cloud

```text
cloud_enabled=true
cloud_url=http://sols.lv
```

If tokens are empty, firmware creates long tokens from the ESP32 device ID.

Do not share your private `cloud_api_token`.

## 🌡️ Climate Control Zone

By default the automation controls the sensor on the controller/display board:

```text
control_zone=inside
```

Use the remote wired sensor as the controlled zone when the display stays in one place and the cabled sensor is placed in another space, for example a basement or cellar:

```text
control_zone=outside
```

In this mode the fan turns on when the `outside` sensor is too hot or too humid and the `inside` air is cooler or drier.

Basement drying example:

```text
control_zone=outside
target_temp_c=45
temp_hysteresis_c=5
humidity_max=70
```

## 💧 Watering Modes

Without soil sensor:

```text
soil_sensor_enabled=false
watering_schedule_enabled=true
watering_interval_min=720
```

With soil sensor:

```text
soil_sensor_enabled=true
soil_moisture_min=45
soil_moisture_target=60
soil_watering_cooldown_min=120
```

## ⚡ Relays

Most relay boards are active-low:

```text
relay_active_low=true
```

If relay logic is inverted, change it to:

```text
relay_active_low=false
```
