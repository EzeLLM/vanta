# Together AI iPhone app: use your Together AI key on iOS

Vanta is an iPhone and iPad app that works with **your own Together AI key**. Together's open models become one more source in the same app as your server, on-device models and Apple Intelligence.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.together.ai/v1` |
| API key | Create one in your project's API keys page at [api.together.ai](https://api.together.ai/settings/projects/~current/api-keys) |
| Example models | `meta-llama/Llama-3.3-70B-Instruct-Turbo`, `Qwen/Qwen3.5-9B` (vision) (checked 24 Oct 2026; names change often) |
| Billing | Together AI bills your account directly; Vanta takes nothing |

## Add your Together AI key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Together AI**. Vanta fills in the address.
3. Paste your Together AI API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Together has no free trial; the first credit purchase is at least $15. Model IDs are namespaced (`org/model`). If the model list doesn't load, type the ID.

## What works

Streaming and tool calling work, and vision models accept images. You can switch between Together AI, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/together-ai/](https://vantaclient.app/works-with/together-ai/).
