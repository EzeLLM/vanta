# Vanta FAQ, setup, supported servers and privacy

## What is Vanta?

Vanta is an all-in-one AI chat app for iPhone and iPad. One app works with:

- cloud models through your own API keys;
- your own server;
- GGUF and MLX models running on the device;
- Apple Intelligence.

It's a one-time App Store purchase by independent developer Ezel Bayraktar. [About Vanta](https://vantaclient.app/about/).

## Which self-hosted servers does Vanta work with?

Any server with a compatible chat API, including:

- [Ollama](https://vantaclient.app/docs/ollama/), [LM Studio](https://vantaclient.app/docs/lm-studio/), [vLLM](https://vantaclient.app/docs/vllm/);
- [llama.cpp's llama-server](https://vantaclient.app/works-with/llama-cpp/), [SGLang](https://vantaclient.app/works-with/sglang/);
- [LiteLLM](https://vantaclient.app/works-with/litellm/), [LocalAI](https://vantaclient.app/works-with/localai/);
- [Jan](https://vantaclient.app/works-with/jan/), [KoboldCpp](https://vantaclient.app/works-with/koboldcpp/);
- [Open WebUI](https://vantaclient.app/works-with/open-webui/), [Hugging Face TGI](https://vantaclient.app/works-with/tgi/);
- [Docker Model Runner](https://vantaclient.app/works-with/docker-model-runner/).

You add the server's address (its base URL) and an optional key. [See all of them](https://vantaclient.app/works-with/).

## Which cloud APIs can I use with my own key?

- OpenRouter is built in.
- Groq, DeepSeek, Mistral, Gemini, Together AI, Fireworks, xAI, Cerebras and other providers with a compatible chat API connect as custom endpoints.

Your provider bills you directly. Vanta takes no cut. [See the cloud setups](https://vantaclient.app/works-with/#cloud-apis).

## Can Vanta run AI models on my iPhone without a server?

Yes. Browse Hugging Face inside Vanta, download a supported GGUF or MLX model, and chat offline once it's downloaded. Selected MLX models can also see images. What fits depends on your device's memory. [Models on your iPhone](https://vantaclient.app/docs/on-device/).

## Can I chat with Apple Intelligence?

Yes, on devices that support Apple Intelligence, running iOS or iPadOS 26 or later with Apple Intelligence turned on. It needs no key and no download inside Vanta. [Apple Intelligence in Vanta](https://vantaclient.app/apple-intelligence/).

## Is there a subscription?

No. Vanta is a one-time purchase, with no Vanta account and no Vanta subscription. Cloud providers and other services you connect may charge for their own usage. [Pricing](https://vantaclient.app/pricing/).

## Where are my conversations stored?

On your iPhone or iPad, whichever model you use. Vanta has no servers and declares no data collection. A chat with an on-device model stays on the device. A chat with your server or a cloud API goes straight to that endpoint, with no Vanta server in between. [Privacy](https://vantaclient.app/privacy/).

## Does it work offline?

Downloaded GGUF and MLX models work offline. Your own server needs a network path to it: home Wi-Fi, a VPN such as Tailscale, or an HTTPS address. Cloud APIs, web search and model downloads need the internet.

## Can I use my home server when I'm away from home?

Yes, if your iPhone can reach it. The usual ways:

- a private VPN such as Tailscale on both devices;
- an HTTPS reverse proxy with authentication.

Don't expose an unauthenticated model server directly to the internet.

## Why can't my iPhone reach `localhost`?

On a real iPhone, `localhost` and `127.0.0.1` mean the phone itself. Use your computer's local network address, for example `http://192.168.1.20:11434`, and make sure the server listens on the network, not only on loopback.

## Does Vanta support MCP, web search and tools?

Yes:

- Remote MCP servers over HTTPS work with models that support tool calling.
- Built-in web search and Deep Search use your own Tavily key.

[MCP](https://vantaclient.app/docs/mcp/) · [Web search](https://vantaclient.app/features/web-search/).

## Can several models talk in one chat?

Yes. Group chats mix local, self-hosted and cloud models, each with its own role. [Group chat](https://vantaclient.app/features/group-chat/).

## Is it hard to set up?

You need one of these to start:

- a downloaded model;
- a reachable server;
- an API key.

The [getting started guide](https://vantaclient.app/docs/getting-started/) walks through each. Vanta sets up Ollama, LM Studio, Jan, llama.cpp, Docker Model Runner and vLLM with you: it finds the server on your Wi-Fi, shows the one setting to turn on, downloads a first model to Ollama or LM Studio and tests a reply. [Guided setup](https://vantaclient.app/features/guided-setup/). If you get stuck, [the developer answers email](https://vantaclient.app/support/).

## Do I need to know my computer's IP address?

Usually not. Vanta finds Ollama, LM Studio, Jan, llama.cpp, Docker Model Runner (with Docker Engine on Linux) or vLLM on your Wi-Fi and fills in the address itself, after iOS asks for Local Network permission. If Vanta can't find it, it shows where your computer lists its address. Any other server connects with its address; each [server guide](https://vantaclient.app/works-with/) shows where to find it.

## How do I contact the developer?

Write to [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer** in the app.

---
This page mirrors [https://vantaclient.app/faq/](https://vantaclient.app/faq/).
