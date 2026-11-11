# Groq iPhone app: use your Groq API key on iOS with no subscription

Vanta is an iPhone and iPad app that works with **your own Groq API key**. Groq's fast inference becomes one more model source in the same app as your own server, on-device models and Apple Intelligence. No subscription, and Groq bills its own usage.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.groq.com/openai/v1` |
| API key | Create one in [console.groq.com/keys](https://console.groq.com/keys) |
| Example models | `llama-3.3-70b-versatile`, `qwen/qwen3.8-27b` (vision, preview) (checked 24 Oct 2026; names change often) |
| Billing | Groq bills your account directly; Vanta takes nothing |

## Add your Groq key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Groq**. Vanta fills in the address, `https://api.groq.com/openai/v1`.
3. Paste your Groq API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Groq has a Free tier, and its paid Developer tier needs a payment method. Its model list also contains speech and guard models, so pick a chat model. Groq rejects a few optional request fields, such as names on individual messages.

## What works

Streaming works. Tool calling works, including parallel calls on some models. Vision models accept up to three images. You can switch between Groq, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/groq/](https://vantaclient.app/works-with/groq/).
