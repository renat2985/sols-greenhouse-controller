# 🔒 Security Notes

Language: English | [Русский](SECURITY.ru.md)

This public package does not include Arduino/ESP32 firmware source code.

Do not commit:

- ❌ real Wi-Fi passwords,
- ❌ real `cloud_api_token`,
- ❌ private server credentials,
- ❌ Arduino `.ino`, `.h` or `.cpp` firmware source files.

Use [config.example.txt](config.example.txt) as a template and keep real `config.txt` private.

Firmware binaries are provided for the supported greenhouse controller hardware.
