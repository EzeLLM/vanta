# LocalAI iPhone app: an iOS client for LocalAI in Docker

Vanta is an iPhone and iPad app that works as a client for **LocalAI**. LocalAI runs models on your computer, server or NAS, often in Docker. Vanta connects to its chat API and gives you a native mobile chat app with history, PDFs and tools.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-SERVER:8080/v1` |
| API key | Optional: `LOCALAI_API_KEY` or `--api-keys` |
| Model ID | The model's configured name (from the gallery or your YAML) |
| Model list | `/v1/models` |

## Make LocalAI reachable from your iPhone

LocalAI's default address `:8080` already listens on every interface. With Docker, publish the port:

```sh
docker run -p 8080:8080 --name local-ai -ti localai/localai:latest
```

LocalAI's guidance: never expose it directly to the internet without TLS. Use your LAN, a VPN such as Tailscale, or an HTTPS reverse proxy. Once you set API keys, every endpoint needs one, including the model list.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **More server software** and **LocalAI**, and read the short guide.
2. Enter the address: `http://192.168.1.50:8080` (Vanta adds `/v1`). Typing just `192.168.1.50` works too; Vanta adds port 8080.
3. Enter a LocalAI API key if you set one, or leave it empty.
4. Check the connection and save.
5. Create a model preset: choose a model by the name `/v1/models` reports.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| 404 model not found | The name must match `/v1/models` exactly. |
| Connection refused | Check the published Docker port and the NAS firewall. |
| 401 | You set API keys; add one in Vanta. |

## What works

Streaming works. Tool calling works across LocalAI's backends. Vision models accept images. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/localai/](https://vantaclient.app/works-with/localai/).
