# Cerebras API iPhone app: use your Cerebras key on iOS

Vanta is an iPhone and iPad app that works with **your own Cerebras key**, for very fast inference next to your own server, on-device models and Apple Intelligence.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.cerebras.ai/v1` |
| API key | Create one in the Cerebras Cloud console at [cloud.cerebras.ai](https://cloud.cerebras.ai) |
| Example models | `gpt-oss-120b`, `qwen-3.8-27b` (checked 24 Oct 2026; names change often) |
| Billing | Cerebras bills your account directly; Vanta takes nothing |

## Add your Cerebras key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Cerebras**. Vanta fills in the address, `https://api.cerebras.ai/v1`.
3. Paste your Cerebras API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Cerebras gives a one-time $5 credit after you add a payment method, expiring after 30 days, and has no permanently free tier. Image input is a public preview on one model.

## What works

Streaming and tool calling work. You can switch between Cerebras, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/cerebras/](https://vantaclient.app/works-with/cerebras/).
