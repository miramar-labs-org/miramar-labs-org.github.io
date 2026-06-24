---
layout: post
title: "Llama32 3b Serving Trt Engine"
date: 2026-06-24
categories: miramar tensorrt trt-llm engine serving
---

Serves Llama-3.2-3B-Instruct via TRT-LLM engine compiled for GB10

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/llama32-3b-serving-trt-engine](https://github.com/miramar-labs-org/llama32-3b-serving-trt-engine)

## Serving stack

| | |
|---|---|
| TRT-LLM engine | <!-- TODO: compression project + run --> |
| Inference engine | tensorrt_llm.serve |
| Host | <!-- TODO: DGX Spark (gb10) / AGX Orin (sm87) / GKE L4 --> |
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
