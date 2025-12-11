# Ammu AI - ESPHome Packages

This directory contains the ESPHome packages that make up the Ammu AI configuration. Using packages keeps the configuration modular, readable, and maintainable.

## Package overview

- **`wifi.yaml`** – Wi‑Fi connection, OTA updates, and the encrypted ESPHome API used by the Assist pipeline. Credentials should live in `packages/secrets.yaml` (copy from `secrets.example.yaml`).
- **`sensors.yaml`** – Placeholder sensor definitions. Replace these with the sensors that match your hardware.
- **`voice_assistant.yaml`** – Core `voice_assistant` component settings, including microphone/speaker IDs, VAD tuning, Assist pipeline selection, and event handlers.
- **`audio.yaml`** – I2S audio interface wiring for microphones and speakers. Update the pin numbers to match your board.

## How packages are combined

The main `ammu.yaml` includes each package so ESPHome can treat them as a single configuration:

```yaml
packages:
  wifi: !include packages/wifi.yaml
  sensors: !include packages/sensors.yaml
  voice_assistant: !include packages/voice_assistant.yaml
  audio: !include packages/audio.yaml
  # OpenAI and Assist pipeline are configured in Home Assistant 2024.12+
```

## Customization checklist

1. **Create secrets** – Copy `packages/secrets.example.yaml` to `packages/secrets.yaml` and fill in your Wi‑Fi, OTA, API encryption key, and wake-word media URL. The real file is ignored by Git.
2. **Update pin mappings** – Adjust pin numbers in `audio.yaml` (and any sensor definitions) to match your ESP32‑S3 wiring.
3. **Define sensors** – Replace the placeholders in `sensors.yaml` with the sensors you actually use.
4. **Tune the assistant** – Modify VAD thresholds, gain, Assist pipeline name, and other options in `voice_assistant.yaml` to suit your environment.
5. **Personalize prompts** – Edit `ammu_baseprompt.txt` and add or adjust functions in `ammu_functions.txt` to customize Ammu's behavior. Upload these to your Home Assistant LLM provider (OpenAI or Google AI Studio/Gemini) so Assist can call services safely.

## Adding new functionality

Create additional package files in this directory and reference them from `ammu.yaml` with `!include`. This keeps the configuration organized as the project grows.
