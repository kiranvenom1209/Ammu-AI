# Ammu AI - The Ultimate Intelligent Malayalam Assistant

Welcome to **Ammu AI** – the first fully intelligent Malayalam AI assistant designed to revolutionize your smart home experience.  Inspired by legendary assistants like **Jarvis**, **Friday**, and **Edith**, and paying homage to the iconic character **Raghavan** from *Gaganachari*, Ammu AI brings cutting-edge technology and local flavor together in one powerful package.

---

## Why Ammu AI?

*   **Unmatched Malayalam Fluency:** Built from the ground up to understand and converse in impeccable Malayalam, Ammu AI provides an interaction that feels truly natural and culturally rich.
*   **Smart Home Command Center:** Seamlessly integrated with Home Assistant, Ammu AI controls your smart devices, automates routines, and enhances home security—all while keeping your data private and local.
*   **Cost-Effective Intelligence:** Enjoy advanced AI capabilities at a very low cost, with efficient API usage ensuring that monthly expenses remain minimal.
*   **Cultural Relevance & Personalization:** With a custom base prompt and dedicated function files, you can tailor Ammu AI's personality to be as friendly, witty, and culturally attuned as you want.
*   **Custom Wake Word Response:** Instead of a generic chime, Ammu AI greets you with the spirited Malayalam phrase **"Parayu Chetta"** (roughly meaning "Hello buddy, how can I help you?"). This distinctive greeting is delivered via a custom FLAC sound file, making every activation a unique experience.

---

## Key Features

### 🗣️ Natural Malayalam Speech Processing

*   **Fluent Communication:** Leverages advanced speech-to-text (STT) and text-to-speech (TTS) systems (powered by Home Assistant Cloud STT and SobhanaNeural TTS) to ensure natural, engaging interactions.
*   **Cultural Authenticity:** Designed to honor Malayalam linguistic nuances, providing responses that resonate with local culture.

### 🎤 Custom Wake Word & Audio Experience

*   **Custom Activation Sound:** When the wake word is detected, Ammu AI plays a custom sound – **"Parayu Chetta"** – replacing a simple chime with a friendly call-to-action.
*   **Optimized Audio Format:** The custom sound is stored as a FLAC file (see [custom_sounds/parayuchetta.flac](https://github.com/kiranvenom1209/ammuai/blob/main/custom_sounds/parayuchetta.flac)) to ensure high-quality, lossless playback with minimal overhead.

### 🤖 Advanced AI-Powered Conversations

*   **Extended OpenAI Conversations:** Equipped with a GPT‑4o–based conversational pipeline for intelligent, context-aware, and mature responses.
*   **Custom Personality:** A specially tailored base prompt sets Ammu's personality as a friendly and knowledgeable 28-year-old assistant.

### 📸 LLM Vision – Intelligent Image Analysis

*   **Smart Vision Capabilities:** Integrated with OpenAI's Vision API to analyze images from your CCTV feeds, recognize objects, and even read text—all to enhance your home security and automation.

### 🔒 Privacy & Local Processing

*   **Data Security First:** All processing is done locally where possible, ensuring minimal dependency on cloud services and maximum privacy.
*   **Seamless Integration:** With secure API and OTA support, Ammu AI is designed to integrate effortlessly with Home Assistant.

---

## Installation & Setup Guide

### 1. Prepare Your Home Assistant

1.  **Install Home Assistant OS:** Follow the official guide on [Home Assistant Installation](https://www.home-assistant.io/installation/).
2.  **Update to the Latest Version:** Ensure your installation is running the latest version to support all integrations.

### 2. Configure Home Assistant Cloud & Pipelines

1.  **Subscribe to Home Assistant Cloud (Nabu Casa):** This provides enhanced STT/TTS services.
2.  **Set Up the Ammu Pipeline:**
    *   Navigate to **Settings → Voice Assistants → Pipelines**.
    *   Create a new pipeline named **Ammu**.
    *   Set the language to **Malayalam (ml-IN)**.
    *   Choose **Home Assistant Cloud STT** and **TTS (SobhanaNeural)**.

### 3. Extended OpenAI Conversation & LLM Vision

1.  **Extended OpenAI Conversation:**
    *   Install via **Settings → Devices & Services → Add Integration** and configure with your OpenAI API key.
    *   Recommended settings:
        *   **Model:** `gpt-4o-2024-11-20`
        *   **Max Tokens:** `2400`
        *   **Top P:** `0.9`
        *   **Temperature:** `0.7`
2.  **LLM Vision Integration:**
    *   Add the integration from **Settings → Devices & Services**, using OpenAI as the provider.

### 4. Set Up OpenWakeWord & Custom Wake Word Model

1.  **Install OpenWakeWord:** Follow the instructions on the [OpenWakeWord GitHub page](https://github.com/dscripka/openWakeWord/tree/main).
2.  **Download the Ammu Wake Word Model:** Retrieve it from [custom_wake_word/ammu.tflite](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite) and place it in your designated Home Assistant folder.

### 5. Flash the Custom Firmware

1.  **Download the Pre-built Binary:** Get `ammuaiencrypted.bin` from the [flashable_code folder](https://github.com/kiranvenom1209/ammuai/blob/main/flashable_code/ammuaiencrypted.bin).
2.  **Flash via ESPHome:** Ensure your Wi-Fi credentials are set in `secrets.yaml`, then flash using your preferred method:

    ```bash
    esphome run ammu.yaml
    ```

    **OTA Updates:**
    Once your device is connected to Wi-Fi, you can update the firmware over the air using the ESPHome dashboard.

### 6. Activate Ammu AI

*   **Select the Ammu Pipeline:** In Home Assistant, choose the Ammu pipeline from Settings → Voice Assistants → Pipelines.
*   **Speak to Activate:** Simply say "Ammu" to trigger the wake word and start interacting with your assistant.

## Customization & Future Scope

### Custom Audio Files & Prompts

*   **Custom Wake Word Sound:** Our custom sound file, `parayuchetta.flac`, replaces the standard chime. It plays the Malayalam phrase "Parayu Chetta" meaning "Hello buddy, how can I help you?".  To change it, update the URL in your YAML under the media files section.
*   **Editable Base Prompt & Functions:** Customize Ammu AI's personality by modifying `ammu_baseprompt.txt` and `ammu_functions.txt`. These files define how Ammu responds, controls devices, and interacts in Malayalam.

### Technical Roadmap & Future Enhancements

*   **Local LLM Capabilities:** Future versions may run more AI processing directly on the device, reducing reliance on cloud services.
*   **Enhanced Vision Integration:** Advanced image recognition and real-time security analysis could be integrated for smarter home automation.
*   **User-Customizable Voice Profiles:** Allow users to upload and configure their own voice prompts for a more personalized experience.
*   **Expanded Language & Dialect Support:** While Ammu AI is optimized for Malayalam, additional language packs or dialects could be integrated in the future.
* **Context-Aware Interactions:** Future enhancements may include dynamic response based on ambient conditions, time of day, or user behavior.

## Credits

*   **Kiran Karthikeyan Achari:** The visionary creator of Ammu AI. His passion for merging technology with cultural authenticity is the driving force behind this project.
*   **Danny Sneham:** A key collaborator whose technical expertise and creative insights have been crucial in developing Ammu AI's advanced features.

## License & Support

This project is released under the MIT License. For support, contributions, or to report issues, please visit the GitHub repository and open an issue or submit a pull request.

---

Experience the next level of intelligent, culturally attuned home automation with Ammu AI – the ultimate Malayalam AI assistant that truly understands you. Enjoy customizing and automating your home with a touch of local flavor and cutting-edge technology!
