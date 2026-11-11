# Hugging Face TGI iPhone app: an iPad and iPhone client for Text Generation Inference

Vanta is an iPhone and iPad app that connects to **Hugging Face Text Generation Inference (TGI)** through its chat API. It suits teams that already run TGI internally and want a native mobile client with history, PDFs and tools.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-SERVER:8080/v1` (Docker `-p 8080:80`) or `:3000/v1` (bare launcher) |
| API key | Optional: `--api-key` |
| Model ID | `tgi` |
| Model list | `/v1/models` reports the served model |

## Make Hugging Face TGI reachable from your iPhone

TGI listens on all interfaces (`0.0.0.0`) by default. With Docker, it's usually published as `-p 8080:80`, so the address is port 8080 on the host. The docs say to include `/v1` at the end of the URL.

**Note:** TGI is now in maintenance mode and its GitHub repository is archived. Hugging Face recommends vLLM, SGLang or llama.cpp for new deployments, and Vanta works with all three: [vLLM](https://vantaclient.app/docs/vllm/), [SGLang](https://vantaclient.app/works-with/sglang/), [llama.cpp](https://vantaclient.app/works-with/llama-cpp/).

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **More server software** and **Hugging Face TGI**, and read the short guide.
2. Enter the address: `http://10.0.0.5:8080/v1`. TGI has no standard port, so type the one your deployment uses.
3. Enter the `--api-key` value if your server uses one.
4. Check the connection and save.
5. Create a model preset: type or choose `tgi`, which every official example sends.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| 404 | Include `/v1` in the address. |
| Connection refused | Check the Docker port mapping (8080→80). |
| Chat endpoint missing | The chat API needs TGI 1.4.0 or later. |

## What works

Streaming works, tool calling works on the chat endpoint (TGI 1.4.3 and later), and vision-language models accept images. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/tgi/](https://vantaclient.app/works-with/tgi/).
