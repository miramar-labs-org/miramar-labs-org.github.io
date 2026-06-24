---
layout: post
title: "Qwen25 3b Serving Llm Nim"
date: 2026-06-24
categories: miramar nim serving dgx local-nim
---

<!-- TODO: one-sentence description -->

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/qwen25-3b-serving-llm-nim](https://github.com/miramar-labs-org/qwen25-3b-serving-llm-nim)

## Serving stack

| | |
|---|---|
| Local model | `<!-- TODO: model path -->` |
| Runtime | NVIDIA Multi-LLM NIM (`nvcr.io/nim/nvidia/llm-nim`) |
| Host | DGX Spark (GB10 Blackwell) |
| Served as | `<!-- TODO: served_model_name -->` |

## Deployment

```bash
curl http://localhost:8000/v1/models
curl -X POST http://localhost:8000/v1/chat/completions \\
  -d '{"model":"<!-- TODO -->","messages":[{"role":"user","content":"..."}]}'
```

## Smoke test results

<!-- TODO: sample prompts and responses -->

## Next steps

<!-- TODO -->
