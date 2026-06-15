---
layout: post
title: "Qwen25 7b Ftuned Serving Vllm"
date: 2026-06-15
categories: miramar vllm serving gke
---

Serving fine-tuned qwen2.5-7b on vLLM / DGX

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/qwen25-7b-ftuned-serving-vllm](https://github.com/miramar-labs-org/qwen25-7b-ftuned-serving-vllm)

## Serving stack

| | |
|---|---|
| Base model | <!-- TODO --> |
| LoRA adapter | <!-- TODO: FT project + run --> |
| Inference engine | vLLM |
| Host | <!-- TODO: DGX Spark / AGX Orin / GKE L4 --> |
| Model alias | `<!-- TODO: served_model_name -->` |

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
