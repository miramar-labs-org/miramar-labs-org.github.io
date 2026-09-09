---
layout: post
title: "Ai Interviewer Kfp Rag Eval"
date: 2026-09-09
categories: miramar kubeflow rag qdrant
---

KFP RAG eval measuring ai-interviewer corpus impact

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/ai-interviewer-kfp-rag-eval](https://github.com/miramar-labs-org/ai-interviewer-kfp-rag-eval)

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
| Qdrant collection | `ai-interviewer-kfp-rag-eval` |
| Embedding model | `BAAI/bge-small-en-v1.5` |
| LLM endpoint | `<!-- TODO: llm.base_url -->` |
| Eval thresholds | recall@5 ≥ 0.70, faithfulness ≥ 4.0, safety ≥ 3.5 |

## Eval results

| Run | recall@5 | faithfulness | safety | Gate |
|---|---|---|---|---|
| — | — | — | — | — |

## Next steps

<!-- TODO -->
