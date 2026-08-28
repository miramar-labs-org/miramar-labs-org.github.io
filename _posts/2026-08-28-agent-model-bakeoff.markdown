---
layout: post
title: "Agent Model Bakeoff"
date: 2026-08-28
categories: miramar kubeflow bakeoff eval llm
---

Ranks candidate LLMs x serving modes on the 3 multi-agent-ai-trader agent tasks (analyst universe, dealer signal, option pick) -- deterministic gates + LLM-judge -> leaderboard

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/agent-model-bakeoff](https://github.com/miramar-labs-org/agent-model-bakeoff)

## Pipeline

| Step | Purpose |
|---|---|
| `load_dataset` | Pull the frozen eval snapshot from MinIO |
| `serve_model` / `teardown_model` | Bring each candidate up/down (`ollama` or transient vLLM) |
| `<task harness>` | One per task — prompt the model, run deterministic gates <!-- TODO --> |
| `judge_and_score` | Fixed 1–5 LLM-as-judge + weighted composite |
| `report` | Winner to MLflow + `runs/RUNS.md` |

## Configuration

| | |
|---|---|
| Candidates | `<!-- TODO: models[] -->` |
| Serving modes | `<!-- TODO: ollama / guided -->` |
| Judge | `<!-- TODO: judge.model -->` |
| Dataset version | `<!-- TODO: dataset.version -->` |

## Leaderboard

| Run | Winner | Composite | Key Finding |
|---|---|---|---|
| — | — | — | — |

## Next steps

<!-- TODO -->
