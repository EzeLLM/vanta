# Fireworks AI iPhone app: use your Fireworks key on iOS

Vanta is an iPhone and iPad app that works with **your own Fireworks AI key**, next to your own server, on-device models and Apple Intelligence.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://api.fireworks.ai/inference/v1` |
| API key | Create one in [app.fireworks.ai](https://app.fireworks.ai/settings/users/api-keys) |
| Example models | `accounts/fireworks/models/glm-5p3-flash`, `accounts/fireworks/models/kimi-k2p5` (vision) (checked 24 Oct 2026; names change often) |
| Billing | Fireworks AI bills your account directly; Vanta takes nothing |

## Add your Fireworks AI key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Fireworks**. Vanta fills in the address, `https://api.fireworks.ai/inference/v1`.
3. Paste your Fireworks AI API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Fireworks model IDs use the long `accounts/…/models/…` form. Its documented model list lives at a different path, so type the model ID when you create the preset. Fireworks lists no free tier.

## What works

Streaming and tool calling work, and vision models accept images. You can switch between Fireworks AI, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/fireworks/](https://vantaclient.app/works-with/fireworks/).
