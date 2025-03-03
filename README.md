# Ammu AI - The First Intelligent Malayalam AI Assistant

## 🌟 Introduction
Ammu AI is the first intelligent Malayalam AI assistant, designed to provide seamless interaction in fluent, modern Malayalam. Inspired by **Raghavan** from the *Gaganachari* movie and legendary AI assistants like **Jarvis, Friday, and Edith** from the Marvel universe, Ammu is a blend of cutting-edge AI technology and cultural relevance.

Developed by **Kiran Karthikeyan Achari** and **Danny Sneham**, Ammu AI is deeply integrated with Home Assistant, offering advanced voice control, smart automation, and an interactive assistant that truly understands and responds in native Malayalam.

## 🔥 Features
### 🗣️ **Fluent and Natural Malayalam Speech Processing**
- Ammu speaks **grammatically perfect** Malayalam with a natural conversational tone.
- Uses **Home Assistant Cloud STT (ml-IN)** for **speech-to-text**.
- Replies with **TTS (ml-IN) SobhanaNeural**, ensuring natural intonation.

### 🎤 **Custom Wake Word - "Ammu"**
- Uses a **custom TensorFlow Lite (TFLite) wake word model**.
- Optimized for Home Assistant using **OpenWakeWord**.
- Download the **wake word model** from:  
  🔗 [Custom Wake Word - Ammu](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite)

### 🤖 **AI-Powered Conversations**
- Runs on **Extended OpenAI Conversation**.
- Uses **GPT-4o** with fine-tuned configurations to ensure intelligent, natural responses.
- Custom base prompt optimizes Ammu for a **28-year-old mature assistant tone**.
- Monthly **OpenAI API cost stays under €5 even for heavy users**.

### 📸 **LLM Vision - AI-Based Image Analysis**
- Ammu can analyze images using **Home Assistant LLM Vision**.
- Uses OpenAI’s **Vision API** for smart home security and automation.
- Ideal for recognizing objects, people, and text from **CCTV feeds**.

### 🔥 **Seamless Smart Home Integration**
- Works **exclusively with Home Assistant**.
- Fully controls **lights, appliances, security cameras, and automation scripts**.
- Custom firmware ensures **optimized performance** on ESP-based smart home devices.

### 🔐 **Privacy-Focused & Local Execution**
- No **unnecessary cloud processing**—everything runs **locally** unless API calls are required.
- Custom firmware ensures **maximum data security** and **minimal external dependencies**.

---

## 🛠️ **Installation Guide**
This guide will walk you through the installation and setup of Ammu AI, ensuring a smooth experience.

### **🔹 Step 1: Setup Home Assistant**
1. Install **Home Assistant OS** on a **Raspberry Pi, Intel NUC, or Home Server**.
2. Follow the official guide:  
   🔗 [Home Assistant Installation Guide](https://www.home-assistant.io/installation/)
3. Ensure your Home Assistant is updated to the latest version.

### **🔹 Step 2: Enable Home Assistant Cloud & Assistant Pipelines**
1. Subscribe to **Home Assistant Cloud** via **Nabu Casa**:  
   🔗 [Home Assistant Cloud](https://www.nabucasa.com/)
2. In Home Assistant, go to **Settings → Voice Assistants → Pipelines**.
3. Create a new pipeline and name it **Ammu**.
4. Set **Malayalam (ml-IN)** as the preferred language.
5. Choose **Home Assistant Cloud STT** and **TTS (SobhanaNeural)**.

### **🔹 Step 3: Install Extended OpenAI Conversation**
1. Open **Home Assistant**.
2. Go to **Settings → Devices & Services → Add Integration**.
3. Search for **Extended OpenAI Conversation**.
4. Enter your **OpenAI API Key** (Get it from [OpenAI's Platform](https://platform.openai.com/signup/)).
5. Use the following configuration settings:
   - **Model:** `gpt-4o-2024-11-20`
   - **Max Tokens:** `2400`
   - **Top P:** `0.9`
   - **Temperature:** `0.7`
6. Save settings and restart Home Assistant.

### **🔹 Step 4: Install LLM Vision Integration**
1. Go to **Settings → Devices & Services**.
2. Click **Add Integration**.
3. Search for **LLM Vision** and install it.
4. Configure **image analyzer** using:
   - **Provider:** OpenAI
   - **Max Tokens:** `100`
   - **Temperature:** `0.3`
   - **Model:** `gpt-4o`

### **🔹 Step 5: Install OpenWakeWord & Setup Custom Wake Word**
1. Install **OpenWakeWord** following this guide:  
   🔗 [OpenWakeWord Installation](https://github.com/dscripka/openWakeWord/tree/main)
2. Download the **Ammu Wake Word Model**:  
   🔗 [Ammu Wake Word](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite)
3. Place the **TFLite file** into your **Home Assistant Local Directory** using **Samba Share**.

### **🔹 Step 6: Flash Custom Firmware on ESP Device**
1. Download the **custom firmware**:  
   🔗 [Ammu AI Firmware](https://github.com/kiranvenom1209/ammuai/blob/main/flashable_code/ammuaiencrypted.bin)
2. Use **ESPHome** to flash it.
3. Ensure **WiFi SSID and password** are pre-configured in the `secrets.yaml` file.
4. Restart your ESP device and verify the connection with Home Assistant.

### **🔹 Step 7: Select "Ammu" Pipeline & Start Using**
1. Go to **Settings → Voice Assistants → Pipelines**.
2. Select the **Ammu pipeline**.
3. Save settings and restart Home Assistant.
4. Say **"Ammu"** to activate!

---

## 🎯 **Why Choose Ammu AI?**
✅ **The First Fully Intelligent Malayalam AI**  
✅ **Accurate & Natural Speech Processing**  
✅ **Smart Home Control with Maximum Privacy**  
✅ **Optimized for Home Assistant with Custom Firmware**  
✅ **Highly Configurable with Minimal Monthly Cost (€5 or Less!)**  

🔗 **Project Repository:** [Ammu AI GitHub](https://github.com/kiranvenom1209/ammuai/)  
📜 **License:** Open-Source under MIT License  
📧 **Support:** For troubleshooting, open an issue in the repository.

---

## 🚀 **Future Plans**
- **Local LLM Support**: Running Ammu AI on-device with **offline AI models**.
- **Enhanced Vision AI**: Integrating person and object recognition.
- **Automated Home Security Alerts**: More advanced **real-time alerts** based on vision.

---

## 🙌 **Credits**
Developed by **Kiran Karthikeyan Achari** and **Danny Sneham**.
Inspired by **Raghavan (Gaganachari), Jarvis, Friday, and Edith**.

🚀 **Experience the next level of Malayalam AI with Ammu!** 🎤

