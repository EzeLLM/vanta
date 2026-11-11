# LiteLLM iPhone app: chat with your LiteLLM proxy from iOS

Vanta is an iPhone and iPad app that connects to a **LiteLLM proxy**. LiteLLM sits in front of your models (local servers, cloud providers or both) behind one address and one key. Vanta is the native chat app on the other end, with history, PDFs and tools.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-SERVER:4000` (Vanta adds `/v1`) |
| API key | **Required**: the master key or a virtual key |
| Model ID | The `model_name` you configured, not the upstream model |
| Model list | `/models` lists your configured model names |

## Make LiteLLM reachable from your iPhone

The proxy already listens on all interfaces by default (`--host 0.0.0.0`, port 4000). Two things to know:

- **It won't start without a master key.** Set `general_settings.master_key` or `LITELLM_MASTER_KEY`. The docs recommend it start with `sk-`.
- **The master key is a root credential.** For a phone, create a virtual key (that needs LiteLLM's database) and give Vanta that, not the master key.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **More server software** and **LiteLLM**, and read the short guide.
2. Enter the address: `http://192.168.1.40:4000`, or your HTTPS proxy address. Typing just `192.168.1.40` works too; Vanta adds port 4000.
3. Paste a virtual key, or the master key on a private test setup.
4. Check the connection and save.
5. Create a model preset: choose one of your configured model names, such as `team-llama`.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| Proxy won't start | Set a master key; LiteLLM refuses to run without one. |
| "No connected db." | Virtual keys need LiteLLM's database; until then only the master key works. |
| Model not found | Use the configured `model_name`, not the provider's model ID. |

## What works

Streaming works. Tools and images depend on the model behind each name; LiteLLM forwards them when the backend supports them. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/litellm/](https://vantaclient.app/works-with/litellm/).
