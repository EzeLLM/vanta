# SGLang iPhone app: a native iOS client for your SGLang server

Vanta is an iPhone and iPad app that works as a native client for **SGLang**. Your GPU server runs the model with SGLang; Vanta connects to its chat API and gives you a mobile chat app with history, PDFs, tools and group chats.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-SERVER:30000/v1` |
| API key | Optional: start with `--api-key` |
| Model ID | The Hugging Face model path you served (or `--served-model-name`) |
| Model list | `/v1/models` |

## Make SGLang reachable from your iPhone

SGLang binds to `127.0.0.1` unless you pass `--host`. SGLang's quickstart serves on every interface:

```sh
sglang serve Qwen/Qwen3-8B --host 0.0.0.0 --port 30000
```

Older guides use `python3 -m sglang.launch_server --model-path … --host 0.0.0.0 --port 30000`, which still works. Wait for "The server is fired up and ready to roll!" before connecting. For tools, launch with a `--tool-call-parser` that matches your model (for example `qwen25` or `llama3`).

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **More server software** and **SGLang**, and read the short guide.
2. Enter the address: `http://192.168.1.30:30000` (Vanta adds `/v1`). Typing just `192.168.1.30` works too; Vanta adds port 30000.
3. Enter the `--api-key` value, or leave it empty.
4. Check the connection and save.
5. Create a model preset: choose the served model; its ID is the model path, such as `Qwen/Qwen3-8B`.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| Connection refused | Add `--host 0.0.0.0`, or check the port and firewall. |
| Tool calls arrive as plain text | Start SGLang with `--tool-call-parser` for your model family. |
| Model not found | Use the exact ID from `/v1/models`. |

## What works

Streaming works. Tools work when SGLang runs with a tool-call parser. Vision models such as Qwen2.5-VL accept images. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/works-with/ollama/) · [LM Studio](https://vantaclient.app/works-with/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/sglang/](https://vantaclient.app/works-with/sglang/).
