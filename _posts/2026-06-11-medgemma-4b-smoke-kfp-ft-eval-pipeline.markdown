---
layout: post
title: "Medgemma 4b Smoke Kfp Ft Eval Pipeline"
date: 2026-06-11
categories: miramar kubeflow fine-tuning
---

MedGemma 4B smoke test — validates chunked adapter PVC copy fix before medgemma-27b overnight run

**Platform:** DGX Spark via [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/medgemma-4b-smoke-kfp-ft-eval-pipeline](https://github.com/miramar-labs-org/medgemma-4b-smoke-kfp-ft-eval-pipeline)

## Pipeline

<!-- TODO: base model, dataset, fine-tuning approach -->

## Steps

| Step | Description |
|------|-------------|
| `prepare_dataset` | <!-- TODO --> |
| `baseline_eval` | <!-- TODO --> |
| `fine_tune` | <!-- TODO --> |
| `post_finetune_eval` | <!-- TODO --> |
| `safety_eval` | <!-- TODO --> |
| `deployment_gate` | <!-- TODO --> |

## Configuration

| Parameter | Value |
|-----------|-------|
| Base model | <!-- TODO --> |
| Dataset(s) | <!-- TODO --> |
| LoRA rank | <!-- TODO --> |
| Epochs | <!-- TODO --> |

## Evaluation results

| Metric | Base | Fine-tuned |
|--------|------|------------|
| Accuracy | | |
| Safety score | | |

## Next steps

<!-- TODO -->
