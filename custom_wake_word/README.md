# Custom Wake Word for Ammu AI

Welcome to the **Custom Wake Word** directory for **Ammu AI**! This repository contains the **custom TensorFlow Lite (TFLite) wake word model** specifically trained to recognize the trigger word **"Ammu"**. This allows **Ammu AI** to be activated by voice without relying on generic wake words like "OK Google" or "Hey Siri".

## 🔹 How the Custom Wake Word Works

Ammu AI leverages **OpenWakeWord**, an open-source wake word detection system, to recognize the custom **"Ammu"** wake word. This enables a **low-latency, offline voice activation system** that integrates seamlessly with **Home Assistant Voice Assistant**.

### 🚀 Features

*   **Custom-trained model** for precise recognition of "Ammu".
*   **Runs entirely offline**, ensuring privacy and fast response time.
*   **Optimized for ESP32-S3 & Edge AI devices** running ESPHome.
*   **Minimal resource consumption**, making it ideal for smart home applications.
*   **Easily updatable** by replacing the wake word model.

---

## 🔹 Installation Guide

To set up the **Ammu** wake word, follow these steps:

### 1️⃣ **Download the Custom Wake Word Model**

Download the latest version of the **Ammu wake word model** from the GitHub repository:

🔗 [Download `ammu.tflite`](https://github.com/kiranvenom1209/ammuai/tree/main/custom_wake_word/ammu.tflite)

### 2️⃣ **Transfer the Model to Home Assistant**

Once you have downloaded the **`ammu.tflite`** file, you need to place it in the **Home Assistant Local Directory** using the **Samba Share** integration.

#### 🔹 Steps to Install Samba Share on Home Assistant:

1.  Open **Home Assistant**.
2.  Navigate to **Settings** > **Add-ons**.
3.  Click **Add-On Store**.
4.  Search for **Samba Share** and install it.
5.  Start the **Samba Share** service and enable **Start on Boot**.
6.  From your PC, access the **Home Assistant local storage** via File Explorer:
    *   On Windows: `\\homeassistant\config`
    *   On macOS: `smb://homeassistant.local/config`
7.  Create a folder named `wakeword/` (if it does not exist) inside `config/`.  *(Note: It is recommended to use `homeassistant/wake_word` as the directory)*
8.  Copy the `ammu.tflite` file into `config/wakeword/`.

🔹 **Expected Path:** `/config/wakeword/ammu.tflite`

### 3️⃣ **Install OpenWakeWord in Home Assistant**

Ammu AI uses **OpenWakeWord** for real-time wake word detection.

#### 🔹 Steps to Install OpenWakeWord:

1.  Go to **Settings** > **Add-ons**.
2.  Click **Add-On Store**.
3.  Search for **OpenWakeWord** and install it.
4.  Start the **OpenWakeWord** service and enable **Start on Boot**.
5.  Open **OpenWakeWord Configuration** and add the path to the custom wake word:

    ```yaml
    wake_word_model: "/config/wakeword/ammu.tflite"
    sensitivity: 0.5  # Adjust this value (0.0 - 1.0) to control how easily the wake word is triggered.  Higher values are more sensitive.
    ```

### 4️⃣ **Restart Home Assistant**

After completing the above steps, restart **Home Assistant** to apply the changes.

### 5️⃣ **Select Wake Word in Home Assistant Voice Settings**

1.  Go to **Settings** > **Voice Assistants**.
2.  Under **Wake Word**, choose **OpenWakeWord**.
3.  Save and restart the voice assistant.

---

## 🔹 Training Details

The `ammu.tflite` model was trained using a combination of Google Colab and local hardware, leveraging a Docker environment for consistency.  The training process followed the guidelines provided in the OpenWakeWord repository ([link to OpenWakeWord GitHub](https://github.com/dscripka/openWakeWord/tree/main)). The training dataset consisted of recordings of the word 'Ammu' spoken by various individuals in different environments.

---

## 🔹 Testing the Wake Word

Once everything is set up, test the wake word:

1.  Say **"Ammu"** near your microphone.
2.  The **voice assistant LED should light up** (if configured).
3.  Ammu AI should respond to the wake word.

🔹 **Troubleshooting**:

*   If Ammu is not responding, **increase sensitivity** in the **OpenWakeWord** configuration.
*   Check if the wake word file is correctly placed at `/config/wakeword/ammu.tflite`.
*   **Ensure your microphone is correctly configured in Home Assistant. Go to Settings -> Devices & Services -> ESPHome -> [Your Ammu Device] and verify the microphone settings.**
*   Restart **Home Assistant** and try again.

---

## 🔹 Updating the Wake Word Model

You can replace `ammu.tflite` with an improved version anytime by following the same steps.

🔹 **For better accuracy, future versions will include**:

*   Noise-resistant models trained with diverse environments.
*   Support for additional trigger phrases.
*   Improved TensorFlow Lite optimizations.

---

## 🔹 Credits & Acknowledgments

*   **Ammu AI** was created by **Kiran Karthikeyan Achari & Danny Sneham**.
*   **Wake word detection powered by OpenWakeWord**: [GitHub Repository](https://github.com/dscripka/openWakeWord/tree/main)
*   **Inspired by Raghavan (Gaganachari Movie) & Marvel AI Systems (JARVIS, FRIDAY, EDITH)**.

---

## 🔹 Support & Contributions

If you find any issues or want to improve the wake word model, feel free to contribute:

🔹 **GitHub Repository**: [Ammu AI](https://github.com/kiranvenom1209/ammuai)
🔹 **Discussion & Support**: [Ammu AI Discussions](https://github.com/kiranvenom1209/ammuai/discussions)

For further assistance, open an **Issue** on GitHub.

🚀 **Enjoy a smarter AI with "Ammu" wake word detection!**
