# Open WebUI iPhone app: use your Open WebUI server from a native iOS client

Vanta is an iPhone and iPad app that can use **Open WebUI** as its backend. Open WebUI exposes the models it serves (Ollama, connected providers, workspace models) through a chat API. Vanta connects to it with your API key and gives you a native app instead of a Safari tab. You can also point Vanta at the model server behind Open WebUI directly.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-SERVER:3000/api` (Docker) or `:8080/api` |
| API key | **Required**: your Open WebUI API key (`sk-…`) |
| Model ID | The model ID as it appears in Open WebUI |
| Model list | `/api/models` |

## Make Open WebUI reachable from your iPhone

Open WebUI's API keys are **off by default**. To get one:

1. An admin turns on **Settings → Admin → Authentication → API Keys** (non-admins also need the API Keys permission).
2. In **Profile → Settings → Account → API keys**, click **Show**, then **Create new secret key**.

Each account has one key; creating a new one replaces the old. Open WebUI calls this API experimental. Its hardening guide recommends a reverse proxy with authentication if you expose the server.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **Something else**.
2. Enter the address: `http://192.168.1.60:3000/api`. Type the `/api` path yourself.
3. Paste your Open WebUI API key.
4. Check the connection and save.
5. Create a model preset: choose a model by its Open WebUI ID, such as `qwen3:8b`.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| 403 | API keys are disabled, you lack the permission, or an endpoint allowlist blocks `/api/models` or `/api/chat/completions`. |
| 401 | The key is wrong or was replaced by a newer one. |
| Reply arrives all at once | The model's **Stream Chat Response** setting in Open WebUI decides streaming. |

## What works

Chat and streaming work through Open WebUI's API, and tools you define in Vanta are passed to the model. Open WebUI's own server-side tools and documents stay in Open WebUI. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/works-with/ollama/) · [LM Studio](https://vantaclient.app/works-with/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/open-webui/](https://vantaclient.app/works-with/open-webui/).
