---
layout: post
title: "Kfp Nemo Curator Verify"
date: 2026-06-22
categories: miramar kubeflow nemo-curator data-curation
---

Verification run for kfp-nemo-curator template

**Platform:** [Miramar Platform](https://miramar-labs-org.github.io/miramar-platform-gcp/)
**Repo:** [miramar-labs-org/kfp-nemo-curator-verify](https://github.com/miramar-labs-org/kfp-nemo-curator-verify)

## Pipeline

| Step | Compute | Purpose |
|---|---|---|
| `preflight_check` | CPU | Verify input data is staged on PVC |
| `extract_text` | CPU | Text extraction + Unicode normalization <!-- TODO --> |
| `quality_filter` | GPU | Heuristic quality scoring + filtering <!-- TODO --> |
| `deduplication` | GPU | Exact hash dedup + fuzzy MinHash LSH <!-- TODO --> |
| `pii_redaction` | CPU | presidio + spaCy PII detection/redaction <!-- TODO --> |
| `curator_report` | CPU | Summary metrics + MLflow logging |

## Curation results

| Run | docs\_in | quality\_filtered | deduped | curated | PII found | Key Finding |
|---|---|---|---|---|---|---|
| — | — | — | — | — | — | — |

## Next steps

<!-- TODO -->
