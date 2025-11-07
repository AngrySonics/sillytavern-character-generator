# SillyTavern Character Card Generator

Auto-generate SillyTavern Character Card V2 JSON files using AI. Just describe a character and get properly formatted, ready-to-import JSON.

## Two Versions

- **Standard**: 600-1000 tokens - For cloud models or powerful local setups
- **Small Model**: 400-600 tokens - For 7B-13B models with 6-12GB VRAM

## How to Use

1. Upload the prompt file to Claude, GPT, Gemini, DeepSeek, etc.
2. Type "execute these instructions" or "let's make a character card"
3. Answer 2-3 questions about your character
4. Copy the JSON output
5. Import into SillyTavern

That's it. The JSON is already properly formatted with correct escaping and field order.

## What You Get

- Token-optimized description, personality, and scenario
- Example dialogues in the character's voice
- Multiple greeting options
- Proper `{{char}}`/`{{user}}` placeholders
- All technical formatting handled automatically

## Which Version?

**Standard** - Cloud models, 16GB+ VRAM, want detailed characters

**Small Model** - Local models, limited VRAM, quantized models, faster inference

---

[Full RP toolkit](https://docs.google.com/document/d/1CfWHATYyDH5HYw_7vFKtax-2fCiE-3hnmAGOtyJWTkM/edit?tab=t.0) • Free to use
