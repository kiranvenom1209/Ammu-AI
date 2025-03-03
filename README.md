# Ammu AI - The Ultimate Intelligent Malayalam Assistant

Welcome to **Ammu AI** – the first, fully intelligent Malayalam AI assistant built to transform your smart home experience. Imagine a personal assistant that speaks your language with natural grace, understands your cultural nuances, and seamlessly integrates with your Home Assistant. Inspired by legendary AIs like **Jarvis**, **Friday**, and **Edith**, and the iconic character **Raghavan** from *Gaganachari*, Ammu AI is here to revolutionize your daily interactions.

---

## 🌟 Why Ammu AI?

- **Unmatched Malayalam Fluency:** Ammu AI is designed to converse in fluent, grammatically perfect Malayalam, making every interaction feel natural and engaging.
- **Smart Home Command Center:** With deep integration into Home Assistant, Ammu AI controls your smart devices, automates routines, and even secures your home—all while keeping your data local and secure.
- **Cost-Effective Intelligence:** Enjoy the power of advanced AI at a minimal monthly cost (often under €5), thanks to optimized API usage and efficient design.
- **Cultural Relevance & Customization:** Tailor Ammu’s personality using our provided base prompt and function files, ensuring that she not only understands your language but also resonates with your cultural identity.

---

## 🚀 Key Features

### 🗣️ Natural Malayalam Speech Processing
- **Fluent Communication:** Leverages Home Assistant Cloud STT (ml-IN) for accurate speech-to-text conversion.
- **Rich Vocal Experience:** Replies using TTS (ml-IN) SobhanaNeural, offering a natural and warm voice with perfect intonation.

### 🎤 Custom Wake Word - "Ammu"
- **Efficient Activation:** Uses a custom TensorFlow Lite (TFLite) model for wake word detection, integrated via OpenWakeWord.
- **Easy Setup:** Simply download the [Ammu Wake Word Model](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite) and enjoy hands-free interaction.

### 🤖 Advanced AI-Powered Conversations
- **Extended OpenAI Conversation:** Powered by GPT-4o with configurations fine-tuned to deliver intelligent, mature, and context-aware responses.
- **Custom Personality:** A tailored base prompt sets Ammu’s tone as a friendly 28-year-old assistant, ensuring consistency and personality in every exchange.

### 📸 LLM Vision - Intelligent Image Analysis
- **Smart Vision Capabilities:** Analyze images for enhanced home security and automation using OpenAI’s Vision API integrated into Home Assistant LLM Vision.
- **Real-Time Analysis:** Recognize objects, people, and text from live CCTV feeds to keep your home safe and smart.

### 🔒 Privacy & Local Processing
- **Data Security First:** All processes run locally where possible, minimizing unnecessary cloud dependencies.
- **Custom Firmware Integration:** Optimized firmware for ESP devices ensures maximum performance and security.

---

## 🛠️ Installation & Setup Guide

### Step 1: Prepare Your Home Assistant
1. **Install Home Assistant OS:** Use a Raspberry Pi, Intel NUC, or your preferred Home Server.
2. **Follow the Official Guide:**  
   🔗 [Home Assistant Installation Guide](https://www.home-assistant.io/installation/)
3. **Keep It Updated:** Ensure your installation is running the latest version.

### Step 2: Configure Home Assistant Cloud & Pipelines
1. **Subscribe to Home Assistant Cloud:**  
   🔗 [Home Assistant Cloud (Nabu Casa)](https://www.nabucasa.com/)
2. **Set Up a New Pipeline:**  
   - Go to **Settings → Voice Assistants → Pipelines**.
   - Create a new pipeline named **Ammu**.
   - Set the language to **Malayalam (ml-IN)**.
   - Select **Home Assistant Cloud STT** and **TTS (SobhanaNeural)**.

### Step 3: Install Extended OpenAI Conversation
1. **Open Home Assistant:**
   - Navigate to **Settings → Devices & Services → Add Integration**.
   - Search for **Extended OpenAI Conversation**.
2. **API Configuration:**
   - Enter your OpenAI API Key (get it from [OpenAI's Platform](https://platform.openai.com/signup/)).
   - Use these settings:
     - **Model:** `gpt-4o-2024-11-20`
     - **Max Tokens:** `2400`
     - **Top P:** `0.9`
     - **Temperature:** `0.7`
3. **Finalize:** Save and restart Home Assistant.

### Step 4: Set Up LLM Vision Integration
1. **Add LLM Vision Integration:**  
   - Navigate to **Settings → Devices & Services** and search for **LLM Vision**.
2. **Configuration Details:**
   - **Provider:** OpenAI
   - **Max Tokens:** `100`
   - **Temperature:** `0.3`
   - **Model:** `gpt-4o`

### Step 5: Implement OpenWakeWord & Custom Wake Word
1. **Install OpenWakeWord:**  
   - Follow the guide: 🔗 [OpenWakeWord Installation](https://github.com/dscripka/openWakeWord/tree/main)
2. **Download & Install Wake Word Model:**  
   - Get the [Ammu Wake Word Model](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite) and place it in your Home Assistant Local Directory via Samba Share.

### Step 6: Flash Custom Firmware on Your ESP Device
1. **Download Firmware:**  
   - 🔗 [Ammu AI Firmware](https://github.com/kiranvenom1209/ammuai/blob/main/flashable_code/ammuaiencrypted.bin)
2. **Flash Using ESPHome:**
   - Ensure WiFi credentials are pre-configured in `secrets.yaml`.
   - Flash the firmware and restart your device.

### Step 7: Activate Ammu AI
1. **Select the Ammu Pipeline:**  
   - Go to **Settings → Voice Assistants → Pipelines** and choose the **Ammu pipeline**.
2. **Final Setup:**  
   - Save settings and restart Home Assistant.
   - Simply say **"Ammu"** to activate your assistant.

---

## 📝 Customization: Using Ammu Base Prompt & Ammu Functions

Ammu AI is designed for flexibility and continuous enhancement. Two critical files enable you to customize Ammu’s behavior and extend her functionality:

### **ammu_baseprompt.txt**
- **Purpose:** Contains the core conversational prompt defining Ammu’s personality, tone, and style.
- **How to Use:**
  - Open the file located [here](https://github.com/kiranvenom1209/ammuai/blob/main/ammu_baseprompt.txt).
  - Customize the base prompt to adjust Ammu’s responses—be it more formal, friendly, or culturally nuanced.
  - Deploy the updated prompt in your Home Assistant configuration for real-time changes in Ammu’s interaction style.

### **ammu_functions.txt**
- **Purpose:** Hosts custom functions and integrations that extend Ammu AI’s capabilities beyond basic conversation.
- **How to Use:**
  - Access the file from [this link](https://github.com/kiranvenom1209/ammuai/blob/main/ammu_functions.txt).
  - Review the provided functions to understand how Ammu handles tasks—from smart home control to dynamic responses.
  - Modify or add new functions to tailor Ammu’s behavior to your specific needs, ensuring she remains the smartest assistant in the Malayalam market.

---

## 💎 What Sets Ammu AI Apart?

- **Exclusive Malayalam Expertise:** Ammu AI is finely tuned to understand and converse in Malayalam, making her the ideal companion for Malayalam speakers.
- **Seamless Integration:** Optimized specifically for Home Assistant, Ammu AI effortlessly bridges the gap between modern technology and traditional homes.
- **Innovative and Adaptable:** With an ever-growing suite of custom functions and prompt configurations, Ammu AI continuously evolves to meet the future needs of smart home enthusiasts.
- **User-First Design:** Every aspect—from privacy to performance—is engineered to deliver an unparalleled user experience.

---

## 📈 Future Enhancements

Ammu AI is just the beginning. Upcoming improvements include:

- **Local LLM Support:** Bringing offline AI capabilities to run directly on your device.
- **Enhanced Vision Capabilities:** Advanced object and person recognition for real-time security.
- **Automated Security Alerts:** Smarter, context-aware alerts to keep your home safe.
- **Expanded Customization Options:** More in-depth configuration files to personalize every interaction.

---

## 📜 License & Support

- **License:** Open-source under the MIT License.
- **Repository:** [Ammu AI on GitHub](https://github.com/kiranvenom1209/ammuai/)
- **Need Help?** Open an issue in the repository or contact us directly for troubleshooting and support.

---

## 🙌 Credits

Developed by **Kiran Karthikeyan Achari** and **Danny Sneham**, Ammu AI is the result of a shared passion for creating technology that respects language, culture, and innovation.

**Experience the next level of intelligent, culturally attuned home automation with Ammu AI – the only Malayalam AI assistant you'll ever need.**

---

Embrace the future of smart home technology with Ammu AI today!
