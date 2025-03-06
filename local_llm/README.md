# Ammu AI – Local LLM Fine-Tuning Dataset

This repository contains the fine-tuning datasets for **Ammu AI**, the ultimate intelligent Malayalam-speaking AI assistant optimized for seamless integration with Home Assistant and Text-to-Speech (TTS).

---

## 🗃️ Dataset Overview

This dataset is specifically prepared in OpenAI's recommended **ChatCompletion JSONL** format, optimized for fine-tuning conversational GPT models, particularly the **GPT-4o-mini-2024-07-18** model, as well as local LLMs like DeepSeek, Ollama, and other open-source conversational models.

### 📦 Files Included
- **`ammu_chat_finetune.jsonl.gz`** *(main training dataset, gzip compressed due to GitHub file-size limits)*
- **`ammu_chat_validation.jsonl`** *(structured validation set)*

### ⚙️ Dataset Format Example

Each entry in `jsonl` follows the structure:

```json
{
  "messages": [
    {"role": "system", "content": "🔹 AMMU: നിങ്ങളുടെ വിശ്വസ്ത സഹായിയാണു!..."},
    {"role": "user", "content": "Ammu, വീടിന്റെ നിലവാരം എങ്ങനെയുണ്ട്?"},
    {"role": "assistant", "content": "ചേട്ടാ, വീടിന്റെ നിലവാരം മികച്ചതാണ്. എല്ലാ സംവിധാനങ്ങളും സാധാരണ നിലയിലാണ്."}
  ]
}
```

### 📂 Dataset Structure

- **Training dataset** (`ammu_chat_finetune.jsonl.gz`):
  - **Size**: Large dataset (compressed with gzip for easy upload)
  - Contains a blend of real Malayalam conversational dialogues from popular movie subtitles and structured examples specifically crafted to define Ammu’s personality and conversational style.

- **Validation dataset** (`ammu_chat_validation.jsonl`):
  - Smaller subset for evaluation
  - Contains carefully structured conversational interactions to validate model performance during fine-tuning.

---

## 🛠️ Using the Dataset for Fine-Tuning

### Step 1: Extract JSONL file
```bash
gzip -d ammu_chat_finetune.jsonl.gz
```

### Step 2: Uploading to OpenAI

Upload your files via OpenAI CLI:

```bash
openai api files.upload -f ammu_chat_finetune.jsonl -p "fine-tune"
openai api files.upload -f ammu_chat_validation.jsonl -p "validation set for Ammu AI"
```

### Step 3: Fine-Tuning (OpenAI GPT-4o-mini)

Run your fine-tuning job with optimal settings:

```bash
openai api fine_tunes.create \
  -t <training-file-id> \
  -v <validation-file-id> \
  -m gpt-4o-mini-2024-07-18 \
  --n_epochs 2 \
  --batch_size 24 \
  --learning_rate_multiplier 0.1 \
  --prompt_loss_weight 0.01
```

Replace `<training-file-id>` and `<validation-file-id>` with your uploaded file IDs from OpenAI.

---

## 🔮 Fine-Tuning Local Models (DeepSeek, Ollama, etc.)

You can utilize this dataset for fine-tuning local, open-source models such as DeepSeek, Ollama, and other conversational models. Here's how:

### Using DeepSeek
- Install DeepSeek CLI and setup your local model environment.
- Convert JSONL to the format required by DeepSeek if necessary (usually compatible directly).
- Start fine-tuning:

```bash
deepseek fine-tune --train-data ammu_chat_finetune.jsonl --eval-data ammu_chat_validation.jsonl --epochs 2
```

### Using Ollama
- Install Ollama and set up the local server environment.
- Import or convert your JSONL data according to Ollama's supported format.
- Start fine-tuning:

```bash
ollama train -d ammu_chat_finetune.jsonl -e 2
```

### Other Local LLMs
- Convert JSONL to the respective format needed by your local LLM toolkit (Alpaca, LoRA, Hugging Face Transformers).
- Use standard fine-tuning scripts provided by the frameworks.

---

## 🚀 Integration with Home Assistant

Once fine-tuning completes, directly integrate Ammu into Home Assistant via REST API or OpenAI integration plugins:

```yaml
rest_command:
  ammu_query:
    url: "https://api.openai.com/v1/chat/completions"
    method: POST
    headers:
      Authorization: "Bearer YOUR_API_KEY"
      Content-Type: "application/json"
    payload: >
      {
        "model": "ft:gpt-4o-mini-2024-07-18:your-account:ammu-ai:suffix",
        "messages": [
          {"role": "system", "content": "🔹 AMMU: നിങ്ങളുടെ വിശ്വസ്ത സഹായിയാണു!..."},
          {"role": "user", "content": "{{ query }}"}
        ],
        "temperature": 0.6
      }
```

---

## 🔍 Technical Insights & Recommendations

- **Epochs:** `2` (optimal for conversational data)
- **Batch size:** 24 (Balanced for speed and stability)
- **Learning Rate multiplier:** 0.1 (recommended)

---

## 🗣️ TTS Optimization

Ammu's responses have contextual pauses to ensure natural Malayalam pronunciation when using TTS services (like Home Assistant Cloud TTS Malayalam SobhanaNeural).

## 🔗 Links & Resources
- [OpenAI Fine-tuning Guide](https://platform.openai.com/docs/guides/fine-tuning)
- [Home Assistant Voice Integration Guide](https://www.home-assistant.io/docs/voice/)
- [DeepSeek Documentation](https://deepseek-ai.com)
- [Ollama Documentation](https://ollama.ai)

---

## 🛠️ Contributions & Issues

Contributions, issues, or improvements are welcome:
- Fork the repository.
- Make changes or enhancements.
- Submit a Pull Request.

## 📄 License

This dataset is released under the **MIT License**.

---

Enjoy building your intelligent, Malayalam-speaking AI assistant—Ammu! 🌟🚀
