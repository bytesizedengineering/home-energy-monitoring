# Whole-Home Energy Monitoring System

![Project Image](docs/project-image.png)  
*A DIY, ESP32-based energy monitoring system that tracks up to 9 circuits using CT clamps and integrates seamlessly with Home Assistant.* 

## 🚀 Overview  
This project provides a cost-effective way to monitor real-time electricity usage across multiple circuits in your home. By using non-invasive Current Transformer (CT) clamps, the system measures magnetic induction to calculate amperage without cutting into your home's wiring.

This project was featured on the [DigiKey YouTube channel](https://www.youtube.com/@digikey) in [this video](https://youtu.be/54pZV8P7hGM?si=jUmZ82UDNDB7HiG6).

## 📂 Repository Structure  
```
📁 mechanical design/   # 3D printable enclosure files (STLs, STEP)
📁 electrical design/   # KiCad PCB files for the stackable 3-channel CT board
📁 firmware/            # ESPHome YAML configuration files
📁 docs/                # Documentation
```

## 🏗️ Build Instructions  

### 🔌 Electronics  
The hardware is built around a stackable PCB design that can scale up to nine individual channels.
- **Microcontroller**: Seeed Studio XIAO ESP32-S3.
- **Sensors**: SCT-013-000 Current Transformer (CT) clamps.
- **PCB Fabrication**: The board uses 3.5mm TRS audio jacks for sensor connections.

### 💾 Firmware Upload  
The system uses **ESPHome** for easy integration with Home Assistant.
1. Install the [ESPHome dashboard](https://esphome.io/).
2. Connect your XIAO ESP32-S3 via USB-C.
3. Add a new ESPHome device, and create a New Device Setup yaml file. This will create entries for api, wifi, and ota. Make sure you've already setup a SECRETS file to store your wifi credentials. 
4. Open the provided `.yaml` configuration in the `firmware/` folder. Copy everything starting with captive portal: and paste into the yaml created in the previous step. This ensures your device has a new and unique api and ota entries. Don't use the ones included in the yaml file
5. Click install to compile a binary. Save the binary locally and use ESPHome web to flash the device. After this first flash, the device can be updated over the air (OTA) wirelessly. 
6. Add the device to your **Home Assistant** instance via the Integrations page.

## 🛒 Bill of Materials (BOM)  
| Part             | Description                                    | Purchase Link                                     |
| ---------------- | ---------------------------------------------- | ------------------------------------------------- |
| Microcontroller  | Seeed Studio XIAO ESP32-S3                     | [DigiKey](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/113991114/19285530?s=N4IgTCBcDaIIwFYCcB2AtHOBmJTNwBY0A5AERAF0BfIA)                |
| CT Clamps        | SCT-013-000 (100A/50mA)                        | [DigiKey](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/101990029/5488226)                |
| Burden Resistor  | 20 Ohm (for 3.3V ADC compatibility)            | [DigiKey](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RNCP0603FTD20R0/2240076?s=N4IgTCBcDaIEoDkDCAFADANjQZgGIBUARMNONJfAWgUJAF0BfIA)                |
| Voltage Divider  | 100K Ohm Resistors (x2 per channel)            | [DigiKey](https://www.digikey.com)                |
| Filter Capacitor | 10uF Electrolytic Capacitor                    | [DigiKey](https://www.digikey.com)                |
| Connectors       | 3.5mm TRS Audio Jacks (PCB Mount)              | [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/SJ-3523-SMT-TR/281297?s=N4IgTCBcDaIMIAUC0BmArGFBlAUnAKkgHIAiIAugL5A)                |

## 🎥 Video & More Info  
📺 Watch the full build and calibration process: [YouTube Video](https://youtu.be/54pZV8P7hGM?si=jUmZ82UDNDB7HiG6)  
📄 Read the technical breakdown: [Article on Maker.io](https://www.digikey.com/en/maker/projects/build-a-diy-whole-home-energy-monitor-with-esphome-and-home-assistant/be84610c06894f87a0f75bd443de7992)

> [!CAUTION]
> **Safety Warning**: This project involves installing sensors inside a main utility panel. This should only be performed by individuals comfortable working around high voltage or a licensed electrician.

## 📝 License  
This project is licensed under the **GNU General Public License v3.0**.  

## ❤️ Support  
- Found this helpful? Consider supporting me on [Patreon](https://www.patreon.com/ByteSizedEngineering) or [YouTube Memberships](https://www.youtube.com/@ByteSizedEngineering/join).  
- Follow me on [YouTube](https://www.youtube.com/@ByteSizedEngineering), [Instagram](https://www.instagram.com/bytesizedengineering/), and [GitHub](https://github.com/bytesizedengineering).
