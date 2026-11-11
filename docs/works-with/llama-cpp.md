# llama.cpp iPhone app: an iOS client for llama-server

Vanta is an iPhone and iPad app that works as a client for **llama.cpp's `llama-server`**. Your computer runs the GGUF model with llama.cpp; Vanta connects to the server's chat API over your network and gives you a native chat app with history, PDFs and tools. You don't need Ollama or any other layer on top.

## Let Vanta set it up

In Add provider, choose **On my computer or server**, then **llama.cpp**. Vanta shows how to install llama.cpp on your Mac, Windows PC or Linux computer (Homebrew or winget), then gives you one command that downloads a small model and starts the server on your network:

```sh
llama-server -hf ggml-org/gemma-3-1b-it-GGUF --host 0.0.0.0 --port 8080
```

You can change the model before copying it. While the model downloads, Vanta keeps looking for the server on ports 8080 and 9931 for up to ten minutes and shows it as soon as it's ready. [How the guided setup works](https://vantaclient.app/features/guided-setup/).

<img src="https://vantaclient.app/media/setup-llama-cpp.webp" width="300" loading="lazy" alt="Vanta showing a filled-in llama-server command with Copy and Share buttons." />

Prefer to set it up yourself? The manual steps below work too.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:9931/v1` for current builds, `:8080/v1` for Docker or builds before b11521 |
| API key | Optional: start the server with `--api-key` |
| Model ID | The loaded model (its `-m` path, or `--alias` if you set one) |
| Model list | `/v1/models` lists the one loaded model |

## Make llama.cpp reachable from your iPhone

`llama-server` listens only on `127.0.0.1` by default, which your iPhone can't reach. Start it on your network address:

```sh
llama-server -m /path/to/model.gguf --host 0.0.0.0 --port 9931
```

**The default port changed.** Since build b11521 (October 2026), native builds listen on **9931** instead of 8080. The official Docker image still uses 8080 inside the container, and older tutorials say 8080. Use whatever port your server prints at start-up.

For anything beyond your home network, llama.cpp's own guidance is to set an API key and put the server behind a reverse proxy. Don't enable `--tools` or `--agent` on a server other people can reach, since those expose file access.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **llama.cpp**, your computer, and answer **Yes, it's on my computer**.
2. Tap **Type the address instead**, enter `http://192.168.1.20:9931` (Vanta adds `/v1`) and tap **Check this address**. Use your computer's local IP or Tailscale address.
3. Enter the `--api-key` value, or leave the key empty if you didn't set one.
4. Check the connection and save.
5. Create a model preset: choose the loaded model from the list.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| Connection refused | The server is bound to `127.0.0.1`; restart it with `--host 0.0.0.0`. |
| Nothing on port 8080 | Current builds use 9931. Check the port printed at start-up. |
| 401 Invalid API Key | The key in Vanta doesn't match `--api-key`. |
| Tool calls come back as text | Use a model whose chat template supports tools; some need `--chat-template-file`. |

## What works

Streaming works. Tool calling works with models whose chat template supports it, so MCP tools and web search are available. Image input is experimental in llama.cpp and needs a multimodal projector (`--mmproj`). Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/llama-cpp/](https://vantaclient.app/works-with/llama-cpp/).
