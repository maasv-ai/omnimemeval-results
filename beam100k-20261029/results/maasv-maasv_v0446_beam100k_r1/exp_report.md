# OmniMemEval Experiment Report — maasv-maasv_v0446_beam100k_r1

> Generated: 2026-10-29 18:19:57

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | BEAM |
| Memory Framework | maasv |
| Version | maasv_v0446_beam100k_r1 |
| Run Time | 2026-10-29 17:53:46 EDT |
| Git | `571a0f7` (maasv-adapter) |
| WORKERS | 2 |
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
| Results Directory | `results/beam/maasv-maasv_v0446_beam100k_r1` |

**Reproduce:**

```bash
./scripts/run_beam_eval.sh --replay results/beam/maasv-maasv_v0446_beam100k_r1
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
| Context Tokens (avg) | 8675.5 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Nugget Score | 0.7483 ± 0.3287 |
| Questions | 400 |

### By Conversation Scale

| Scale | Nugget Score | Questions |
|-------|-------------|-----------|
| 100k | 0.7483 ± 0.3287 | 400 |

### By Question Dimension

| Dimension | Nugget Score | Questions |
|-----------|-------------|-----------|
| abstention | 0.8875 ± 0.2619 | 40 |
| contradiction_resolution | 0.6438 ± 0.2211 | 40 |
| event_ordering | 0.3350 ± 0.2496 | 40 |
| information_extraction | 0.9625 ± 0.1020 | 40 |
| instruction_following | 0.8750 ± 0.2622 | 40 |
| knowledge_update | 0.6250 ± 0.4294 | 40 |
| multi_session_reasoning | 0.6957 ± 0.3630 | 40 |
| preference_following | 0.9292 ± 0.1509 | 40 |
| summarization | 0.7983 ± 0.1746 | 40 |
| temporal_reasoning | 0.7312 ± 0.3682 | 40 |

### By Difficulty

| Difficulty | Nugget Score | Questions |
|------------|-------------|-----------|
| clear | 0.6438 ± 0.2211 | 40 |
| easy | 0.6959 ± 0.3769 | 124 |
| hard | 0.9048 ± 0.1970 | 42 |
| medium | 0.7709 ± 0.3223 | 193 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=400 |
| answer | 0 | 0 | success=400 |
| eval | 0 | 0 | success=400 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 24910.0 | 24543.1 | 33650.9 |
| Search Latency | 283.2 | 257.8 | 452.9 |
