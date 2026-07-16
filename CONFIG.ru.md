# 🧾 Файл конфигурации

Язык: [English](CONFIG.md) | Русский

Создайте файл:

```text
/config.txt
```

Положите его в корень MicroSD карты.

Строки, которые начинаются с `#`, считаются комментариями.

Прошивка читает:

- 📡 Wi-Fi имя и пароль
- 💡 яркость экрана
- 🌡️ границы климата
- 💧 расписание полива
- 🌱 настройки датчика влажности почвы
- ⚡ режим реле
- ☁️ настройки облачного подключения

Примеры:

- [config.example.txt](config.example.txt)
- [config.example.ru.txt](config.example.ru.txt)

## 📡 Wi-Fi

```text
ssid=YourRouterName
password=YourRouterPassword
```

## ☁️ Облако

```text
cloud_enabled=true
cloud_url=http://sols.lv
```

Если токены пустые, прошивка создаст длинные токены на основе ESP32 device ID.

Не публикуйте приватный `cloud_api_token`.

## 🌡️ Контролируемая зона климата

По умолчанию автоматика контролирует датчик на экране/плате контроллера:

```text
control_zone=inside
```

Если экран стоит в одном месте, а выносной датчик на проводе находится в другой зоне, например в погребе или подвале, можно контролировать именно выносной датчик:

```text
control_zone=outside
```

В этом режиме вентилятор включается, когда `outside` датчик показывает слишком высокую температуру или влажность, а воздух у `inside` датчика холоднее или суше.

Пример для осушения погреба:

```text
control_zone=outside
target_temp_c=45
temp_hysteresis_c=5
humidity_max=70
```

## 💧 Режимы полива

Без датчика влажности почвы:

```text
soil_sensor_enabled=false
watering_schedule_enabled=true
watering_interval_min=720
```

С датчиком влажности почвы:

```text
soil_sensor_enabled=true
soil_moisture_min=45
soil_moisture_target=60
soil_watering_cooldown_min=120
```

## ⚡ Реле

Большинство модулей реле работают как active-low:

```text
relay_active_low=true
```

Если логика реле перевернута, поменяйте на:

```text
relay_active_low=false
```
