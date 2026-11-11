# Gemini API iPhone app: use your own Gemini key in a third-party iOS chat app

Vanta is an iPhone and iPad app that works with **your own Gemini API key** from Google AI Studio. Use Gemini models next to your own server, on-device models and Apple Intelligence, in one app with no subscription.

## Settings at a glance

| Setting | Value |
| --- | --- |
| API base URL | `https://generativelanguage.googleapis.com/v1beta/openai` |
| API key | Create one in [aistudio.google.com/apikey](https://aistudio.google.com/apikey) |
| Example models | `gemini-3.8-flash`, `gemini-3.6-flash`, `gemini-3.5-flash-lite` (checked 24 Oct 2026; names change often) |
| Billing | Gemini API bills your account directly; Vanta takes nothing |

## Add your Gemini API key to Vanta

1. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
2. Choose **Gemini API**. Vanta fills in the address, `https://generativelanguage.googleapis.com/v1beta/openai`.
3. Paste your Gemini API key.
4. Check the connection and save.
5. Create a model preset: choose a model from the list, or type its ID.
6. Start a chat.

## Good to know

Google labels this compatibility endpoint beta. The Gemini API has a free tier for some models, and on the free tier Google may use your content to improve its products. If the model list doesn't load, type the model name.

## What works

Streaming and function calling work, and Gemini accepts images. You can switch between Gemini API, your own server and an on-device model mid-conversation, and use PDFs, memory and group chats with all of them.

Your conversations stay on your iPhone or iPad, whichever model answers: Vanta has no servers and no account, and requests go straight to the address you entered. Stuck? Write to the developer at [ezel964@icloud.com](mailto:ezel964@icloud.com) or use **Settings → About → Contact developer**.

Also works with: [OpenRouter](https://vantaclient.app/works-with/openrouter/) · [Groq](https://vantaclient.app/works-with/groq/) · [DeepSeek](https://vantaclient.app/works-with/deepseek/) · [Gemini](https://vantaclient.app/works-with/gemini/) · [Mistral](https://vantaclient.app/works-with/mistral/) · [all setups](https://vantaclient.app/works-with/)

---
This page mirrors [https://vantaclient.app/works-with/gemini/](https://vantaclient.app/works-with/gemini/).
