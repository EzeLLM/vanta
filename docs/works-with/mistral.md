# Mistral API iPhone app: use your own Mistral key on iOS, not Le Chat

Vanta is an iPhone and iPad app that works with **your own Mistral API key**, for people who want Mistral's models without Le Chat. They sit in the same app as your own server, on-device models and Apple Intelligence.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.mistral.ai/v1` |
| API key | Create one in [console.mistral.ai/api-keys](https://console.mistral.ai/api-keys) |
| Example models | `mistral-large-latest`, `mistral-medium-2508`, `mistral-small-2506` (checked 24 Oct 2026; names change often) |
| Billing | Mistral bills your account directly; Vanta takes nothing |

## Add your Mistral key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Mistral**. Vanta fills in the address, `https://api.mistral.ai/v1`.
3. Paste your Mistral API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Mistral's API has a free mode with no credit card required, subject to usage and rate limits.

## What works

Streaming and tool calling work, and Mistral's current models accept images. You can switch between Mistral, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/mistral/](https://vantaclient.app/works-with/mistral/).
