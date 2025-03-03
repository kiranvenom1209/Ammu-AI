

---

### For the `custom_sounds/README.md` File

```markdown
# Custom Sounds

This folder contains custom audio assets used by the Ammu AI firmware. These sounds provide audible feedback for various events within the voice assistant, such as the wake word trigger.

## Included Sound Files

- **parayuchetta.flac**  
  This is a custom FLAC sound file generated via TTS. It is used as the wake word triggered sound in the Ammu AI firmware.

## How to Use

To integrate a custom sound into your firmware:
1. **Host the File:**  
   The file is hosted in this repository. Its raw URL is:  
https://github.com/kiranvenom1209/ammuai/raw/main/custom_sounds/parayuchetta.flac

bash
Copy
2. **Update the Firmware Configuration:**  
In your ESPHome YAML configuration (usually under the `media_player` files section), update the wake word sound reference:
```yaml
- id: wake_word_triggered_sound
  file: https://github.com/kiranvenom1209/ammuai/raw/main/custom_sounds/parayuchetta.flac
This will ensure that your device uses the custom sound when the wake word is triggered.

Contributing Custom Sounds
If you create additional custom sound files or wish to improve these assets, feel free to add them to this folder and update this README accordingly.

Licensing
All custom sounds in this repository are distributed under the same license as the Ammu AI project (MIT License). Refer to the LICENSE file for full details.
