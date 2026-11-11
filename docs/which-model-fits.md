# Which local AI model can my iPhone run? Models by iPhone and memory

How big a local model your iPhone can run depends mostly on its **memory (RAM)**. Vanta is an iPhone and iPad app that runs GGUF and MLX models on the device. It reads your device's actual memory, recommends models that fit, and shows a fit rating on every model before you download it.

## The short answer

| Device memory | Examples (reported) | What Vanta recommends |
| --- | --- | --- |
| 12 GB | iPhone 17 Pro, iPhone 17 Pro Max, iPhone Air | Qwen3.5 4B (MLX, sees images) as the main pick, Qwen3.5 2B as the fast one. Larger 7B–8B models at 4-bit are worth trying; check their fit rating. |
| 8 GB | iPhone 17, iPhone 16 series, iPhone 16e, iPhone 15 Pro, iPhone 15 Pro Max | Qwen3.5 4B as the main pick, Qwen3.5 2B as the fast one. |
| 6 GB | iPhone 15, iPhone 15 Plus, iPhone 14 series, iPhone 13 Pro | Qwen3.5 4B is offered but rated a tight fit; Qwen3.5 2B is the comfortable choice. |
| 4 GB | iPhone 13, iPhone 13 mini, iPhone SE (3rd generation) | Qwen3.5 2B only. |

Apple doesn't publish iPhone memory. These figures are widely reported, and Vanta measures the device you actually have. iPads follow the same rule by memory.

The featured models are:

- **Qwen3.5 4B** in MLX format, about 3.1 GB, which can also look at images;
- **Qwen3.5 2B**, about 1.75 GB, which also sees images.

Both are Apache-2.0 licensed and hosted on Vanta's own Hugging Face mirror, so the download source can't move.

## What actually limits you

- **Model size.** At 4-bit, a model takes roughly 0.6 to 0.9 GB per billion parameters on disk (Qwen3.5 4B is about 3.1 GB), plus working memory while it runs.
- **Context length.** A longer context window uses more memory. If a model fails to load or the app closes, lower the context length first.
- **iOS itself.** iOS keeps memory for the system and other apps, so a phone can't give all of its RAM to one model.
- **Format.** Selected MLX models in Vanta can see images or call tools. GGUF models are text-only and don't call tools.

## Apple Intelligence: no download at all

On devices that support Apple Intelligence, running iOS 26 or later, Vanta can also chat with Apple's own on-device model. There's nothing to download inside Vanta, no key and no cost. [Apple Intelligence in Vanta](https://vantaclient.app/apple-intelligence/).

## Bigger models: use your own computer

If you want a 30B or 70B model, run it on your Mac or PC with [Ollama](https://vantaclient.app/docs/ollama/), [LM Studio](https://vantaclient.app/docs/lm-studio/) or [llama.cpp](https://vantaclient.app/works-with/llama-cpp/), and use Vanta as the iPhone client. The model doesn't need to fit on the phone when your server does the work, and you can switch between it and an on-device model in the same app.

## Get a model onto your iPhone

1. Open **Settings → Local AI**.
2. Pick one of the recommended models, or browse Hugging Face for GGUF or MLX and check its fit rating.
3. Download it, then start a chat. It works offline from then on.

More detail: [run LLMs offline on iPhone](https://vantaclient.app/docs/on-device/), [compatibility](https://vantaclient.app/compatibility/).

---
This page mirrors [https://vantaclient.app/docs/which-model-fits/](https://vantaclient.app/docs/which-model-fits/).
