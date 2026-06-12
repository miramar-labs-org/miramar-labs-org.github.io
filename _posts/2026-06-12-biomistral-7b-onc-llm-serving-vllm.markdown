---
layout: post
title: "Biomistral 7b Onc Llm Serving Vllm"
date: 2026-06-12
categories: miramar vllm serving gke
---

BioMistral-7B oncology LoRA adapter served via vLLM on GKE — Stage 1 of Miramar serving arc

**Platform:** GKE via [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/biomistral-7b-onc-llm-serving-vllm](https://github.com/miramar-labs-org/biomistral-7b-onc-llm-serving-vllm)

## Serving stack

| | |
|---|---|
| Base model | <!-- TODO --> |
| LoRA adapter | <!-- TODO: FT project + run --> |
| Inference engine | vLLM |
| GPU | L4 spot (24 GB) |
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
