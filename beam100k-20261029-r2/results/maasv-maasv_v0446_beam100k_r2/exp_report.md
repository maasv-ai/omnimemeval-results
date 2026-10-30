# OmniMemEval Experiment Report — maasv-maasv_v0446_beam100k_r2

> Generated: 2026-10-29 20:41:10

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | BEAM |
| Memory Framework | maasv |
| Version | maasv_v0446_beam100k_r2 |
| Run Time | 2026-10-29 20:14:18 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| SCALE | 100k |
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
| Results Directory | `results/beam/maasv-maasv_v0446_beam100k_r2` |

**Reproduce:**

```bash
./scripts/run_beam_eval.sh --replay results/beam/maasv-maasv_v0446_beam100k_r2
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
| Answer API Calls | 400 |
| Context Tokens (avg) | 8419.4 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Nugget Score | 0.7543 ± 0.3208 |
| Questions | 400 |

### By Conversation Scale

| Scale | Nugget Score | Questions |
|-------|-------------|-----------|
| 100k | 0.7543 ± 0.3208 | 400 |

### By Question Dimension

| Dimension | Nugget Score | Questions |
|-----------|-------------|-----------|
| abstention | 0.8750 ± 0.2681 | 40 |
| contradiction_resolution | 0.6531 ± 0.2138 | 40 |
| event_ordering | 0.4177 ± 0.2495 | 40 |
| information_extraction | 0.9510 ± 0.1041 | 40 |
| instruction_following | 0.9000 ± 0.2222 | 40 |
| knowledge_update | 0.6500 ± 0.4359 | 40 |
| multi_session_reasoning | 0.6734 ± 0.3636 | 40 |
| preference_following | 0.9271 ± 0.1710 | 40 |
| summarization | 0.7898 ± 0.1734 | 40 |
| temporal_reasoning | 0.7063 ± 0.3988 | 40 |

### By Difficulty

| Difficulty | Nugget Score | Questions |
|------------|-------------|-----------|
| clear | 0.6531 ± 0.2138 | 40 |
| easy | 0.6967 ± 0.3893 | 124 |
| hard | 0.8875 ± 0.1662 | 42 |
| medium | 0.7838 ± 0.3024 | 193 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=400 |
| answer | 0 | 0 | success=400 |
| eval | 0 | 0 | success=400 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 12417.2 | 11568.7 | 19722.3 |
| Search Latency | 287.7 | 252.2 | 507.9 |
