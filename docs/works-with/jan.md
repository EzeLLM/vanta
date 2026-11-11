# Jan iPhone app: connect to Jan's Local API Server from iOS

Vanta is an iPhone and iPad app that connects to **Jan's Local API Server**. Jan runs the model on your Mac or PC; Vanta talks to it over your network and gives you a native chat app with history, PDFs and tools.

## Let Vanta set it up

In Add provider, choose **On my computer or server**, then **Jan**. Vanta looks for Jan on your Wi-Fi and fills in your computer's numeric address, which Jan accepts. If Jan isn't reachable yet, Vanta walks you through it: first a downloaded model, because Jan's server won't start without one, then the setting (**Settings › Local API Server › Server Host: 0.0.0.0 › Start Server**). [How the guided setup works](https://vantaclient.app/features/guided-setup/).

<img src="https://vantaclient.app/media/setup-jan.webp" width="300" loading="lazy" alt="Vanta showing a drawing of Jan's Local API Server settings with Server Host set to 0.0.0.0." />

Prefer to set it up yourself? The manual steps below work too.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `http://YOUR-COMPUTER:1337/v1` |
| API key | Optional, but Jan recommends one when it listens on the network |
| Model ID | The ID of a model available in Jan |
| Model list | `/v1/models` |

## Make Jan reachable from your iPhone

In Jan, open **Settings → Local API Server**:

1. Choose a default model; the server won't start without a local model.
2. Set **Server Host** to `0.0.0.0` so other devices on your network can connect. Jan's default, `127.0.0.1`, is this computer only.
3. Set an **API Key** (strongly advised once it's on the network).
4. Start the server.

**Using Tailscale or a domain name?** Jan only accepts requests addressed to localhost or a private LAN IP. A Tailscale IP, a MagicDNS name or a reverse-proxy hostname gets a `403 Invalid host header` until you add it to **Trusted Hosts**.

On a real iPhone, `localhost` means the phone itself, so always use your computer's network address. Away from home, use a private VPN such as Tailscale, or an HTTPS reverse proxy with authentication.

## Add it to Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **Jan**, and answer **Yes, it's on my computer**.
2. Tap **Type the address instead**, enter `http://192.168.1.20:1337` (Vanta adds `/v1`) and tap **Check this address**. Use the numbers; Jan doesn't accept `.local` names.
3. Enter Jan's API key, or leave it empty if you didn't set one.
4. Check the connection and save.
5. Create a model preset: choose the model by its Jan ID.
6. Start a chat.

## Common problems

| Symptom | Fix |
| --- | --- |
| 403 Invalid host header | Add the Tailscale IP or hostname you're using to Jan's Trusted Hosts. |
| Connection refused | The server isn't started, or Server Host is still `127.0.0.1`. |
| 404 | Wrong model ID, or you changed Jan's API prefix from `/v1`. |

## What works

Chat works with any model Jan serves. Jan returns MCP tool calls to the client by default, so tool support depends on the model. Jan doesn't document streaming or image input for this server. Vanta adds the rest on the phone: PDFs, memory, group chats, and switching to an on-device model when you're offline.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [Ollama](https://vantaclient.app/docs/ollama/) · [LM Studio](https://vantaclient.app/docs/lm-studio/) · [vLLM](https://vantaclient.app/docs/vllm/) · [llama.cpp](https://vantaclient.app/works-with/llama-cpp/) · [LocalAI](https://vantaclient.app/works-with/localai/) · [Open WebUI](https://vantaclient.app/works-with/open-webui/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/jan/](https://vantaclient.app/works-with/jan/).
