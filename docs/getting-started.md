# Get started with Vanta

You need one working model to start. It can run on your iPhone or iPad, on a computer you control, or at a cloud provider. Vanta supplies the chat interface; you choose the model and where it runs.

## 1. Choose a starting point

| You already have… | Start with… |
| --- | --- |
| LM Studio on a computer | [The LM Studio guide](https://vantaclient.app/docs/lm-studio/) |
| Ollama on a computer or server | [The Ollama guide](https://vantaclient.app/docs/ollama/) |
| A vLLM server | [The vLLM guide](https://vantaclient.app/docs/vllm/) |
| A cloud API key | [Cloud providers](https://vantaclient.app/docs/cloud-providers/) |
| No server or API account | [On-device models](https://vantaclient.app/docs/on-device/) |

Apple Intelligence can be a quick starting point on an eligible device with the system model available. A supported downloaded model is another option; its size must fit your device's memory.

## 2. Add the source

Open **Settings → Providers → Add provider**. It asks where your models run:

- **OpenRouter:** paste your key.
- **A cloud provider:** pick Anthropic, Groq, Mistral, DeepSeek or another from the list and Vanta fills in the address, or choose **Another provider** and enter its base URL. Then paste your key.
- **On my computer or server:** pick the app. For Ollama, LM Studio, Jan, llama.cpp, Docker Model Runner and vLLM, Vanta finds the server on your Wi-Fi and walks you through the rest, including a first model and a test reply ([guided setup](https://vantaclient.app/features/guided-setup/)). For any other server, pick it or **Something else** and enter its address.

A local address such as `192.168.1.10:1234` belongs to your computer; `localhost` refers to the phone itself.

For downloaded models, open **Local AI** in Settings and choose a supported model or import a GGUF file. Finish its download before starting a local chat.

## 3. Save and select a model

A preset remembers the model and its settings. Create a preset for your connected provider or downloaded model, then select it in **Settings → Models**. The model picker in the chat also lets you switch between saved presets.

Use the exact model identifier supplied by a remote server. A friendly preset name is just for you; it does not change the model the server runs.

## 4. Send a simple first message

Start a new chat and ask: “Say hello in one sentence.” Check that the response finishes. Keep this first check free of files and tools so a connection problem is easy to identify.

After basic chat works, add a [PDF](https://vantaclient.app/docs/files-and-pdfs/), configure [MCP tools](https://vantaclient.app/docs/mcp/), or adjust your preset. Choose a vision-capable model before attaching an image.

## Before using sensitive information

Read [privacy and data flow](https://vantaclient.app/privacy/). A remote model receives the context assembled for the request. A local model keeps inference on-device, but separately configured tools, embeddings and cloud speech can still make network requests.

If the first message fails, use [troubleshooting](https://vantaclient.app/docs/troubleshooting/) or [contact support](https://vantaclient.app/support/).

---
This page mirrors [https://vantaclient.app/docs/getting-started/](https://vantaclient.app/docs/getting-started/).
