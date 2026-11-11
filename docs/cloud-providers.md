# Use your own API key on iPhone: OpenRouter and compatible cloud APIs

Vanta can connect to OpenRouter or another provider that exposes an OpenAI-compatible chat API. You supply the endpoint and your API key. The provider runs the model and handles API billing; Vanta sends requests directly to the endpoint you select.

## Use OpenRouter

1. Create an API key with OpenRouter and review its billing settings.
2. Open **Settings → Providers → OpenRouter** in Vanta and save the key.
3. Create a model preset, select OpenRouter as its source and choose a model.
4. Select the preset in **Settings → Models** and send a short message.

OpenRouter uses the API base `https://openrouter.ai/api/v1`. Its [official quickstart](https://openrouter.ai/docs/quickstart) explains its API and model identifiers. Tools, image input and generation settings depend on the selected model and provider route.

## Add a custom provider

1. Get the provider's **OpenAI-compatible API base URL** and an API key.
2. Open **Settings → Providers → Add provider** and choose **A cloud provider**.
3. Pick your provider from the list and Vanta fills in the address, or choose **Another provider** and enter its base URL.
4. Enter the key, check the connection and save the provider.
5. Create a model preset with a model identifier supplied by the provider.
6. Select the preset and verify a plain text conversation first.

Use the provider's documented base path. Vanta adds `/v1` if you enter no path, and preserves an explicit path. For example, an API under `/api/v1` must keep that full path. The app appends `chat/completions` for chat requests; do not enter that final endpoint in the base field.

## Compatibility matters more than the brand

A provider may offer several different APIs. A native API using a different message format is not interchangeable with an OpenAI-compatible endpoint. If the provider does not offer the compatible API, use a compatible gateway such as OpenRouter or your own gateway.

A successful model-list check confirms discovery and access. Test chat, then test any image or tool feature you need. Support for one feature does not establish support for the others.

## Keys and costs

Vanta stores API keys in the device Keychain. Never put a key into the server URL, a system prompt or a support screenshot.

The provider may require credit, a billing account or permission for a particular model. A subscription to a consumer chat application may not grant API access. [Vanta's app purchase](https://vantaclient.app/pricing/) does not include third-party API usage.

## What is sent

The remote model receives the context assembled for your request, which can include history, prompts, memories, document excerpts and tool results. Review [privacy and data flow](https://vantaclient.app/privacy/) and the provider's policy before sending sensitive information.

For 401, 403, 404 or model errors, see [troubleshooting](https://vantaclient.app/docs/troubleshooting/).

---
This page mirrors [https://vantaclient.app/docs/cloud-providers/](https://vantaclient.app/docs/cloud-providers/).
