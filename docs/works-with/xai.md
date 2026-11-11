# Grok API iPhone app: use your own xAI key on iOS

Vanta is an iPhone and iPad app that works with **your own xAI key**, so you can chat with Grok models next to your own server, on-device models and Apple Intelligence.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.x.ai/v1` |
| API key | Create one in [console.x.ai](https://console.x.ai/team/default/api-keys) (your account needs credits) |
| Example models | `grok-4.7`, `grok-4.3` (checked 24 Oct 2026; names change often) |
| Billing | xAI bills your account directly; Vanta takes nothing |

## Add your xAI key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **xAI**. Vanta fills in the address, `https://api.x.ai/v1`.
3. Paste your xAI API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

xAI now marks its chat completions endpoint as legacy and adds new features to its newer API first. No shutdown date has been announced, and chat works today.

## What works

Streaming and function calling work. Some models accept images. You can switch between xAI, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/xai/](https://vantaclient.app/works-with/xai/).
