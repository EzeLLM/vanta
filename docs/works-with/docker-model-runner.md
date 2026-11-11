# Docker Model Runner iPhone app: chat with Docker's local models from iOS

Vanta is an iPhone and iPad app that connects to **Docker Model Runner**, Docker's built-in way to run models. Docker runs the model on your computer; Vanta is the native chat app for it, with history, PDFs and tools.

## Let Vanta set it up

In Add provider, choose **On my computer or server**, then **Docker Model Runner**. Vanta asks which computer you have first, because the answer decides whether it can work:

- **Linux with Docker Engine:** Vanta gives you the command that starts the runner on your network, and `docker model pull ai/smollm2` for a small first model. Then it finds the runner on port 12434 and fills in the address.
- **Docker Desktop on a Mac or Windows PC:** Docker Desktop only accepts connections from the computer it runs on, so Vanta tells you your iPhone can't reach it and offers to set up Ollama instead.

[How the guided setup works](https://vantaclient.app/features/guided-setup/).

<img src="https://vantaclient.app/media/setup-docker.webp" width="300" loading="lazy" alt="Vanta explaining that Docker Desktop can't be reached from an iPhone, with a Use Ollama instead button." />

Prefer to set it up yourself? The manual steps below work too.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:12434/engines/v1`, not `/v1` |
| API key | None: Model Runner ignores the Authorization header |
| Model ID | The full namespaced name, such as `ai/smollm2` |
| Model list | `/engines/v1/models` |

## Make Docker Model Runner reachable from your iPhone

- **Docker Engine:** TCP is on at port 12434, bound to `127.0.0.1`. To reach it from your phone, install the runner on the network: `docker model install-runner --host 0.0.0.0 --port 12434`.
- **Docker Desktop:** host-side TCP is off by default. Turn it on in **Settings → AI → Enable host-side TCP support**, or run `docker desktop enable model-runner --tcp 12434`. Docker documents this for `localhost` only, so your iPhone can't reach it without a proxy on your computer. On a Mac or Windows PC, Ollama is the simpler choice.

Docker's warning applies: the Model Runner API isn't authenticated, so anyone who can reach it can pull and run models. Keep it on a trusted network, or put an authenticating HTTPS proxy in front.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **Docker Model Runner**, **Linux**, and answer **Yes, it's on my computer**.
2. Tap **Type the address instead**, enter `http://192.168.1.20:12434` (Vanta adds `/engines/v1`, not `/v1`) and tap **Check this address**.
3. Leave the key empty (or use your proxy's key).
4. Check the connection and save.
5. Create a model preset: choose a pulled model with its namespace, such as `ai/qwen2.5`.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| Connection refused | TCP isn't enabled, or the port is taken; check `docker model status`. |
| Model not found | Pull it first, and include the namespace (`ai/…`). |
| First reply is slow | The model loads on the first request. |

## What works

Streaming works. Tool calling works with llama.cpp-backed models that support it, and multimodal models accept images. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/docker-model-runner/](https://vantaclient.app/works-with/docker-model-runner/).
