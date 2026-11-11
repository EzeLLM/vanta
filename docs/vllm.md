# vLLM iPhone app: an iOS client for your vLLM server

Vanta can use a chat model served by vLLM through its OpenAI-compatible API. vLLM runs the model on your host; the phone is the client. Use a model with a supported chat template and a host with enough resources to serve it.

## Let Vanta set it up

In Add provider, choose **On my computer or server**, then **vLLM**. Vanta first asks whether you have a Linux computer with an NVIDIA graphics card, since vLLM needs one; if not, it suggests Ollama instead. Then it gives you the install commands and one `vllm serve` command with a small model filled in, which you can change. While the first start downloads the model, Vanta keeps looking for the server on port 8000 for up to ten minutes and shows it as soon as it's ready. [How the guided setup works](https://vantaclient.app/features/guided-setup/).

Prefer to set it up yourself? The manual steps below work too.

## Prepare the server

Follow the [vLLM quickstart](https://docs.vllm.ai/en/latest/getting_started/quickstart/) to install vLLM and serve a model. Its normal API port is `8000`. Use `--host` and `--port` to choose the interface and port; a loopback-only server cannot be reached directly from your phone.

The API base is typically `http://YOUR_SERVER:8000/v1`. vLLM documents chat support and authentication in its [OpenAI-compatible server guide](https://docs.vllm.ai/en/latest/serving/online_serving/openai_compatible_server/).

For a private LAN, allow only the intended devices through the firewall. For access over the internet, use an authenticated HTTPS reverse proxy or a private VPN. vLLM warns that `--api-key` does not protect every endpoint on its HTTP server, so that option alone is not a complete public deployment boundary.

## Add the provider

1. Open **Settings → Providers → Add provider**, choose **On my computer or server**, then **vLLM**, answer **Yes, I have one**, and answer **Yes, it's on my computer**.
2. Tap **Type the address instead**.
3. Enter the address, for example `http://192.168.1.10:8000`, and tap **Check this address**. For an HTTPS proxy, enter its API base and choose **Use this address anyway** if Vanta can't recognise it.
4. Enter the server or proxy key if authentication is required.
5. Check and save the provider.
6. Create a model preset with the identifier reported by `/v1/models`, select it and send a short message.

If you configured a served-model alias, use that exposed identifier. Do not assume the local model directory or a display name is the API identifier.

Vanta adds `/v1` when the address has no path. It preserves custom paths, so include the API path your reverse proxy expects. Do not paste the full `/chat/completions` URL into the base-address field.

## Check reachability

For a server without API authentication:

```sh
curl http://192.168.1.10:8000/v1/models
```

For an authenticated server, send the appropriate bearer token header. A successful list request verifies the address and access from the device making the request. Then check a basic chat inside Vanta.

## Common problems

| Symptom | Check |
| --- | --- |
| 401 or 403 | The key and proxy access policy match the saved provider. |
| 404 | The base path reaches the API rather than a website or a duplicated `/v1` prefix. |
| Chat-template error | The served model has a suitable chat template in vLLM. |
| Model identifier rejected | Use the exact name exposed by the server's model list. |
| Streaming stalls | The model has loaded and the proxy permits streaming responses without an early timeout. |

Tools and images also require appropriate model and server support; an OpenAI-compatible API does not make every served model multimodal or tool-capable.

For related limits, see [compatibility](https://vantaclient.app/compatibility/), [privacy](https://vantaclient.app/privacy/) and [troubleshooting](https://vantaclient.app/docs/troubleshooting/). These are documented configuration steps, not newly measured performance results.

---
This page mirrors [https://vantaclient.app/docs/vllm/](https://vantaclient.app/docs/vllm/).
