# OmniMemEval Experiment Report — maasv-maasv_v0448_beam10m_r2

> Generated: 2026-11-01 20:38:12

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | BEAM |
| Memory Framework | maasv |
| Version | maasv_v0448_beam10m_r2 |
| Run Time | 2026-11-01 17:07:41 EST |
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
| Results Directory | `results/beam/maasv-maasv_v0448_beam10m_r2` |

**Reproduce:**

```bash
./scripts/run_beam_eval.sh --replay results/beam/maasv-maasv_v0448_beam10m_r2
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
| Context Tokens (avg) | 8656.1 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| Nugget Score | 0.6509 ± 0.3885 |
| Questions | 200 |

### By Conversation Scale

| Scale | Nugget Score | Questions |
|-------|-------------|-----------|
| 10m | 0.6509 ± 0.3885 | 200 |

### By Question Dimension

| Dimension | Nugget Score | Questions |
|-----------|-------------|-----------|
| abstention | 0.8000 ± 0.3317 | 20 |
| contradiction_resolution | 0.6312 ± 0.1504 | 20 |
| event_ordering | 0.2278 ± 0.2010 | 20 |
| information_extraction | 0.7750 ± 0.4023 | 20 |
| instruction_following | 0.8750 ± 0.2681 | 20 |
| knowledge_update | 0.7250 ± 0.3945 | 20 |
| multi_session_reasoning | 0.2608 ± 0.3638 | 20 |
| preference_following | 0.8500 ± 0.3102 | 20 |
| summarization | 0.8264 ± 0.1988 | 20 |
| temporal_reasoning | 0.5375 ± 0.4129 | 20 |

### By Difficulty

| Difficulty | Nugget Score | Questions |
|------------|-------------|-----------|
| clear | 0.6312 ± 0.1504 | 20 |
| easy | 0.5385 ± 0.4443 | 71 |
| hard | 0.7917 ± 0.3186 | 12 |
| medium | 0.7233 ± 0.3657 | 91 |
| moderate | 0.6667 ± 0.3436 | 6 |

### Pipeline Status

| Stage | Failed Units | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=200 |
| answer | 0 | 0 | success=200 |
| eval | 0 | 0 | success=200 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 123376.1 | 115819.1 | 203619.1 |
| Search Latency | 536.7 | 366.4 | 1518.0 |
