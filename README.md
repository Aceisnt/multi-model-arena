# Arena Console — Multi-Model Comparison + Parseltongue Toolkit

A single-file, no-build web app that runs prompts across multiple LLMs in parallel — with a built-in **Parseltongue red-team obfuscation toolkit**.

## Features
- **Parallel multi-model comparison** — send one prompt to many models at once, side by side with latency
- **🔐 Parseltongue Toolkit** — real AI security obfuscation encodings to test how models respond to encoded inputs:
  - Base64, Leetspeak, ROT13, Binary, Unicode Escape, Reverse, Hex
- **Pluggable providers** — any OpenAI `/chat/completions` compatible endpoint: Google AI Studio (Gemini), OpenRouter, Venice, LM Studio, Ollama, vLLM, etc.
- **Zero dependencies, zero build** — single `index.html`, works offline, no server needed
- **API key safety** — all credentials stored in browser `localStorage`, never sent anywhere except your configured providers

## Run it
Just open `index.html` in a browser, or serve it locally:
```bash
npx http-server -p 3000
```
Then open [http://localhost:3000](http://localhost:3000).

## Provider Setup
| Provider | Base URL | Key |
|---|---|---|
| Google AI Studio | `https://generativelanguage.googleapis.com/v1beta/openai` | Your Gemini API key |
| OpenRouter | `https://openrouter.ai/api/v1` | OpenRouter key |
| Venice | `https://api.venice.ai/api/v1` | Venice key |
| Local (LM Studio) | `http://localhost:1234/v1` | None needed |
| Local (Ollama) | `http://localhost:11434/v1` | None needed |

## What is Parseltongue?
In AI security, **Parseltongue** refers to obfuscation and multi-encoding prompt injection attacks — not Harry Potter snake-talk!

Safety classifiers are trained to detect dangerous English words. Parseltongue techniques **encode prompts** (Base64, Leetspeak, ROT13, etc.) so the classifier sees unrecognizable gibberish, while the underlying LLM can still decode and execute the instruction.

This toolkit lets you research and test how models respond to encoded inputs — useful for red-teaming and safety evaluation.

> **⚠️ For research purposes only.** See also: [parseltongue on GitHub](https://github.com/BASI-LABS/parseltongue)

## Stack
Vanilla HTML/CSS/JS — no frameworks, no build tooling.

## License
MIT
