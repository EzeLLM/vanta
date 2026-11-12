# Connect LM Studio to your iPad or iPhone: Serve on Local Network, port 1234

Choosing an app? See [Vanta for LM Studio](https://vantaclient.app/works-with/lm-studio/).

Vanta can chat with a model running in LM Studio on your computer. LM Studio handles inference; your iPhone or iPad connects to its OpenAI-compatible API. This lets you use a model that does not fit on your phone.

## Let Vanta set it up

In Add provider, choose **On my computer or server**, then **LM Studio**. Vanta finds LM Studio 0.4 or later on your Wi-Fi, fills in the address and asks for a key only if LM Studio requires one. If your iPhone can't reach it yet, Vanta shows where the setting is: **Developer › Start server**, then **Serve on Local Network**. If LM Studio has no models yet, Vanta downloads a small one onto your computer from Hugging Face, then tests a reply. [How the guided setup works](https://vantaclient.app/features/guided-setup/).

<img src="https://vantaclient.app/media/setup-lm-studio.webp" width="720" height="1564" loading="lazy" alt="Vanta showing a drawing of LM Studio's Developer page with the server running and Serve on Local Network on." />

Prefer to set it up yourself? The manual steps below work too.

## Prepare LM Studio

Install LM Studio, download a chat model and load it. Open its server controls, enable **Serve on Local Network**, and start the server. Use the network address displayed by LM Studio. The usual port is `1234`; keep the port your server actually shows. LM Studio documents the [LAN setting](https://lmstudio.ai/docs/developer/core/server/serve-on-network) and [server options](https://lmstudio.ai/docs/developer/core/server/settings).

Keep your computer awake. Connect the phone and computer to the same trusted network, or use a private VPN that lets the phone reach the computer. If LM Studio requires authentication, have its token ready.

## Add the provider in Vanta

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **LM Studio**, and answer **Yes, it's on my computer**.
2. Tap **Type the address instead**.
3. Enter the address, for example `http://192.168.1.10:1234`, and tap **Check this address**.
4. Continue and enter the server's API token if authentication is enabled. Otherwise leave the key empty.
5. Check the connection, save the provider and create a model preset.
6. Use the model identifier returned by LM Studio, then select the preset in **Settings → Models**.

Replace `192.168.1.10` with your computer's address. Vanta adds `/v1` when you enter an address without a path. An explicitly entered path is preserved. Enter the API base, rather than the full `/chat/completions` endpoint.

## Check the connection

From another device on the same network, this request should return a model list:

```sh
curl http://192.168.1.10:1234/v1/models
```

If authentication is enabled, add the bearer token header required by your server. Use LM Studio's [model-list documentation](https://lmstudio.ai/docs/developer/openai-compat/models) to check the expected response. In Vanta, send a short message in a new chat and confirm that it completes.

## Common problems

| Symptom | Check |
| --- | --- |
| Server cannot be reached | The server is running, LAN serving is enabled, the computer is awake, and its firewall allows the server port. |
| Works on the computer only | Replace `localhost` or `127.0.0.1` with the computer's reachable LAN address. |
| No models appear | Load a model and check `/v1/models`; make sure the saved URL points to the API. |
| Authentication fails | Use the server's API token and check whether authentication is enabled. |
| Text works but tools or images fail | The selected model and LM Studio configuration must support that capability. |

Guest Wi-Fi can isolate devices even when they share a network name. Also check Vanta's Local Network permission in iOS Settings if access was denied.

## Where the conversation goes

Vanta sends the assembled request directly to your LM Studio server. The model runs on that computer. External tools or embedding services you configure can add separate destinations. Use authentication and a secured connection or private VPN for access beyond a trusted LAN.

These steps follow current LM Studio documentation and Vanta's connection flow; they are not a new device-performance test. See [compatibility](https://vantaclient.app/compatibility/), [privacy](https://vantaclient.app/privacy/) and [troubleshooting](https://vantaclient.app/docs/troubleshooting/).

---
This page mirrors [https://vantaclient.app/docs/lm-studio/](https://vantaclient.app/docs/lm-studio/).
