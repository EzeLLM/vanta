# Fix a Vanta connection or model problem

Start with a new chat and a short plain text message. If that works, add files and tools one at a time. This separates connection and model problems from features that add their own requirements.

## The server cannot be reached

Use the server's address as seen from the phone. `localhost`, `127.0.0.1` and a loopback-only binding refer to the current device, not your computer. For a LAN server, confirm that it is running, listening on a reachable interface and allowed through the host firewall.

Check Vanta's Local Network permission in iOS Settings. Guest Wi-Fi may isolate devices. If using a VPN, confirm that the phone can reach the server through that VPN. A server that works on its own computer can still be unreachable from the phone.

Use the specific [LM Studio](https://vantaclient.app/docs/lm-studio/), [Ollama](https://vantaclient.app/docs/ollama/) or [vLLM](https://vantaclient.app/docs/vllm/) setup guide.

## The API returns an error

| Error or symptom | What to check |
| --- | --- |
| 401 | A required key is missing, incorrect or expired. |
| 403 | The account, model or proxy denies access. |
| 404 | The API base path is incorrect, or the requested model or route does not exist. |
| 429 | Provider rate limits or usage limits; check the provider's dashboard. |
| No models listed | Check the server's model-list endpoint, key and loaded or installed models. |
| Model not found | Use the exact exposed identifier, including a tag or alias. |
| Timeout before the first reply | The host may be loading a model; check its logs and available resources. |
| Stream stops partway through | Check network stability, proxy streaming behavior and server memory. |

Most compatible servers use a base ending in `/v1`. Vanta adds that path if you enter none, then appends `chat/completions` for chat. If a proxy has a custom path, enter its documented API base. Avoid duplicating `/v1` or pasting the final chat endpoint.

For a slow self-hosted server, the provider's request timeout can be increased. It controls waiting for the first response or the gap between streamed updates; it does not fix an unreachable host or a failed model load.

## A downloaded model will not load

Confirm that the download completed and all required files are still present. Use a supported model architecture and the right format for the selected runtime. For imported GGUF files, try a smaller supported model to separate architecture and memory problems.

Reduce context length and close other demanding apps if memory is tight. Free storage does not establish available RAM. An interrupted download or missing MLX tokenizer and configuration files can also prevent loading.

## Apple Intelligence is unavailable

Read the status shown on the Apple Intelligence model row. Check the OS requirement, device eligibility, Apple Intelligence setting and supported language. The system model may still be downloading or unavailable. Reopen Vanta after changing system settings so its availability check can refresh.

Apple Intelligence in Vanta is text-only. Use a supported remote or MLX vision model for images.

## Tools or images do not work

Check the [capability table](https://vantaclient.app/compatibility/). Enable the required tools and confirm the MCP server is connected. Successful text chat does not prove image or tool support. For MCP, use a real HTTPS MCP endpoint with the correct transport and credentials, as described in the [MCP guide](https://vantaclient.app/docs/mcp/).

## A PDF cannot be processed

Check that it is a valid, unencrypted PDF within the file and page limits. Wait for processing before asking about it. For scans or complex layouts, try a smaller excerpt and inspect the text in the original. [The files guide](https://vantaclient.app/docs/files-and-pdfs/) explains retrieval and image limits.

## Send a useful report

Include the device, OS, Vanta version, exact model and steps to reproduce. **Settings → About → View logs** can help explain the failure. Redact secrets and private content before sharing. [Contact the developer](https://vantaclient.app/support/) with the smallest example that still fails.

---
This page mirrors [https://vantaclient.app/docs/troubleshooting/](https://vantaclient.app/docs/troubleshooting/).
