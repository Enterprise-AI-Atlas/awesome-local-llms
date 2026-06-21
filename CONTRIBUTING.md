# Contributing

Contributions are welcome. Please read this guide before opening a pull request.

## What belongs in this list

This registry is for resources that help people run, serve, manage, fine-tune, or optimize Large Language Models on local hardware. Acceptable entries include:

- Local inference engines and model servers (CPU, GPU, Apple Silicon, edge).
- Quantized model families and community quantization hubs.
- Local chat UIs and frontends that connect to on-device models.
- Model management, conversion, and quantization utilities.
- Fine-tuning, LoRA/QLoRA, and post-training frameworks that run locally.
- Local RAG frameworks, vector stores, and document-chat applications.
- Deployment, clustering, proxy, and packaging tools for local LLM serving.
- Hardware-acceleration SDKs, backends, and optimization runtimes for local inference.

## What does **not** belong

- Cloud-only APIs or services with no local/offline path.
- General AI news, blogs, or tutorials that are not tool/resource oriented.
- Closed-source or paywalled-only tools with no public documentation or trial.
- Duplicate entries.

## Quality bar

Every submission must be:

1. **Publicly accessible** — open source or publicly documented.
2. **Actively maintained** — last meaningful commit or release within the last 12 months (exceptions for widely used official reference repos).
3. **Documented** — a real README or docs page with setup or install instructions.
4. **Correctly categorized** — placed under the local-LLM category it primarily targets.
5. **Honestly labeled** — use the `Official` or `Community` badge.

## Entry format

Use this pattern:

```markdown
- **[Name](URL)** `Official` — One-sentence description.
  - Install: `command here`
```

If there is no install command, omit the install line.

## Category sections

The README is organized by **local-LLM concern**, not by programming language. New categories are allowed only if they contain at least five entries and fit the local-LLM theme.

## Pull request process

1. Fork the repository.
2. Add your entry in the correct category section.
3. Run `./scripts/validate-links.sh` and fix any broken links or anchors.
4. Open a pull request with a clear description of the resource and why it fits.

One resource per pull request is preferred.
