# LM Studio iPad and iPhone app: a client for your LM Studio server

**Vanta** is an iPad and iPhone app for the models you run in LM Studio. LM Studio does the work on your computer. Vanta connects to its server over your Wi-Fi, lists its models and gives you a native chat app with history, PDFs, and photos for vision models. That lets you use a model that doesn't fit on your iPad or iPhone, and switch the same chat to a model on the device when the computer is asleep.

## What Vanta does for LM Studio

- **Finds LM Studio on your Wi-Fi.** In **Add provider**, choose **On my computer or server**, then **LM Studio**. Vanta finds LM Studio 0.4 or later on your network and fills in the address. iOS asks for Local Network permission first.
- **Shows the setting to turn on.** If your iPad can't reach LM Studio yet, Vanta shows where it is: **Developer › Start server**, then **Serve on Local Network**.
- **Asks for a key only when LM Studio needs one.** If you turned on authentication, Vanta asks for the token. Otherwise there is nothing to type.
- **Gets you a first model.** If LM Studio has no models yet, pick one of three small ones; Gemma 3 1B is the recommended start. Vanta downloads it onto your computer from Hugging Face and shows the progress on your iPad or iPhone.
- **Tests a real reply.** Before you save, Vanta sends one short message to the model and waits for the answer.
- **Keeps your chats on your iPad.** Vanta has no servers and no account. Requests go straight to your LM Studio server.

The guided setup is new in Vanta 3.1.1. Any version connects to LM Studio with its address. [How the guided setup works](https://vantaclient.app/features/guided-setup/) · [Set up LM Studio by hand](https://vantaclient.app/docs/lm-studio/)

<img src="https://vantaclient.app/media/setup-lm-studio.webp" width="720" height="1564" loading="lazy" alt="Vanta showing a drawing of LM Studio's Developer page with the server running and Serve on Local Network on." />

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:1234` (Vanta adds `/v1`) |
| API key | Only if authentication is on in LM Studio |
| Model ID | The identifier LM Studio returns in its model list |
| Model list | `/v1/models` |

The usual port is `1234`; keep the port LM Studio shows. Enter the API base, not the full `/chat/completions` endpoint.

## Photos, tools and staying connected

Photos work with a vision model you've loaded in LM Studio, and tool-capable models can use MCP tools and web search; the model and LM Studio's configuration both have to support it. Keep the computer awake while you chat. Guest Wi-Fi can keep devices apart even when they share a network name. Away from home, use a private VPN such as Tailscale that lets your iPad reach the computer.

Vanta adds the rest on the device: PDFs, memory, group chats with several models, and GGUF and MLX models that run offline when LM Studio is out of reach.

## Buying Vanta

Vanta is a one-time purchase; the App Store shows the price for your region. There is no subscription, no in-app purchase and no Vanta account. The same app also connects to Ollama, llama.cpp, vLLM and other servers, takes OpenRouter and other API keys, and chats with Apple Intelligence on supported devices. It needs iOS 18 or iPadOS 18 or later.

Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/works-with/ollama/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [vLLM](https://vantaclient.app/docs/vllm/) · [Jan](https://vantaclient.app/works-with/jan/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/lm-studio/](https://vantaclient.app/works-with/lm-studio/).
