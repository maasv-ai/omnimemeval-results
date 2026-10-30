# OmniMemEval Experiment Report — maasv-maasv_v0446_pmv2_r1

> Generated: 2026-10-30 15:32:43

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | PersonaMem v2 |
| Memory Framework | maasv |
| Version | maasv_v0446_pmv2_r1 |
| Run Time | 2026-10-30 12:38:21 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| NUM_RUNS | 1 |
| SAVE_MODEL_INPUT | 0 |
| CLEAR | 0 |
| WAIT_AFTER_INGEST | 0 |
| STREAMING | 0 |
| START_IDX | 0 |
| END_IDX |  |
| ALLOW_EMPTY_SEARCH | 1 |
| SKIP_FAILED_SEARCH | 0 |
| SKIP_FAILED_ANSWER | 0 |
| SKIP_FAILED_STREAMING | 0 |
| ALLOW_MISSING_DATA | 0 |
| Results Directory | `results/pmv2/maasv-maasv_v0446_pmv2_r1` |

**Reproduce:**

```bash
./scripts/run_pmv2_eval.sh --replay results/pmv2/maasv-maasv_v0446_pmv2_r1
```

### Environment Variables (snapshot_eval.env)

| Variable | Value |
|----------|-------|
| `MAASV_BASE_URL` | `http://127.0.0.1:8765` |
| `LLM_WORKERS` | `10` |
| `TOPK` | `20` |
| `ANSWER_MODEL` | `gpt-4.1-mini-2025-04-14` |
| `EVAL_MODEL` | `gpt-4o-mini-2024-07-18` |

## Context Tokens

> Context Tokens are answer-stage prompt/input tokens. They are used as an approximate proxy for retrieved search-result length and should be compared only under the same benchmark, answer model, and prompt template.

| Metric | Value |
|--------|-------|
| Answer Model | gpt-4.1-mini-2025-04-14 |
| Answer API Calls | 5,000 |
| Context Tokens (avg) | 2831.7 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Precision (Accuracy) | 0.3548 ± 0.0000 |
| Questions | 5000 |
| Total Runs | 5000 |

### Category Breakdown

| Category | Precision | Questions |
|----------|-----------|-----------|
| anti_stereotypical_pref | 0.3567 ± 0.0000 | 855 |
| ask_to_forget | 0.3721 ± 0.0000 | 1048 |
| health_and_medical_conditions | 0.3028 ± 0.0000 | 568 |
| neutral_preferences | 0.3462 ± 0.0000 | 858 |
| sensitive_info | 0.3386 ± 0.0000 | 511 |
| stereotypical_pref | 0.3977 ± 0.0000 | 533 |
| therapy_background | 0.3589 ± 0.0000 | 627 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=5000 |
| answer | 0 | 0 | success=5000 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 3647.7 | 3743.3 | 4183.8 |
| Search Latency | 246.6 | 231.5 | 401.7 |
