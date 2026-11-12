# KoboldCpp iPhone app: use KoboldCpp from your iPhone or iPad

Vanta is an iPhone and iPad app that connects to **KoboldCpp** through its chat API. KoboldCpp runs your GGUF model on your computer; Vanta gives you a native mobile chat app for it, with history, PDFs and tools.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:5001/v1` |
| API key | Optional: KoboldCpp's `--password` doubles as the key |
| Model ID | `kcpp`, the name KoboldCpp's own API examples use, or the model listed by `/v1/models` |
| Model list | `/v1/models` |

## Make KoboldCpp reachable from your iPhone

KoboldCpp accepts connections on all routable interfaces unless you restrict it with `--host`, so on the same Wi-Fi your phone can usually reach `http://192.168.x.x:5001`. If it can't, start KoboldCpp with `--host` set to your computer's LAN IP.

For access from outside, KoboldCpp offers `--remotetunnel` (a Cloudflare tunnel) and `--ssl` for HTTPS. Set `--password` on anything other people could reach.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **Something else**.
2. Enter the address: `http://192.168.1.20:5001` (Vanta adds `/v1`).
3. Enter your `--password`, or leave it empty.
4. Check the connection and save.
5. Create a model preset: choose the model listed, or type `kcpp`.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| Connection refused | Wait for the model to finish loading, then check Wi-Fi and the firewall. |
| 401 | The key in Vanta must match `--password`. |
| Short replies | Raise `--defaultgenamt` if your client doesn't send a length. |

## What works

Streaming and tool calling are part of KoboldCpp's chat API. Images need a multimodal projector (`--mmproj`). Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/works-with/ollama/) · [LM Studio](https://vantaclient.app/works-with/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/koboldcpp/](https://vantaclient.app/works-with/koboldcpp/).
