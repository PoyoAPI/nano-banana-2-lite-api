# Nano Banana 2 Lite API Examples for PoYo

[![Model page](https://img.shields.io/badge/Model%20page-nano-banana-2-lite-84cc16)](https://poyo.ai/models/nano-banana-2-lite)
[![API docs](https://img.shields.io/badge/API%20docs-docs.poyo.ai-22d3ee)](https://docs.poyo.ai/api-manual/image-series/nano-banana-2-lite)
[![License: MIT](https://img.shields.io/badge/License-MIT-111827)](LICENSE)
[![Main examples](https://img.shields.io/badge/Main%20examples-PoyoAPI%2Fpoyo--examples-0f172a?logo=github)](https://github.com/PoyoAPI/poyo-examples)

Focused server-side examples for building with `nano-banana-2-lite` and `nano-banana-2-lite-edit` on PoYo.

Nano Banana 2 Lite is useful for fast lower-cost image drafts, thumbnails, product concepts, and high-throughput visual tests.

[Model Page](https://poyo.ai/models/nano-banana-2-lite) | [Docs](https://docs.poyo.ai/api-manual/image-series/nano-banana-2-lite) | [Get API Key](https://poyo.ai/dashboard/api-key) | [Pricing](https://poyo.ai/pricing) | [Main Examples](https://github.com/PoyoAPI/poyo-examples)

## What This Repo Covers

- Text-to-image with `nano-banana-2-lite`
- Image editing with `nano-banana-2-lite-edit`
- cURL and Node.js backend examples
- Async task flow: submit, store `data.task_id`, poll status, retrieve files
- Webhook receiver notes for production callbacks

## Quick Start

```bash
cp .env.example .env
export POYO_API_KEY="your-api-key"
```

Run the Node.js example:

```bash
cd node
npm start
```

Keep `POYO_API_KEY` on the server. Do not expose it in browser code, mobile apps, screenshots, or public logs.

## Examples

| Path | What it covers |
| --- | --- |
| [`curl/generate.md`](curl/generate.md) | Copy-paste API request. |
| [`node/`](node/) | Native Node.js backend example. |
| [`docs/prompt-examples.md`](docs/prompt-examples.md) | Practical prompts for product workflows and creative tests. |
| [`docs/production-notes.md`](docs/production-notes.md) | Security and reliability notes before launch. |
| [`webhooks/express-webhook/`](webhooks/express-webhook/) | Minimal Express receiver for PoYo callbacks. |

## Run Checks

```bash
make check
```

On Windows:

```powershell
./scripts/check.ps1
```

## License

MIT
