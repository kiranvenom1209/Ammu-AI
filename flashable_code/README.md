
# Ammu AI

Ammu AI is a custom voice assistant built with ESPHome and designed for seamless integration with Home Assistant. It leverages an ESP32-S3 board and incorporates streaming wake word detection, dynamic LED feedback, and dual-microphone support to deliver an interactive smart home experience.

## Features

- **Streaming Wake Word Detection:**  
  Uses the micro_wake_word component to continuously listen for a wake word, so your device stays responsive while conserving power.
- **Voice Assistant Pipeline:**  
  Processes speech-to-text using the asr_mic channel and handles commands, announcements, and more.
- **Dynamic LED Visuals:**  
  Custom LED animations indicate different states such as idle, listening, thinking, replying, error, and more.
- **Dual-Microphone Support:**  
  Separates the ASR (speech-to-text) channel and the wake word channel for clear audio processing.
- **Over-the-Air Updates & API Integration:**  
  Easily update the firmware via OTA and integrate securely with Home Assistant using the API component.

## Hardware Requirements

- **ESP32-S3 Development Board** (e.g., ESP32-S3-DevKitC-1)
- **LED Ring** (WS2812 or similar; 12 LEDs)
- **Dual-Microphone Module** (such as the nabu_microphone which provides separate channels for ASR and wake word)
- **Speaker & Amplifier** (for audio output)
- Additional components: I2C, PSRAM, I2S, etc., as specified in the configuration

## Software Requirements

- [ESPHome](https://esphome.io/) (version 2025.2.0 or later)
- [Home Assistant](https://www.home-assistant.io/) (optional for integration)

## Installation

### 1. Clone the Repository

Clone your repository locally:

```bash
git clone https://github.com/kiranvenom1209/ammuai.git
cd ammuai
2. Configure Your Secrets
Update your secrets.yaml (or add your Wi-Fi credentials directly in the YAML) to include your Wi-Fi SSID and password:

yaml
Copy
wifi_ssid: "YOUR_WIFI_SSID"
wifi_password: "YOUR_WIFI_PASSWORD"
3. Flash the Firmware
Use ESPHome to validate and flash your firmware:

bash
Copy
esphome run ammu.yaml
For the initial flash, connect your device via USB. Once the device is connected to your network, you can update OTA.

Configuration Overview
Global Variables & States:
Global variables control LED animations, device initialization, and voice assistant phases (idle, waiting, listening, thinking, replying, etc.).

API & OTA:
The api: block (and optionally an API password) allows secure integration with Home Assistant, while OTA support makes firmware updates easy.

Audio Pipelines:
The speaker, media_player, and audio_dac components manage audio playback for announcements, timer sounds, and wake word responses.

Voice Assistant & Wake Word:
The voice_assistant component uses the asr_mic (channel_0) for speech-to-text, and the micro_wake_word component (also set to use asr_mic) continuously listens for the wake word. Adjust the use_wake_word setting and model URLs if needed.

LED Effects:
Various scripts and lambda functions control LED effects for different states (waiting, listening, thinking, error, etc.). These provide real-time visual feedback.

Customization
Replacing the Wake Word Sound
Your current configuration references the wake word trigger sound like so:

yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/esphome/home-assistant-voice-pe/raw/dev/sounds/wake_word_triggered.flac
If you have generated a new custom TTS MP3 file and then converted it to FLAC (to match the original format and length), host your new FLAC file (for example, on GitHub) and update the entry:

yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/parayuchetta.flac
Tuning LED Animations & Voice Settings
You can modify the lambda functions under the light: component to adjust the LED animations. Also, tweak the parameters under the voice_assistant block (e.g., noise_suppression_level, auto_gain, etc.) to fine-tune the audio processing.

Troubleshooting
Device Not Discovered:
Check that your device appears on your network (using your router’s DHCP client list) and that mDNS is enabled. If it’s not discovered automatically, you can add it manually via its IP address in the ESPHome dashboard.

API Issues:
Ensure that the api: block is present and that any API passwords are correctly set up. Verify that your Home Assistant integration is configured with the correct API details.

Audio or LED Issues:
Review the logs (via ESPHome’s dashboard or serial output) to troubleshoot any errors related to audio processing or LED control. Double-check your wiring and component connections.

Contributing
If you have ideas for improvements or encounter issues, feel free to open an issue or submit a pull request. Contributions are welcome!

License
This project is licensed under the MIT License. See the LICENSE file for details.

Enjoy your custom voice assistant – Ammu AI – where technology meets home automation in a creative and interactive way!

yaml
Copy

---

Feel free to adjust any section to match your specific setup and creative vision. This README should provide clear guidance and context for anyone looking to understand or contribute to your Ammu AI project.

2/2






You said:
give me entirely in a copy pasteable format
Reasoned for a second
Below is a complete README.md file in a copy-paste-ready format:

markdown
Copy
# Ammu AI

Ammu AI is a custom voice assistant built using ESPHome. It is designed for seamless integration with Home Assistant and features streaming wake word detection, dynamic LED feedback, and dual-microphone support for enhanced speech recognition and wake word responsiveness.

## Features

- **Streaming Wake Word Detection:** Continuously listens for a wake word using the micro_wake_word component.
- **Voice Assistant Pipeline:** Uses a dedicated speech-to-text channel for processing commands and generating responses.
- **Dynamic LED Animations:** Custom LED effects display various states such as idle, waiting, listening, thinking, replying, and error.
- **Dual-Microphone Support:** Separates the ASR (speech-to-text) channel and the wake word channel for optimal performance.
- **Over-the-Air Updates & Secure API:** Easily update firmware via OTA and integrate securely with Home Assistant.

## Hardware Requirements

- **ESP32-S3 Board** (e.g., ESP32-S3-DevKitC-1)
- **LED Ring** (e.g., WS2812 with 12 LEDs)
- **Dual-Microphone Module** (e.g., nabu_microphone providing separate channels for ASR and wake word)
- **Speaker & Amplifier**
- Additional components such as I2C, PSRAM, and I2S as detailed in the configuration.

## Software Requirements

- [ESPHome](https://esphome.io/) (version 2025.2.0 or later)
- [Home Assistant](https://www.home-assistant.io/) (optional, for integration)

## Installation

### 1. Clone the Repository

Clone your repository locally:

```bash
git clone https://github.com/kiranvenom1209/ammuai.git
cd ammuai
2. Configure Your Secrets
Ensure your secrets.yaml (or equivalent) contains your Wi-Fi credentials:

yaml
Copy
wifi_ssid: "YOUR_WIFI_SSID"
wifi_password: "YOUR_WIFI_PASSWORD"
3. Flash the Firmware
Validate and flash your firmware using ESPHome:

bash
Copy
esphome run ammu.yaml
For the initial flash, connect your device via USB. Once the device is connected to your network, you can update it over-the-air (OTA).

Configuration Overview
Global Variables & States:
Global variables are used to control LED animations, device initialization, and voice assistant phases (idle, waiting, listening, thinking, replying, error).

API & OTA:
The API component allows secure integration with Home Assistant, while OTA support simplifies firmware updates.

Audio Pipelines:
Components like speaker, media_player, and audio_dac manage audio playback for announcements and wake word responses.

Voice Assistant & Wake Word:
The voice_assistant component uses the ASR microphone (asr_mic) for speech-to-text, while the micro_wake_word component also uses asr_mic to detect the wake word. Adjust these settings if you prefer a different channel.

LED Effects:
A range of lambda functions under the light: component control various LED animations that reflect device states.

Customization
Replacing the Wake Word Sound
By default, the configuration references the wake word sound file as follows:

yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/esphome/home-assistant-voice-pe/raw/dev/sounds/wake_word_triggered.flac
To use your custom TTS-generated sound:

Convert your MP3 to FLAC (if desired) using a tool like FFmpeg.
Host the new FLAC file (e.g., in your GitHub repository).
Update the file URL. For example:
yaml
Copy
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/parayuchetta.flac
Tuning LED Animations & Voice Settings
You can modify the lambda functions under the light: component to adjust the LED animations. Additionally, tweak parameters in the voice_assistant block (e.g., noise_suppression_level, auto_gain, etc.) to fine-tune audio processing.

Troubleshooting
Device Not Discovered:
Ensure your device is connected to your Wi-Fi network (check your router’s DHCP list) and that mDNS is enabled. If it isn’t auto-discovered, add it manually using its IP address in the ESPHome dashboard.

API Issues:
Confirm the presence of an api: block. If you set an API password, ensure you use the correct password when connecting through Home Assistant.

Audio or LED Issues:
Check the logs via ESPHome’s dashboard or serial output. Verify your wiring and component connections if issues persist.

Contributing
Contributions, improvements, and bug fixes are welcome. Please open an issue or submit a pull request on GitHub.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Enjoy building and customizing Ammu AI — where cutting-edge technology meets creative home automation!
