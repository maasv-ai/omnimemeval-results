# OmniMemEval Experiment Report — maasv-maasv_v0446_beam10m_r2

> Generated: 2026-10-30 08:15:52

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | BEAM |
| Memory Framework | maasv |
| Version | maasv_v0446_beam10m_r2 |
| Run Time | 2026-10-29 20:41:12 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| SCALE | 10m |
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
| SKIP_FAILED_JUDGE | 0 |
| SKIP_FAILED_STREAMING | 0 |
| Results Directory | `results/beam/maasv-maasv_v0446_beam10m_r2` |

**Reproduce:**

```bash
./scripts/run_beam_eval.sh --replay results/beam/maasv-maasv_v0446_beam10m_r2
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
| Answer API Calls | 200 |
| Context Tokens (avg) | 8535.6 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Nugget Score | 0.6169 ± 0.3810 |
| Questions | 200 |

### By Conversation Scale

| Scale | Nugget Score | Questions |
|-------|-------------|-----------|
| 10m | 0.6169 ± 0.3810 | 200 |

### By Question Dimension

| Dimension | Nugget Score | Questions |
|-----------|-------------|-----------|
| abstention | 0.7750 ± 0.2947 | 20 |
| contradiction_resolution | 0.5437 ± 0.1267 | 20 |
| event_ordering | 0.2552 ± 0.2406 | 20 |
| information_extraction | 0.7000 ± 0.4301 | 20 |
| instruction_following | 0.7750 ± 0.3345 | 20 |
| knowledge_update | 0.7250 ± 0.3700 | 20 |
| multi_session_reasoning | 0.3408 ± 0.3940 | 20 |
| preference_following | 0.8250 ± 0.3172 | 20 |
| summarization | 0.8163 ± 0.1768 | 20 |
| temporal_reasoning | 0.4125 ± 0.4052 | 20 |

### By Difficulty

| Difficulty | Nugget Score | Questions |
|------------|-------------|-----------|
| clear | 0.5437 ± 0.1267 | 20 |
| easy | 0.5202 ± 0.4294 | 71 |
| hard | 0.8088 ± 0.3142 | 12 |
| medium | 0.6852 ± 0.3568 | 91 |
| moderate | 0.5833 ± 0.4488 | 6 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=200 |
| answer | 0 | 0 | success=200 |
| eval | 0 | 0 | success=200 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 413764.3 | 404197.6 | 505944.1 |
| Search Latency | 383.6 | 338.0 | 824.8 |
