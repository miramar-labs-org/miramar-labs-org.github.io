---
layout: post
title: "Dnabert2 Clinvar Kfp Sequence Classify"
date: 2026-07-04
categories: miramar kubeflow sequence-classification genomics
---

DNABERT-2 sequence-encoder classification pipeline for ClinVar variant pathogenicity prediction

**Platform:** DGX Spark via [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/dnabert2-clinvar-kfp-sequence-classify](https://github.com/miramar-labs-org/dnabert2-clinvar-kfp-sequence-classify)

## Pipeline

<!-- TODO: base model, dataset, task description -->

## Two-phase transfer learning

This pipeline implements Phase 2 (classification fine-tuning) of a transfer learning workflow.

**Phase 1 (pre-training, done by model authors):** the base model learned sequence structure from
billions of raw nucleotides/amino acids using masked prediction — no labels, no task.

**Phase 2 (this pipeline):** attach a linear classification head to the `[CLS]` embedding
and train on labeled examples. Baseline accuracy ≈ 50% (random head); post-FT expected 75–85%+.

## Steps

| Step | Description |
|------|-------------|
| `download_model` | Snapshot-download base encoder from HuggingFace Hub |
| `prepare_dataset` | Load + process sequences; chromosome or random split |
| `baseline_eval` | Random-head accuracy + AUC (expected ≈ 50% / 0.50) |
| `fine_tune` | Train encoder + classification head via HuggingFace Trainer |
| `post_finetune_eval` | Accuracy + AUC on held-out test set |
| `deployment_gate` | Check AUC ≥ threshold and accuracy delta ≥ threshold |

## Configuration

| Parameter | Value |
|-----------|-------|
| Base encoder | <!-- TODO: model ID --> |
| Dataset | <!-- TODO: HF dataset ID --> |
| num_labels | <!-- TODO: 2 for binary --> |
| Split strategy | <!-- TODO: chromosome / random --> |
| Epochs | <!-- TODO --> |

## Evaluation results

| Run | Baseline Acc | Post-FT Acc | Δ Acc | Baseline AUC | Post-FT AUC | Gate |
|-----|-------------|-------------|-------|-------------|-------------|------|
| run-001 | | | | | | |

## Next steps

<!-- TODO -->
