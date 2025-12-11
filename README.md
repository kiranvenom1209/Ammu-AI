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

### 2. Configure Cloud & Assist Pipelines (Home Assistant 2024.12+)
- [Subscribe to Home Assistant Cloud (Nabu Casa)](https://www.nabucasa.com)
- Create an Assist pipeline for Ammu:
  - Navigate to `Settings → Voice Assistants → Pipelines`
  - Add a pipeline named **"Ammu Malayalam"** (matches `assist_pipeline` in `ammu.yaml`)
  - Language: Malayalam (ml-IN)
  - Speech-to-Text: Home Assistant Cloud STT (ml-IN)
  - Text-to-Speech: Microsoft **SobhanaNeural** (ml-IN)
  - Wake word: enabled via ESPHome voice assistant (no extra HA wake word needed)
  - Set this pipeline as the default for the device or area

### 3. Integrate LLM Conversation (OpenAI or Google AI Studio) & Vision
- **Option A: OpenAI Conversation** ([integration docs](https://www.home-assistant.io/integrations/openai_conversation/))
  - Model: GPT-4o or GPT-4o-mini
  - Parameters: Max Tokens 2400 | Top P 0.9 | Temperature 0.7
  - Prompt: upload `ammu_baseprompt.txt`
  - Functions/Tools: upload `ammu_functions.txt` to enable Home Assistant service calls
- **Option B: Google AI Studio (Gemini)** ([Google Generative AI Conversation](https://www.home-assistant.io/integrations/google_generative_ai_conversation/))
  - Create an API key in [Google AI Studio](https://aistudio.google.com/app/apikey) and set it in Home Assistant
  - Model: `gemini-1.5-flash` for fastest responses or `gemini-1.5-pro` for higher quality
  - Temperature: start around 0.7 and tune to preference
  - Prompt: paste the contents of `ammu_baseprompt.txt`
  - Tools: add `ammu_functions.txt` functions so Gemini can call Home Assistant services
- **Vision (optional, OpenAI today)**: configure [LLM Vision with OpenAI](https://www.home-assistant.io/integrations/openai_image_processing/) for CCTV/object detection

### 4. Custom Wake Word
- [Install OpenWakeWord](https://github.com/dscripka/openWakeWord/tree/main)
- Deploy Ammu’s custom wake word model [`ammu.tflite`](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite)

### 5. Flash Custom Firmware
- Download pre-built binary [`ammuaiencrypted.bin`](https://github.com/kiranvenom1209/ammuai/blob/main/flashable_code/ammuaiencrypted.bin)
- When adding the device to Home Assistant, copy the generated **ESPHome API encryption key** into `packages/secrets.yaml`
- Flash via [ESPHome](https://esphome.io/guides/getting_started_hassio.html) and set the Assist pipeline to "Ammu Malayalam"
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

# Meet the Creators

## Kiran Karthikeyan Achari  
[![Kiran's GitHub](https://img.shields.io/badge/GitHub-kiranvenom1209-181717?style=flat&logo=github)](https://github.com/kiranvenom1209)

Kiran is the visionary founder behind Ammu AI—a groundbreaking project that fuses cutting-edge artificial intelligence with rich Malayalam cultural heritage. His passion for blending technology with tradition has led him to design innovative smart home solutions that are both functional and culturally resonant.

**Key Strengths:**
- **Innovative Product Design:** Crafts solutions that combine modern AI with cultural authenticity.
- **Advanced AI & Machine Learning:** Deep expertise in natural language processing and context-aware AI.
- **Leadership & Vision:** Drives projects from concept to reality with strategic foresight and creativity.
- **Community & Collaboration:** Actively contributes to open-source projects and mentors emerging tech talents.

---

## Danny Sneham  
[![Danny's GitHub](https://img.shields.io/badge/GitHub-FatCat--IOT-181717?style=flat&logo=github)](https://github.com/FatCat-IOT)

Danny is the technical mastermind behind Ammu AI's robust integration capabilities. With a sharp focus on IoT, firmware, and hardware-software synergy, he turns complex technical challenges into elegant solutions. His commitment to precision and quality ensures that every smart home interaction is smooth and reliable.

**Key Strengths:**
- **Expertise in IoT & Firmware Development:** Translates intricate hardware demands into streamlined software experiences.
- **Problem-Solving & Innovation:** Tackles complex issues with creative, resourceful solutions.
- **Quality & Scalability:** Designs systems that are both robust and scalable, ensuring long-term reliability.
- **Collaborative Spirit:** Works seamlessly with cross-functional teams to drive project success and foster innovation.

---

Together, Kiran and Danny combine their diverse talents and shared passion for innovation to create transformative tech solutions that set new standards in AI-assisted smart home automation. Their collaboration not only highlights their individual strengths but also demonstrates the power of teamwork in revolutionizing the way we interact with technology.


## 📜 License & Support

Released under the [MIT License](LICENSE). Contributions and issue reports are welcomed via the [GitHub Repository](https://github.com/kiranvenom1209/ammuai).

## 📤 Publishing your changes to GitHub
This repository currently has no Git remotes configured. To publish updates on GitHub, add your remote and push the `work` branch:

1. Verify whether a remote already exists: `git remote -v` (no output means none).
2. Add your GitHub remote, for example: `git remote add origin git@github.com:<your-username>/Ammu-AI.git`.
3. Push this branch: `git push -u origin work`.
4. Open a pull request from the `work` branch in your GitHub repository.

---

Dive into the innovative world of Ammu AI and experience intelligent, culturally-rich home automation like never before. Start your journey today! 🚀🌟

