# ESP32-LCD-01 Bluetooth Proxy for Home Assistant

This project is a custom ESPHome configuration for the following ESP32 board:
👉 [ESP32-C3 1.9" LCD Display Development Board with SH1106 OLED](https://www.aliexpress.com/item/1005008125231916.html?spm=a2g0o.order_list.order_list_main.28.67061802V3w2kA#nav-specification)

## Description
This ESPHome configuration turns the ESP32 board into a **Bluetooth Proxy** for Home Assistant, while also displaying real-time connection status information on the built-in SH1106 128x64 OLED screen.

It includes:
- Bluetooth Proxy functionality
- OLED display showing WiFi and Home Assistant status
- Blue LED that can be toggled via Home Assistant UI (optional visual status indicator)

## Features
- ✅ Bluetooth Proxy for passive BLE device tracking
- 📶 WiFi connection status displayed on screen
- 🏠 Home Assistant connection status displayed on screen
- 🔵 Blue LED controllable from Home Assistant to disable the light at night

## Pin Configuration
- **SDA**: GPIO5
- **SCL**: GPIO6
- **OLED Reset Pin**: GPIO3
- **Blue LED Pin**: GPIO8 (⚠️ Strapping pin, use with caution)

## Display
The OLED screen shows:
- `WiFi: OK` / `WiFi: NO`
- `HA: OK` / `HA: NO`

Centered text, updated every 2 seconds.

## Home Assistant Integration
Once added via ESPHome integration, you will see:
- Two `text_sensor` entities showing WiFi and HA status
- One `light` entity controlling the blue LED
- One `switch` to toggle the LED manually

## Usage
1. Flash the ESP32 board with this configuration using ESPHome
2. Add the device in Home Assistant via ESPHome integration
3. Use the blue LED switch in the dashboard to disable the light if needed

## Notes
- GPIO8 is a strapping pin on ESP32-C3. Use it carefully and avoid pull-up/down resistors on it.
- Font used for the display is `OpenSans-Bold` size 16 via local TTF file
- Ensure your secrets (`wifi_ssid`, `wifi_password`) are set up in `secrets.yaml`

## License
MIT License

