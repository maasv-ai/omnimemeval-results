# OmniMemEval Experiment Report — maasv-maasv_v0448_beam100k_r2

> Generated: 2026-10-31 22:48:07

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | BEAM |
| Memory Framework | maasv |
| Version | maasv_v0448_beam100k_r2 |
| Run Time | 2026-10-31 22:36:09 EDT |
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
| Results Directory | `results/beam/maasv-maasv_v0448_beam100k_r2` |

**Reproduce:**

```bash
./scripts/run_beam_eval.sh --replay results/beam/maasv-maasv_v0448_beam100k_r2
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
| Context Tokens (avg) | 8525.6 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Nugget Score | 0.7638 ± 0.3250 |
| Questions | 400 |

### By Conversation Scale

| Scale | Nugget Score | Questions |
|-------|-------------|-----------|
| 100k | 0.7638 ± 0.3250 | 400 |

### By Question Dimension

| Dimension | Nugget Score | Questions |
|-----------|-------------|-----------|
| abstention | 0.8625 ± 0.2955 | 40 |
| contradiction_resolution | 0.6531 ± 0.1906 | 40 |
| event_ordering | 0.4222 ± 0.2702 | 40 |
| information_extraction | 0.9094 ± 0.2436 | 40 |
| instruction_following | 0.8875 ± 0.2368 | 40 |
| knowledge_update | 0.7000 ± 0.4444 | 40 |
| multi_session_reasoning | 0.6849 ± 0.3663 | 40 |
| preference_following | 0.9688 ± 0.0998 | 40 |
| summarization | 0.8248 ± 0.1721 | 40 |
| temporal_reasoning | 0.7250 ± 0.3742 | 40 |

### By Difficulty

| Difficulty | Nugget Score | Questions |
|------------|-------------|-----------|
| clear | 0.6531 ± 0.1906 | 40 |
| easy | 0.7123 ± 0.3926 | 124 |
| hard | 0.9335 ± 0.1480 | 42 |
| medium | 0.7843 ± 0.3102 | 193 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=400 |
| answer | 0 | 0 | success=400 |
| eval | 0 | 0 | success=400 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 2796.3 | 2666.4 | 3968.3 |
| Search Latency | 305.4 | 272.5 | 496.8 |
