# 🚀 Ammu AI – The First Intelligent Malayalam AI Assistant

> **Created by Kiran Karthikeyan Achari & Danny Sneham**

> **Inspired by the legendary Raghavan from Gaganachari and Marvel’s Jarvis, Friday, and EDITH, Ammu AI is the first truly intelligent Malayalam AI assistant, blending cultural authenticity with cutting-edge AI technology.**

---

## 🌟 Introduction

Ammu AI is a next-generation **Malayalam-speaking AI assistant** designed for **Home Assistant**, making smart homes truly intelligent in the **Malayalam language**. Unlike generic voice assistants, Ammu is **context-aware, culturally adaptive, and seamlessly integrated with smart home devices**.

### 🏡 **What Makes Ammu Special?**

✅ **Flawless Malayalam with Phonetic English Support** – No awkward translations!\
✅ **Context-Aware Smart Home Control** – Lights, security, climate, and more!\
✅ **Conversational AI with Personality** – A true assistant, not just a command parser.\
✅ **Fully Integrated with Home Assistant Voice PE** – A seamless smart home experience.\
✅ **Custom Wake Word using OpenWakeWord** – Personalized trigger phrases.\
✅ **Vision AI for Camera Analysis** – Uses LLM Vision for advanced image recognition.\
✅ **Raspberry Pi / Home Server Ready** – Low-latency response and local processing options.

---

## 🛠️ **Technology Stack**

Ammu AI is built on a robust tech stack integrating multiple AI models, wake word detection, and smart home automation.

### 🔧 **Core Components**

| Component                | Technology Used                                   |
| ------------------------ | ------------------------------------------------- |
| **AI Model**             | GPT-4o (Extended OpenAI Conversation)             |
| **STT (Speech-to-Text)** | Home Assistant Cloud STT (ml-IN, Malayalam India) |
| **TTS (Text-to-Speech)** | SobhanaNeural (ml-IN)                             |
| **Wake Word**            | OpenWakeWord (Custom Triggers)                    |
| **Vision AI**            | LLM Vision Integration                            |
| **Home Automation**      | Home Assistant Voice PE                           |
| **Cloud Processing**     | Home Assistant Cloud + Local Server Support       |

### 🖥️ **Home Assistant Integration**

Ammu AI is designed to run seamlessly within **Home Assistant**, providing smart home automation, real-time voice interactions, and advanced AI-driven responses.

**Main Integrations:**

- **Extended OpenAI Conversation** (for intelligent responses).
- **Home Assistant Voice PE** (for deep voice integration).
- **LLM Vision** (for security camera analysis).
- **OpenWakeWord** (custom wake word detection).

---

## 🎙️ **Speech & Language Handling**

Ammu AI is **fully optimized for Malayalam**, ensuring natural and grammatically correct responses while handling English words using phonetic Malayalam spelling to prevent awkward TTS pronunciation issues.

✅ **All English words are transliterated into Malayalam.**\
✅ **Natural conversational flow with correct grammar and phrasing.**\
✅ **Avoids robotic or bookish Malayalam, ensuring a real-life conversational tone.**

### 🗣️ **Examples of English Words in Malayalam**

| English Word             | Malayalam Phonetic        |
| ------------------------ | ------------------------- |
| **Lock**                 | ലോക്ക്                    |
| **Main Door**            | മേയിൻ ഡോർ                 |
| **Security Camera**      | സെക്യൂരിറ്റി ക്യാമറ       |
| **Entertainment System** | എന്റർടെയിൻമെന്റ് സിസ്റ്റം |
| **Bluetooth**            | ബ്ലൂടൂത്ത്                |
| **Wi-Fi**                | വൈ-ഫൈ                     |
| **Projector**            | പ്രൊജക്ടർ                 |
| **Rain Mode**            | റെയിൻ മോഡ്                |
| **Battery Status**       | ബാറ്ററി സ്റ്റാറ്റസ്       |
| **Google**               | ഗൂഗിൾ                     |

---

## 🔥 **Setup Guide**

### 🚀 **Step 1: Install Required Home Assistant Integrations**

1. **Extended OpenAI Conversation**

   - Navigate to **Settings → Integrations** in Home Assistant.
   - Search for **Extended OpenAI Conversation** and install.
   - Set the API to **GPT-4o** with the recommended settings (refer to images).

2. **Home Assistant Voice PE**

   - Install the **Voice PE** add-on for real-time voice interactions.

3. **STT & TTS Configuration**

   - Enable **Home Assistant Cloud STT (ml-IN)** for **speech-to-text**.
   - Set **SobhanaNeural (ml-IN)** as the **text-to-speech (TTS)** engine.

4. **LLM Vision Integration (Optional for Cameras)**

   - Set up **LLM Vision** under **Scripts → llmvision.image\_analyzer** in Home Assistant.
   - Assign it to relevant security cameras.

### 🎤 **Step 2: Setup OpenWakeWord for Custom Wake Word**

Ammu AI uses a **custom wake word** trained via OpenWakeWord.

#### 🔧 **To Enable OpenWakeWord:**

1. Clone the OpenWakeWord repository:
   ```bash
   git clone https://github.com/dscripka/openWakeWord.git
   cd openWakeWord
   ```
2. Train a new wake word model (`wakeword.wav` of your choice).
3. Integrate the model into Home Assistant’s voice assistant settings.

---

## 📊 **Optimal AI Settings**

For **best performance**, use these **GPT-4o** settings in Extended OpenAI Conversation:

- **Maximum Tokens:** `2400`
- **Top P:** `0.9`
- **Temperature:** `0.7`
- **Max Function Calls:** `1`
- **Context Threshold:** `23000`
- **Context Truncation Strategy:** `Clear All Messages`

---

## 🎯 **Future Enhancements & Roadmap**

- **🧠 Local LLM Support:** Fine-tuning **Mistral/DeepSeek LLMs** for offline processing.
- **📹 Enhanced Vision AI:** Real-time facial and object recognition for **home security**.
- **🔊 Multi-User Profiles:** Context-aware **voice differentiation**.
- **💬 Multi-Language Expansion:** Support for **Tamil, Kannada, and Hindi** along with Malayalam.

---

## 🙌 **Contributing & Support**

Want to improve Ammu AI? Feel free to **contribute** by:

- Enhancing **Wake Word Models**
- Fine-tuning **STT/TTS Processing**
- Adding **New AI Capabilities**

💬 **Discussions & Updates:** Join our **GitHub Issues** and **Community Discussions**.

📧 **Need Help?** Open a GitHub issue or reach out!

---

## 🎉 **Final Thoughts**

Ammu AI is **not just another AI assistant**—it’s the **first truly intelligent Malayalam AI**, bringing an immersive, **culturally rich experience** to smart homes. Whether it's managing home automation, answering queries, or interacting with a natural flow, **Ammu AI is here to revolutionize smart assistant interactions for Malayalis worldwide**.

🔥 **Let’s build the future of Malayalam AI together!** 🚀

