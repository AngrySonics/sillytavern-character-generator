> [!NOTE]
> This repository was generated using AI (with a few touch-ups from me). This likely shouldn't be an issue, considering how it's designed for a frontend to chat with AI characters, but if you prefer not to use AI for your characters, you should find another repository.

# SillyTavern Character Card Generator

Auto-generate SillyTavern Character Card V3 (`chara_card_v3`) JSON files using AI. Just describe a character and get properly formatted, ready-to-import JSON.

## How to Use

1. Upload the prompt file to Claude, ChatGPT, Gemini, DeepSeek, or your preferred LLM.
2. Type `"execute these instructions"` or `"let's make a character card"` (or add `"generate now"` to skip clarifying questions).
3. Answer 2-3 questions about your character.
4. Copy the JSON output and save it as a `.json` file (or paste it directly into SillyTavern).
5. Import into SillyTavern.

That's it. The JSON is generated with proper `\n` escaping, straight ASCII quotes, and valid CCv3 schema structure.

## What You Get

- **Token-optimized permanent fields** (600–1,000 tokens across `description`, `personality`, and `scenario`)
- **Rich, open-ended greetings** (`first_mes`, optional `alternate_greetings`, and `group_only_greetings` for group chats)
- **Example dialogues** (`mes_example`) tailored to the character's voice without impersonating `{{user}}`
- **Smart `nickname` support** — Automatically populates `data.nickname` for formal/full names (compatible with the [Nicknames](https://github.com/SillyTavern/SillyTavern-Nicknames) extension for SillyTavern)
- **Optional Embedded Lorebooks** (`character_book`) with CCv3 decorators (`@@depth`, `@@is_greeting`, `@@activate_only_after`)
- **Proper `{{char}}` / `{{user}}` placeholders** and straight-quote JSON formatting

## Model & Hardware Notes

- **Cloud & Local Models:** Tested with cloud frontier models and local 8B+ quantized models (`IQ4_XS` or higher). Ultra-small models (such as **Llama 3.2 1B or 3B**) have not been tested, so your experience may suffer.
- **Web Search Support (Canonical Characters):** If your LLM has web search enabled (such as [KoboldCpp](https://github.com/lostruins/koboldcpp) via "Enable WebSearch" in the Network tab or `--websearch`, Claude, Gemini, ChatGPT, or DeepSeek), it can look up canon lore, wiki details, and speech patterns online to build much more accurate cards for existing or newly released characters, which can help prevent hallucinations.
- **Tip for SillyTavern Nicknames Users:** If the generated card includes a `nickname` field, enable **V3 spec compatibility** and **Macros & prompts** under **Extensions → Nicknames** to sync it automatically.

<details>
<summary>Local VRAM / Context Benchmark (KoboldCpp)</summary>

Even on 6GB VRAM setups (e.g., an RTX 4050 running Llama 3.1 8B quantized to `IQ4_XS` (~4.14 GB) with all 33 layers on GPU, MMproj/embeds offloaded to CPU, `q4_0` KV cache, and MMQ enabled on a MSI Katana 15 B13VEK), KoboldCpp supports up to **30,720 tokens** of context (or **20,480 tokens** alongside a GGML `base q5_1` transcriber model), leaving plenty of headroom for 1,000-token V3 cards. KoboldCpp can theoretically go up to 262,144 tokens in the launcher, or up to 524,288 tokens in the command line (or [even more!](https://koboldcpp.net/docs/settings/context-size/#:~:text=For%20more%20than%20262144%2C%20use%20%2D%2Dcontextsize%2C%20or%20set%20it%20in%20a%20config%20file%20and%20start%20that%20with%20%2D%2Dconfig%2E%20The%20launcher%20cannot%20load%20a%20config%20whose%20context%20size%20is%20not%20one%20of%20its%20slider%20steps)), though results have not been tested.
</details>