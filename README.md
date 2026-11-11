# Vanta: AI chat client for iPhone and iPad

Vanta is an iOS app for chatting with the AI models you choose: your own **Ollama, LM Studio, llama.cpp or vLLM** server, your own API keys (**OpenRouter**, Anthropic, Groq, DeepSeek, Gemini and more), **offline GGUF and MLX models** on the iPhone itself, and **Apple Intelligence**. One-time purchase, no subscription, no account.

**[Download on the App Store](https://apps.apple.com/app/id6758898098?pt=128128593&ct=github&mt=8)** · [vantaclient.app](https://vantaclient.app) · [Report a bug](https://github.com/EzeLLM/vanta/issues/new/choose)

This repository holds Vanta's public documentation and its issue tracker. The app's source code is not published.

## What it does

- **Your own server:** Ollama, LM Studio, llama.cpp (llama-server), vLLM, Jan and Docker Model Runner with step-by-step setup; SGLang, LiteLLM, LocalAI, KoboldCpp, Open WebUI, Hugging Face TGI or any server with a compatible chat API. At home, or away over a VPN such as Tailscale or an HTTPS address.
- **Your own API keys (BYOK):** OpenRouter is built in; add Anthropic, Groq, DeepSeek, Mistral, the Gemini API, Together AI, Fireworks, xAI, Cerebras or another compatible provider. Your provider bills you directly.
- **Offline on the device:** browse Hugging Face inside Vanta and download GGUF or MLX models, or import a GGUF file. Selected MLX models can see images.
- **Apple Intelligence:** the on-device model on supported devices with iOS 26 or later.
- **More than chat:** PDFs and photos, web search with your own Tavily key, Deep Research, MCP tools (remote MCP servers over HTTPS), group chats that mix several models, memory, on-device voice input, and every prompt Vanta sends is yours to edit.
- **Private:** conversations stay on your iPhone or iPad. There is no Vanta server and no Vanta account.

Requires iOS 18 or later on iPhone or iPad.

## Docs

| | |
|---|---|
| [Getting started](docs/getting-started.md) | [Ollama](docs/ollama.md) |
| [LM Studio](docs/lm-studio.md) | [vLLM](docs/vllm.md) |
| [llama.cpp](docs/works-with/llama-cpp.md) | [Every server and provider](docs/works-with/README.md) |
| [Cloud providers and your own key](docs/cloud-providers.md) | [On-device models](docs/on-device.md) |
| [Which model fits your iPhone](docs/which-model-fits.md) | [MCP tools](docs/mcp.md) |
| [Files and PDFs](docs/files-and-pdfs.md) | [Troubleshooting](docs/troubleshooting.md) |
| [FAQ](docs/faq.md) | |

## Bugs and feature requests

[Open an issue](https://github.com/EzeLLM/vanta/issues/new/choose) and pick a template. Include your device, iOS version and Vanta version (Settings → About). **Never paste an API key.** You can also write from the app (Settings → About → Contact developer) or to ezel964@icloud.com.

## Quick answers

**Is there an iPhone app for Ollama?** Yes, Vanta connects to Ollama on your Mac, PC, NAS or server, finds it on your Wi-Fi and tests a real reply before you chat. [Ollama guide](docs/ollama.md).

**Can I use my OpenRouter or Anthropic key instead of a subscription?** Yes. You pay your provider for usage; Vanta itself is a one-time purchase.

**Does it work offline?** Yes, with GGUF and MLX models downloaded to the device.

**Is Vanta open source?** No. This repository holds the docs and the issue tracker; the app is closed source.
