# 🚀 Ammu AI – The Ultimate Intelligent Malayalam Assistant

Welcome to **Ammu AI**, the revolutionary Malayalam AI assistant designed to redefine your smart home experience! Drawing inspiration from legendary AI assistants like **Jarvis**, **Friday**, and **Edith**, as well as paying homage to the iconic Malayalam character **Raghavan** from *Gaganachari*, Ammu AI seamlessly blends cutting-edge AI technology with authentic Malayalam cultural nuances.

---

## 🌟 Why Choose Ammu AI?

- **Unparalleled Malayalam Fluency:** Interacts with native-level fluency, capturing the beauty and authenticity of the Malayalam language.
- **Smart Home Command Center:** Effortlessly controls your smart devices, manages routines, and boosts your home's security, ensuring privacy and local data handling.
- **Affordable AI Intelligence:** Designed for maximum efficiency, Ammu AI optimizes API usage, ensuring minimal costs without sacrificing functionality.
- **Cultural and Personalized Experience:** Fully customizable personality and response style, ensuring interactions feel personalized, familiar, and deeply cultural.
- **Unique Wake Word Greeting:** Greets you with the spirited Malayalam phrase **"Parayu Chetta"** ("Hello, buddy!") via a custom high-quality FLAC sound file, enhancing your AI interaction experience.

---

## 🌐 Key Features

### 🗣️ Natural Malayalam Speech Processing
- **Advanced Speech-to-Text & Text-to-Speech:** Powered by Home Assistant Cloud and SobhanaNeural TTS for natural and engaging interactions.
- **Authentic Malayalam Responses:** Crafted responses that deeply resonate with Malayalam cultural and linguistic traditions.

### 🎤 Custom Wake Word & Audio Experience
- **Immersive Activation Sound:** Replaces generic wake sounds with a custom, high-quality Malayalam FLAC audio greeting, creating an engaging interaction experience.

### 🤖 Advanced AI Conversations
- **Context-Aware Conversations:** Utilizes GPT-4o for intelligent, mature, and culturally relevant interactions.
- **Tailored Personality:** Set as a knowledgeable, friendly 28-year-old AI assistant, ensuring relatable and enjoyable conversations.

### 📸 LLM Vision Integration
- **Smart Image Analysis:** OpenAI Vision API integration for real-time CCTV image analysis, object recognition, and text interpretation to enhance security and home automation.

### 🔒 Privacy-First Local Processing
- **Local Data Handling:** Prioritizes local processing to safeguard your privacy, seamlessly integrated with Home Assistant.

---

## 📖 Step-by-Step Installation & Setup Guide

### 1. Prepare Home Assistant
- [Install Home Assistant OS](https://www.home-assistant.io/installation/)
- Update your Home Assistant to the latest version.

### 2. Configure Cloud & Voice Pipelines
- [Subscribe to Home Assistant Cloud (Nabu Casa)](https://www.nabucasa.com)
- Set up the Ammu pipeline:
  - Navigate to `Settings → Voice Assistants → Pipelines`
  - Language: Malayalam (ml-IN)
  - Speech-to-Text: Home Assistant Cloud STT
  - Text-to-Speech: SobhanaNeural TTS

### 3. Integrate OpenAI & LLM Vision
- Install and configure [OpenAI Integration](https://www.home-assistant.io/integrations/openai_conversation/)
  - Recommended model: GPT-4o-2024-11-20
  - Max Tokens: 2400 | Top P: 0.9 | Temperature: 0.7
- Install and configure [LLM Vision with OpenAI](https://www.home-assistant.io/integrations/openai_image_processing/)

### 4. Custom Wake Word
- [Install OpenWakeWord](https://github.com/dscripka/openWakeWord/tree/main)
- Deploy Ammu’s custom wake word model [`ammu.tflite`](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite)

### 5. Flash Custom Firmware
- Download pre-built binary [`ammuaiencrypted.bin`](https://github.com/kiranvenom1209/ammuai/blob/main/flashable_code/ammuaiencrypted.bin)
- Flash via [ESPHome](https://esphome.io/guides/getting_started_hassio.html)
- OTA updates supported for easy maintenance

### 6. Activate Ammu AI
- Select Ammu pipeline: `Settings → Voice Assistants → Pipelines`
- Activate by simply saying **"Ammu"**

---

## 🤖 Local LLM Fine-Tuning Support

Fully supports local fine-tuning of open-source LLM models like DeepSeek, Ollama, and more:

- **[Local LLM Dataset](local_llm/README.md)**
  - Training dataset (`ammu_chat_finetune.jsonl.gz`)
  - Validation dataset (`ammu_chat_validation.jsonl`)

Detailed, step-by-step instructions provided for each supported local LLM.

---

## 🎨 Customization & Future Roadmap

- **Personalize Ammu:** Edit prompts and response styles via customizable files.
- **Technical Enhancements:** Planned future capabilities include advanced local LLM processing, expanded dialect support, enhanced image recognition, and context-aware interactions.

---

## 🙌 Contributors

- **Kiran Karthikeyan Achari:** Visionary founder, passionate about blending technology with Malayalam cultural heritage.
- **Danny Sneham:** Key technical collaborator, instrumental in developing Ammu’s advanced AI capabilities.

## 📜 License & Support

Released under the [MIT License](LICENSE). Contributions and issue reports are welcomed via the [GitHub Repository](https://github.com/kiranvenom1209/ammuai).

---

Dive into the innovative world of Ammu AI and experience intelligent, culturally-rich home automation like never before. Start your journey today! 🚀🌟

