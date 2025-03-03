# Ammu AI - ESPHome Packages

This directory contains the ESPHome packages that make up the Ammu AI configuration.  Using packages promotes modularity, readability, and maintainability.  Each file focuses on a specific aspect of the system.

## Package Structure

The `packages` directory contains the following YAML files:

*   **`wifi.yaml`:**  Handles Wi-Fi connection and OTA (Over-The-Air) updates.  This includes setting the SSID, password, and optionally a static IP address.  Sensitive credentials (SSID, password, OTA password) should be stored in `secrets.yaml`.
*   **`sensors.yaml`:**  Defines all the sensors used by Ammu AI.  This could include temperature sensors, humidity sensors, binary sensors (e.g., for detecting voice command activity), and any other sensors relevant to your setup.  You will need to adapt this file to your specific hardware.
*   **`voice_assistant.yaml`:**  Contains the core configuration for the ESPHome `voice_assistant` component.  This includes settings for the microphone, speaker, Voice Activity Detection (VAD), noise suppression, and event handlers (`on_wake_word_detected`, `on_voice_command_start`, etc.).  This is where the main logic for interacting with Home Assistant's voice assistant pipeline resides.
*   **`audio.yaml`:** Configures the I2S audio interface, microphone, and speaker. This includes setting the appropriate pin numbers for your specific hardware (e.g., I2S DAC, INMP441 microphone). You *must* adapt the pin numbers to match your board.
*   **`openai.yaml`:**  This file sets up the integration with OpenAI's API for natural language processing. It includes the configuration for the `conversation` agent, including your API key (stored in `secrets.yaml`), the chosen model (e.g., `gpt-4o`), and the base prompt (loaded from `ammu_baseprompt.txt`).

## How Packages Work

The main `ammu.yaml` file uses the `packages:` directive to include these individual YAML files:

```yaml
packages:
  wifi: !include packages/wifi.yaml
  sensors: !include packages/sensors.yaml
  voice_assistant: !include packages/voice_assistant.yaml
  audio: !include packages/audio.yaml
  openai: !include packages/openai.yaml
This effectively combines all the separate files into a single configuration that ESPHome can understand, but it keeps the code much better organized than having everything in one giant file.

Customization
To customize Ammu AI for your specific setup, you will need to:

Edit secrets.yaml: Create a secrets.yaml file (in the same directory as ammu.yaml) and add your Wi-Fi credentials, OTA password, and OpenAI API key. Never commit your secrets.yaml file to a public repository. An example secrets.yaml.example is provided to guide you.
Modify Pin Numbers: In audio.yaml (and potentially sensors.yaml), change the pin numbers to match the wiring of your ESP32-S3 board and connected peripherals (microphone, speaker, sensors).
Add/Configure Sensors: In sensors.yaml, define any sensors you want to use with Ammu AI.
Adjust Voice Assistant Settings: In voice_assistant.yaml, fine-tune the VAD threshold, noise suppression, and other settings to optimize performance in your environment.
Customize the Base Prompt: Edit ammu_baseprompt.txt (located in the main directory alongside ammu.yaml) to refine Ammu AI's personality and response style.
Add custom functions in ammu_functions.txt.
Adding New Packages
If you want to add more functionality to Ammu AI, you can create additional package files within the packages directory and include them in ammu.yaml using the !include directive. This keeps your configuration modular and easy to manage.
