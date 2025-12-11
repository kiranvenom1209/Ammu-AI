# Ammu AI Editable YAML Configuration

This folder holds the full ESPHome YAML configuration for Ammu AI on the ESP32‑S3 platform. Customize it, compile with ESPHome, and flash it to your device or update it over the air. The config targets **Home Assistant 2024.12+ Assist pipelines** and expects an encrypted ESPHome API connection.

## Overview

Ammu AI combines streaming wake-word detection, dynamic LED feedback, dual-microphone support, and secure API connectivity. Every aspect—from network settings to LED animations—is customizable in the YAML.

## Key features

- **Fully editable YAML**: Adjust LED animations, voice assistant phases, and audio pipelines.
- **Streaming wake-word detection**: Always listening for activation without sacrificing performance (pipeline selection handled in HA).
- **Dynamic LED visuals**: Animations that reflect idle, listening, thinking, replying, or error states.
- **Dual-microphone support**: Separate channels for wake-word detection and speech recognition.
- **Secure API & OTA updates**: Home Assistant integration with OTA firmware updates.
- **Customizable audio assets**: Swap default sounds with your own recordings.

## Hardware requirements

- ESP32‑S3 board (e.g., ESP32-S3-DevKitC-1)
- LED ring (e.g., WS2812 with 12 LEDs)
- Dual‑microphone module (e.g., nabu_microphone)
- Speaker and amplifier
- Supporting peripherals (I2C, PSRAM, I2S, etc.)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/kiranvenom1209/ammuai.git
   cd ammuai/Yaml
   ```
2. **Edit the YAML file**
   Open the YAML in your editor and adjust network settings, hardware pins, and assistant behavior.
3. **Compile and flash**
   ```bash
   esphome run your_configuration.yaml
   ```
   Replace `your_configuration.yaml` with the actual filename.
4. **Pair with Home Assistant Assist**
   - Add the device to Home Assistant and paste the generated ESPHome API encryption key into `packages/secrets.yaml`.
   - Ensure the Assist pipeline named "Ammu Malayalam" is set as default or mapped to the device in `Settings → Voice Assistants → Pipelines`.
5. **OTA updates**
   After the device is on Wi‑Fi, use the ESPHome dashboard for over‑the‑air updates.

## Customization tips

- **Custom audio files**: Host your FLAC wake word audio and update the sound URL in the configuration.
- **Tuning LED effects**: Modify the lambda effects under the `light` component for different colors, speeds, and patterns.
- **Voice assistant settings**: Adjust `noise_suppression_level`, `auto_gain`, and `volume_multiplier` under `voice_assistant` for your environment.

## Troubleshooting

- **Device not showing up**: Verify Wi‑Fi connectivity, ensure mDNS is allowed, or add the device by IP in ESPHome.
- **Compilation errors**: Run ESPHome validation and check YAML indentation and lambdas.
- **Audio/LED issues**: Inspect ESPHome logs and wiring.

## Contributing

Contributions and feature suggestions are welcome. Open an issue or submit a pull request on GitHub.

## License

This project is licensed under the MIT License. See the [LICENSE](../LICENSE) file for details.
