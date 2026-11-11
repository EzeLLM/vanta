# Chat with PDFs and images on iPhone, privately

Vanta can use extracted PDF text as conversation context and send images to a compatible vision model. Choose the model before attaching the file: its context size and capabilities determine what the request can include.

## Ask about a PDF

1. Open a chat and use the attachment control to select a PDF.
2. Wait for validation and processing to finish.
3. Ask a focused question, such as “What are the payment deadlines in this contract?”
4. Compare the answer with the relevant passage in the original file.

Vanta extracts text on-device and can use OCR for pages that need it. Smaller documents can fit in the model's context. For larger documents, retrieval supplies relevant passages rather than the entire file. Models that cannot call the PDF search tool can use prepared retrieval context.

PDF questions use text and do not require a vision model. OCR quality, unusual layouts and a limited model context can still affect the result. Ask narrower questions when a broad request misses details.

## File limits

The PDF validator rejects encrypted PDFs, invalid files and files above **100 MiB**, shown as 100 MB in the app. A page limit also applies. Split a large document or use a permitted unencrypted copy when the app cannot process the original.

Renaming a file to `.pdf` does not turn it into a valid PDF. A scan can also contain little readable text even when it opens successfully.

## Ask about an image

Select a remote vision model or one of Vanta's selected vision-capable MLX models. Then attach a photo or screenshot and ask about it.

GGUF and Apple Intelligence do not accept image input in Vanta. Switching to one of those models does not convert the image into a supported input. See the [runtime capability table](https://vantaclient.app/compatibility/) before choosing a model for image work.

## Embeddings are a separate choice

Embeddings can help match document passages by meaning. A configured remote embedding provider receives the text it embeds, even when your chat model is local. Review embedding settings alongside the chat-model settings when deciding where documents may be processed.

## Where file contents go

Local extraction does not mean a remote answer is local. A remote chat model receives the document text or retrieved passages included in its request. A remote vision model receives the image input. Selected MLX vision models process supported images on-device.

For sensitive documents, check the model, embeddings and tools together. Read [privacy and data flow](https://vantaclient.app/privacy/) before attaching them.

If ingestion fails, note the file size, page count and error message. If an answer misses a passage, try a direct question about that passage. [Support](https://vantaclient.app/support/) can help with a reproducible, redacted example.

---
This page mirrors [https://vantaclient.app/docs/files-and-pdfs/](https://vantaclient.app/docs/files-and-pdfs/).
