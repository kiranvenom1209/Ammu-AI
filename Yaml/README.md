# Ammu AI Editable YAML Configuration

Welcome to the Ammu AI YAML configuration repository! This file contains the full, editable ESPHome YAML configuration for Ammu AI – our custom voice assistant firmware designed for the ESP32-S3 platform. Customize it to your heart’s content, then compile and flash it to your device or update it over the air!

---

## Overview

Ammu AI combines state-of-the-art streaming wake word detection, dynamic LED feedback, dual-microphone support, and secure API connectivity to create an engaging and interactive voice assistant experience. This configuration file lets you tailor every aspect of the firmware—from network settings and audio pipelines to LED animations and voice assistant behavior.

---

## Key Features

- **Fully Editable YAML:**  
  Customize settings such as LED animations, voice assistant phases, and audio pipelines easily.

- **Streaming Wake Word Detection:**  
  Continuously listens for a wake word to activate the voice assistant without sacrificing performance.

- **Dynamic LED Visuals:**  
  Enjoy creative LED animations that reflect the device’s state—idle, listening, thinking, replying, or in error.

- **Dual-Microphone Support:**  
  Uses separate channels for wake word detection and speech recognition, ensuring clear command processing.

- **Secure API & OTA Updates:**  
  Seamless integration with Home Assistant via a secure API, plus over‑the‑air firmware updates for hassle‑free maintenance.

- **Customizable Audio Assets:**  
  Easily swap out default sounds with your own custom recordings to personalize your device.

---

## Hardware Requirements

- **ESP32-S3 Board** (e.g., ESP32-S3-DevKitC-1)  
- **LED Ring** (e.g., WS2812 with 12 LEDs)  
- **Dual-Microphone Module** (such as nabu_microphone for separate ASR and wake word channels)  
- **Speaker & Amplifier**  
- Other peripherals: I2C, PSRAM, I2S, etc.

---

## Installation

### 1. Clone the Repository

Clone this repository and navigate to the `Yaml` folder:

```bash
git clone https://github.com/kiranvenom1209/ammuai.git
cd ammuai/Yaml
2. Edit the YAML File
Open the YAML file in your favorite editor (VSCode, Sublime Text, etc.) and adjust the configuration to suit your network and hardware setup. You can modify:

Wi‑Fi Credentials (via secrets)
LED Animations and timings
Voice Assistant Settings (microphone channels, wake word models, etc.)
Custom Sound URLs (e.g., replace the default wake word sound)
3. Compile and Flash
Use ESPHome to validate and compile your configuration. Then flash the firmware to your device using USB for the first time:

bash
Copy
esphome run your_configuration.yaml
Replace your_configuration.yaml with the actual filename if it differs.

4. OTA Updates
Once the device is connected to your Wi‑Fi, you can perform OTA updates directly from the ESPHome dashboard—no USB required!

Customization Tips
Custom Audio Files
If you’ve generated a new custom wake word file, convert it to FLAC (if necessary) and host it (e.g., in your repository). Then update the sound file URL in the configuration:

yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/flashable_code/your_custom_sound.flac
Tuning LED Effects
The configuration uses a variety of lambda functions under the light: component to create dynamic LED effects. Feel free to modify these lambdas to experiment with different colors, speeds, and patterns.

Voice Assistant Settings
Adjust parameters like noise_suppression_level, auto_gain, and volume_multiplier under the voice_assistant block to optimize speech recognition and audio output based on your environment.

Troubleshooting
Device Not Showing Up:
• Verify your device’s Wi‑Fi connectivity (check your router’s DHCP list).
• Ensure mDNS is not blocked on your network.
• Manually add the device by its IP address via the ESPHome dashboard if needed.

Compilation Errors:
• Use the ESPHome validation tool to check for YAML syntax errors.
• Double-check indentation and lambda function formatting.

Audio/LED Issues:
• Review ESPHome logs for error messages.
• Confirm that all wiring and component connections are secure and correct.

Contributing
Contributions, improvements, and feature suggestions are welcome! Please open an issue or submit a pull request on GitHub.

License
This project is licensed under the MIT License. See the LICENSE file for more details.

Enjoy customizing and deploying Ammu AI – where cutting-edge voice assistant technology meets creative home automation!

yaml
Copy

