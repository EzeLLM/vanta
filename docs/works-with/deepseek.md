# DeepSeek API iPhone app: use your own DeepSeek key on iOS

Vanta is an iPhone and iPad app that works with **your own DeepSeek API key**. Chat with DeepSeek's models in the same app as your own server, on-device models and Apple Intelligence. DeepSeek bills your account directly, with no Vanta subscription.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.deepseek.com/v1` |
| API key | Create one in [platform.deepseek.com/api_keys](https://platform.deepseek.com/api_keys) |
| Example models | `deepseek-flash`, `deepseek-v4-pro` (checked 24 Oct 2026; names change often) |
| Billing | DeepSeek bills your account directly; Vanta takes nothing |

## Add your DeepSeek key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **DeepSeek**. Vanta fills in the address, `https://api.deepseek.com/v1`.
3. Paste your DeepSeek API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

DeepSeek documents `https://api.deepseek.com` as its base. Vanta adds `/v1` to an address without a path, and DeepSeek's API answers at `/v1` too. The older names `deepseek-chat` and `deepseek-reasoner` no longer appear in its docs. Its frequency and presence penalties have no effect.

## What works

Streaming and tool calling work. `deepseek-flash` accepts images in user messages. You can switch between DeepSeek, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/deepseek/](https://vantaclient.app/works-with/deepseek/).
