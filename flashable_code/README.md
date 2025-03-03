# Ammu AI - Flashable Firmware

Welcome to Ammu AI – a custom voice assistant firmware built with ESPHome for integration with Home Assistant. This folder contains a pre-built, encrypted binary (`ammuaiencrypted.bin`) that you can flash directly onto your ESP32-S3 device. The firmware features streaming wake word detection, dynamic LED feedback, dual-microphone support, and a host of creative features to bring intelligent voice control to your smart home.

## Features

- **Pre-built, Encrypted Binary:**  
  Flash the provided `ammuaiencrypted.bin` file directly without needing to rebuild from source.
- **Streaming Wake Word Detection:**  
  Continuously listens for a wake word using an optimized wake word detection pipeline.
- **Voice Assistant Pipeline:**  
  Processes speech-to-text using dedicated microphone channels.
- **Dynamic LED Feedback:**  
  Customizable LED animations indicate device states (idle, listening, thinking, replying, error, etc.).
- **Dual-Microphone Support:**  
  Separates the audio channels for wake word detection and speech recognition for improved accuracy.
- **Seamless Integration:**  
  Secure OTA and API support make it easy to update and integrate with Home Assistant.

## What's Included

- **ammuaiencrypted.bin:**  
  The pre-built, flashable binary for your ESP32-S3 device.
- **Source Configuration:**  
  The complete ESPHome YAML configuration is available for reference and customization.

## Hardware Requirements

- **ESP32-S3 Board** (e.g., ESP32-S3-DevKitC-1)
- **LED Ring** (e.g., WS2812 with 12 LEDs)
- **Dual-Microphone Module** (for separate wake word and speech-to-text channels)
- **Speaker & Amplifier**
- Additional supporting components such as I2C, PSRAM, I2S, etc.

## Installation

### Flashing the Firmware

1. **Download the Binary:**  
   Navigate to this folder and locate `ammuaiencrypted.bin`.

2. **Connect Your Device:**  
   Connect your ESP32-S3 board to your computer using a USB cable.

3. **Flash the Binary:**  
   Use your preferred flashing tool (for example, [esptool](https://github.com/espressif/esptool)) to flash the firmware. For instance, using esptool:
   
   ```bash
   esptool.py --chip esp32s3 --port /dev/ttyUSB0 write_flash 0x10000 ammuaiencrypted.bin
Replace /dev/ttyUSB0 with the correct port for your device. (If necessary, adjust the flash address as required by your board.)

Over-the-Air (OTA) Updates
After the initial USB flash, once your device is connected to Wi‑Fi, you can perform OTA updates via ESPHome or Home Assistant without needing a USB cable.

Configuration Overview
Global Variables & Device States:
The configuration manages various global states (LED animations, initialization, voice assistant phases, etc.) using global variables.

Audio & LED Pipelines:
The firmware is built to handle audio pipelines for wake word detection and TTS responses, as well as LED animations that visually represent the device’s state.

Voice Assistant & Wake Word:
The voice assistant is configured to use the asr_mic channel for speech recognition, while the micro wake word component listens for the wake word.

API & OTA:
Secure API integration allows the firmware to communicate with Home Assistant, while OTA updates streamline firmware maintenance.

Customization
Replacing the Wake Word Sound
By default, the firmware uses a wake word sound referenced in the YAML. If you wish to update it with a custom file, perform the following steps:

Convert your custom TTS file (e.g., an MP3 file) to FLAC using a tool like FFmpeg (if necessary) to match the original file format.
Host the new FLAC file (for example, in this repository or on another server).
Update the file URL in the YAML configuration under the media files section. For instance, change:
yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/esphome/home-assistant-voice-pe/raw/dev/sounds/wake_word_triggered.flac
to:
yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/flashable_code/your_custom_file.flac
Tuning Other Settings
You can adjust LED animations, voice assistant parameters (noise suppression, auto gain, etc.), and other settings by modifying the provided YAML configuration. This allows you to personalize your device's behavior to best suit your environment.

Troubleshooting
Device Not Discovered:
Ensure your device is connected to your Wi‑Fi network (check your router’s DHCP list) and that mDNS traffic is not blocked. You can also manually add the device by its IP address via the ESPHome dashboard.

API Issues:
Confirm the API block is present and configured correctly. If you set an API password, ensure it is entered properly in your Home Assistant integration.

Audio/LED Problems:
Verify wiring and component connections. Check the ESPHome logs for any errors related to audio processing or LED control.

Contributing
Contributions and improvements are welcome! If you encounter any issues or have suggestions, please open an issue or submit a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for more details.

Enjoy your custom voice assistant firmware – Ammu AI – and happy automating!
