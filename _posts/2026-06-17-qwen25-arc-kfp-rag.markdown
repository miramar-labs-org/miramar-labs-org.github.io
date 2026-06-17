---
layout: post
title: "Qwen25 Arc Kfp Rag"
date: 2026-06-17
categories: miramar kubeflow rag qdrant
---

RAG pipeline for general QA using qwen25-arc (Qwen2.5-7B + ARC LoRA) on DGX Spark via KFP

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/qwen25-arc-kfp-rag](https://github.com/miramar-labs-org/qwen25-arc-kfp-rag)

## Pipeline

| Step | Purpose |
|---|---|
| `ingest_documents` | Chunk + embed docs, upsert to Qdrant |
| `retrieval_eval` | recall@k, MRR, hit_rate <!-- TODO --> |
| `generation_eval` | RAG chain + LLM-as-judge correctness <!-- TODO --> |
| `faithfulness_eval` | Faithfulness, citation coverage <!-- TODO --> |
| `safety_eval` | Safety scoring 1–5 <!-- TODO --> |
| `deployment_gate` | Threshold check — fail pipeline if unmet |

## Configuration

| | |
|---|---|
| Qdrant collection | `qwen25-arc-kfp-rag` |
| Embedding model | `BAAI/bge-small-en-v1.5` |
| LLM endpoint | `<!-- TODO: llm.base_url -->` |
| Eval thresholds | recall@5 ≥ 0.70, faithfulness ≥ 4.0, safety ≥ 3.5 |

## Eval results

| Run | recall@5 | faithfulness | safety | Gate |
|---|---|---|---|---|
| — | — | — | — | — |

## Next steps

<!-- TODO -->
