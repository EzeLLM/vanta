# Ollama iPhone app: an iOS client for your Ollama server

**Vanta** is an iPhone and iPad app for your own Ollama server. Ollama runs the model on your Mac, Windows PC or Linux computer. Vanta finds it on your Wi-Fi, lists the models you've installed and gives you a native chat app with history, PDFs and tools. When the server is off or out of reach, you can switch the same chat to a model that runs on the phone.

## What Vanta does for Ollama

- **Finds Ollama on your Wi-Fi.** In **Add provider**, choose **On my computer or server**, then **Ollama**. Vanta looks for Ollama on port 11434 on your network and fills in the address itself. iOS asks for Local Network permission first.
- **Shows the one switch.** If your iPhone can't reach Ollama yet, Vanta shows the **Expose Ollama to the network** switch in Ollama's settings on a Mac or Windows PC, or one command on Linux.
- **Gets you a first model.** If Ollama has no models yet, pick Gemma 3 1B (806 MB, recommended), Llama 3.2 3B or Gemma 3 4B. Vanta downloads it onto your computer and shows the progress on your phone.
- **Tests a real reply.** Before you save, Vanta sends one short message to the model and waits for the answer.
- **Works with the models you already have.** Vanta lists every model installed in Ollama. Each preset keeps its own system prompt, temperature and context length.
- **Keeps your chats on your iPhone.** Vanta has no servers and no account. Requests go straight from your phone to your Ollama server.

The guided setup is new in Vanta 3.1.1. Any version connects to Ollama with its address. [How the guided setup works](https://vantaclient.app/features/guided-setup/) · [Set up Ollama by hand](https://vantaclient.app/docs/ollama/)

<img src="https://vantaclient.app/media/setup-found.webp" width="720" height="1564" loading="lazy" alt="Vanta's Find screen reporting Found Ollama, with the computer's local network address filled in." />

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:11434` (Vanta adds `/v1`) |
| API key | Not needed for an ordinary Ollama server on your network |
| Model ID | The installed name with its tag, as `ollama list` shows it |
| Model list | `/v1/models` |

Vanta uses Ollama's compatible chat API under `/v1`, not its native `/api` path.

## Away from home

On a real iPhone, `localhost` means the phone itself, so Vanta uses your computer's network address. Away from home, connect through Tailscale or another private VPN, or put Ollama behind an HTTPS reverse proxy with authentication. A blank API key does not protect a server that is open to the internet.

## What works with Ollama

Chat works with any model Ollama serves. Photos work with a vision model, and tool-capable models can use MCP tools and web search; both depend on the model and on what Ollama's compatible API supports. Vanta adds the rest on the phone: PDFs, memory, group chats with several models, and GGUF and MLX models that run offline when your server is out of reach.

## Buying Vanta

Vanta is a one-time purchase; the App Store shows the price for your region. There is no subscription, no in-app purchase and no Vanta account. The same app also connects to LM Studio, llama.cpp, vLLM and other servers, takes OpenRouter and other API keys, and chats with Apple Intelligence on supported devices. It needs iOS 18 or iPadOS 18 or later.

Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [LM Studio](https://vantaclient.app/works-with/lm-studio/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [vLLM](https://vantaclient.app/docs/vllm/) · [Jan](https://vantaclient.app/works-with/jan/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/ollama/](https://vantaclient.app/works-with/ollama/).
