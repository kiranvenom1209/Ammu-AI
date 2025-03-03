# Ammu AI - Flashable Firmware

Welcome to Ammu AI – a custom voice assistant firmware built with ESPHome for seamless integration with Home Assistant. This folder contains a pre‑built, encrypted binary (`ammuaiencrypted.bin`) that you can flash directly onto your ESP32-S3 device. The firmware features streaming wake word detection, dynamic LED feedback, dual‑microphone support, and many creative features to bring intelligent voice control to your smart home.

## Features

- **Pre‑built, Encrypted Binary:**  
  Flash the provided `ammuaiencrypted.bin` file directly without needing to rebuild from source.
- **Streaming Wake Word Detection:**  
  Continuously listens for a wake word using an optimized wake word detection pipeline.
- **Voice Assistant Pipeline:**  
  Processes speech-to-text via a dedicated microphone channel.
- **Dynamic LED Feedback:**  
  Custom LED animations indicate device states such as idle, listening, thinking, replying, and error.
- **Dual‑Microphone Support:**  
  Separates audio channels for wake word detection and speech recognition for improved accuracy.
- **Secure API & OTA Updates:**  
  Easily update the firmware via OTA and integrate securely with Home Assistant.

## What's Included

- **ammuaiencrypted.bin:**  
  The pre‑built, flashable binary for your ESP32‑S3 device.
- **Source Configuration:**  
  The complete ESPHome YAML configuration used to build the firmware is provided for reference and customization.
- **Custom Sounds:**  
  The firmware uses custom sound files. For example, the wake word trigger sound is now provided via a custom FLAC file hosted in the [custom_sounds](../custom_sounds) folder.

## Hardware Requirements

- **ESP32‑S3 Board** (e.g., ESP32‑S3‑DevKitC‑1)
- **LED Ring** (e.g., WS2812 with 12 LEDs)
- **Dual‑Microphone Module** (e.g., nabu_microphone for separate channels)
- **Speaker & Amplifier**
- Additional components (I2C, PSRAM, I2S, etc.)

## Installation

### Flashing the Firmware

1. **Download the Binary:**  
   Locate the `ammuaiencrypted.bin` file in this folder.

2. **Connect Your Device:**  
   Connect your ESP32‑S3 board to your computer via USB.

3. **Flash the Binary:**  
   Use your preferred flashing tool (such as [esptool](https://github.com/espressif/esptool)) to flash the firmware. For example, using esptool:
   ```bash
   esptool.py --chip esp32s3 --port /dev/ttyUSB0 write_flash 0x10000 ammuaiencrypted.bin
Replace /dev/ttyUSB0 with your device’s port. Adjust the flash address if necessary.

Over‑the‑Air (OTA) Updates
After the initial USB flash, once your device is connected to Wi‑Fi, you can perform OTA updates via ESPHome or Home Assistant without needing a USB cable.

Configuration Overview
Global Variables & Device States:
Global variables manage LED animations, initialization, and voice assistant phases (idle, waiting, listening, thinking, replying, error).

Audio & LED Pipelines:
The firmware handles audio playback for announcements and wake word responses, along with dynamic LED animations that reflect the device’s state.

Voice Assistant & Wake Word:
The voice_assistant component uses the ASR microphone (asr_mic) for speech-to-text while the micro_wake_word component (also using asr_mic) detects the wake word.

API & OTA:
Secure API integration enables communication with Home Assistant, and OTA support streamlines firmware updates.

Customization
Replacing the Wake Word Sound
The firmware references the wake word trigger sound file as follows:

yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/esphome/home-assistant-voice-pe/raw/dev/sounds/wake_word_triggered.flac
To use your custom sound:

Convert your custom TTS-generated file to FLAC (if necessary).
Host the new FLAC file (for example, in the custom_sounds folder).
Update the URL in the YAML configuration:
yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/custom_sounds/parayuchetta.flac
Tuning Other Settings
Adjust the LED animations and voice assistant parameters (like noise suppression and auto gain) in the YAML configuration to fit your environment and preferences.

Troubleshooting
Device Not Discovered:
Ensure the device is connected to Wi‑Fi (check your router’s DHCP list) and that mDNS traffic isn’t blocked. You can also manually add the device by its IP address in the ESPHome dashboard.

API Issues:
Make sure your API block is configured correctly. If using an API password, ensure it is entered correctly in your Home Assistant integration.

Audio or LED Issues:
Check wiring and component connections, and review the ESPHome logs for errors related to audio processing or LED control.

Contributing
Contributions, improvements, and bug fixes are welcome. Please open an issue or submit a pull request on GitHub.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Enjoy your custom voice assistant firmware – Ammu AI – and happy automating!
