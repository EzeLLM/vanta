# Everything Vanta works with: every AI server, API and on-device model in one iPhone app

Vanta is the all-in-one AI chat app for iPhone and iPad. It works with:

- **your own server**, from Ollama to vLLM;
- **cloud models** through your own API keys;
- **models that run on the iPhone itself**;
- **Apple Intelligence**.

You can use all of them in one app and switch between them mid-conversation. Every setup below works in the current App Store version. Your conversations stay on your iPhone whichever one answers, and you buy the app once.

Any server or provider with a compatible chat API works the same way. Enter its **base URL** (the custom endpoint) and an optional key, and Vanta lists its models. The pages below have the exact address, port and gotchas for each one.

## Your own server

| Server | Base URL to enter | Key |
| --- | --- | --- |
| [Ollama](https://vantaclient.app/works-with/ollama/) | `http://YOUR-COMPUTER:11434` | Not needed on your LAN |
| [LM Studio](https://vantaclient.app/works-with/lm-studio/) | `http://YOUR-COMPUTER:1234` | Optional |
| [vLLM](https://vantaclient.app/docs/vllm/) | `http://YOUR-SERVER:8000` | Optional |
| [llama.cpp (llama-server)](https://vantaclient.app/works-with/llama-cpp/) | `http://YOUR-COMPUTER:9931` (8080 in Docker or older builds) | Optional |
| [SGLang](https://vantaclient.app/works-with/sglang/) | `http://YOUR-SERVER:30000` | Optional |
| [LiteLLM proxy](https://vantaclient.app/works-with/litellm/) | `http://YOUR-SERVER:4000` | Required |
| [LocalAI](https://vantaclient.app/works-with/localai/) | `http://YOUR-SERVER:8080` | Optional |
| [Jan](https://vantaclient.app/works-with/jan/) | `http://YOUR-COMPUTER:1337` | Recommended |
| [KoboldCpp](https://vantaclient.app/works-with/koboldcpp/) | `http://YOUR-COMPUTER:5001` | Optional |
| [Open WebUI](https://vantaclient.app/works-with/open-webui/) | `http://YOUR-SERVER:3000/api` | Required |
| [Hugging Face TGI](https://vantaclient.app/works-with/tgi/) | `http://YOUR-SERVER:8080/v1` | Optional |
| [Docker Model Runner](https://vantaclient.app/works-with/docker-model-runner/) | `http://YOUR-COMPUTER:12434/engines/v1` | None |

Vanta adds `/v1` to an address that has no path. On a real iPhone, `localhost` is the phone itself, so use your computer's network address. Away from home, use Tailscale or another private VPN, or an HTTPS reverse proxy. Vanta finds Ollama, LM Studio, Jan, llama.cpp, Docker Model Runner and vLLM on your Wi-Fi, fills in the address and shows the one setting to turn on, so you usually won't need this table for those six. [Guided setup](https://vantaclient.app/features/guided-setup/).

## Cloud APIs

| Provider | Base URL | Notes |
| --- | --- | --- |
| [OpenRouter](https://vantaclient.app/works-with/openrouter/) | Built in, just paste your key | Hundreds of models from many labs through one key, including free ones |
| [Groq](https://vantaclient.app/works-with/groq/) | `https://api.groq.com/openai/v1` | Free tier; very fast |
| [DeepSeek](https://vantaclient.app/works-with/deepseek/) | `https://api.deepseek.com/v1` | |
| [Mistral](https://vantaclient.app/works-with/mistral/) | `https://api.mistral.ai/v1` | Free API mode |
| [Gemini API](https://vantaclient.app/works-with/gemini/) | `https://generativelanguage.googleapis.com/v1beta/openai` | Free tier for some models |
| [Together AI](https://vantaclient.app/works-with/together-ai/) | `https://api.together.ai/v1` | Prepaid credits |
| [Fireworks AI](https://vantaclient.app/works-with/fireworks/) | `https://api.fireworks.ai/inference/v1` | Type the model ID |
| [xAI (Grok)](https://vantaclient.app/works-with/xai/) | `https://api.x.ai/v1` | |
| [Cerebras](https://vantaclient.app/works-with/cerebras/) | `https://api.cerebras.ai/v1` | Trial credit |

Each provider bills its own usage. Vanta never sits between you and the provider and takes no cut. Perplexity ended chat-completions support for its Sonar API in September 2026, so use Perplexity's models through OpenRouter.

## On your iPhone

| Runtime | What it is |
| --- | --- |
| [GGUF models](https://vantaclient.app/docs/on-device/) | Download from Hugging Face inside Vanta, or import a file. Text chat, offline. |
| [MLX models](https://vantaclient.app/docs/on-device/) | Apple-silicon models from Hugging Face; selected ones see images or call tools. Offline. |
| [Apple Intelligence](https://vantaclient.app/apple-intelligence/) | Apple's on-device model. No download, no key, no cost. |

Not sure what your phone can run? [Which model fits your iPhone](https://vantaclient.app/docs/which-model-fits/).

## One app for all of it

- **Switch models without switching apps.** Your server at home, a cloud model on the road, an on-device model on a plane.
- **Put several in one group chat.** [Group chat](https://vantaclient.app/features/group-chat/) lets a local model and a cloud model review each other.
- **Same tools everywhere.** PDFs, memory, MCP tools and web search work across sources, wherever the model supports them.
- **Talk to the developer.** Write to [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

---
This page mirrors [https://vantaclient.app/works-with/](https://vantaclient.app/works-with/).
