# Parayu Chetta Sound Asset

This repository contains the custom FLAC sound file **parayuchetta.flac**. Instead of a generic chime, this sound asset plays the Malayalam phrase "Parayu Chetta" – roughly translating to "Hello buddy, how can I help you?" – every time the wake word is triggered. This adds a personal and culturally rich touch to the Ammu AI voice assistant.

## Purpose

The **parayuchetta.flac** file is designed to serve as the audible wake word response for the Ammu AI firmware. When the device detects its wake word, it plays this friendly greeting in Malayalam, making the interaction more engaging and personable. This unique audio prompt differentiates Ammu AI from standard assistants that use generic beeps or chimes.

## Technical Details

- **Format:** FLAC  
  The file is encoded in the FLAC format to ensure high-quality, lossless audio playback while maintaining a small file size.
  
- **Duration & Quality:**  
  The sound file has been carefully trimmed and normalized to match the intended duration for a wake word trigger. It is optimized for quick playback and minimal processing overhead on the ESP32-S3 platform.

- **Usage in Firmware:**  
  In the Ammu AI YAML configuration, the wake word trigger sound is referenced by its ID (`wake_word_triggered_sound`). The firmware downloads and plays the file via its URL. For example:
  
  ```yaml
  - id: wake_word_triggered_sound
    file: https://github.com/kiranvenom1209/ammuai/raw/main/custom_sounds/parayuchetta.flac
Integration:
This asset is part of a larger audio ecosystem in Ammu AI, which includes multiple sound files for various states (e.g., button press, error, timer alerts). The custom sound enhances the user experience by providing localized feedback in Malayalam.
Future Scope
The custom_sounds directory is envisioned as a dynamic collection of audio assets for Ammu AI. Future enhancements may include:

Additional Languages & Phrases:
Expanding the library with sounds in other languages or dialects to cater to a diverse user base. Imagine having localized greetings or command confirmations in multiple languages.

User-Customizable Prompts:
Developing a user interface or integration with Home Assistant that allows users to upload and configure their own audio files. This would give each user a chance to personalize their assistant's responses.

Dynamic Audio Effects:
Integration with audio processing modules to dynamically adjust the tone, pitch, or volume of sound prompts based on environmental factors or user preferences.

Interactive Feedback:
Creating context-aware responses, where the assistant’s audio feedback changes based on the current mode (e.g., different sounds for high ambient noise levels or different greetings at various times of day).

Credits
Kiran:
The primary creator of Ammu AI and the mastermind behind this project. Kiran’s vision for a culturally nuanced and interactive voice assistant is reflected in every aspect of the project, from hardware design to software configuration.

Danny:
A key contributor who provided valuable technical insights and helped shape the project's audio capabilities. Danny’s support and expertise have been crucial to the success of this project.

Enjoy the rich, localized audio experience with Ammu AI and let "Parayu Chetta" be your friendly call to action! For further details or contributions, please visit the Ammu AI repository.
