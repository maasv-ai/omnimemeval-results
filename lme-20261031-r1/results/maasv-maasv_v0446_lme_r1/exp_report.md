# OmniMemEval Experiment Report — maasv-maasv_v0446_lme_r1

> Generated: 2026-10-31 04:06:08

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | LongMemEval |
| Memory Framework | maasv |
| Version | maasv_v0446_lme_r1 |
| Run Time | 2026-10-30 15:38:52 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| NUM_RUNS | 1 |
| SAVE_MODEL_INPUT | 0 |
| STREAMING | 0 |
| START_IDX | 0 |
| END_IDX |  |
| ALLOW_EMPTY_SEARCH | 1 |
| SKIP_FAILED_SEARCH | 0 |
| SKIP_FAILED_ANSWER | 0 |
| SKIP_FAILED_JUDGE | 0 |
| SKIP_FAILED_STREAMING | 0 |
| Results Directory | `results/lme/maasv-maasv_v0446_lme_r1` |

**Reproduce:**

```bash
./scripts/run_lme_eval.sh --replay results/lme/maasv-maasv_v0446_lme_r1
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
| Answer API Calls | 500 |
| Context Tokens (avg) | 3967.0 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| LLM-as-Judge | 0.9220 ± 0.0000 |
| F1 | 0.1570 |
| ROUGE-1 | 0.1231 |
| ROUGE-2 | 0.0632 |
| ROUGE-L | 0.1119 |
| BLEU-1 | 0.0707 |
| BLEU-4 | 0.0262 |
| METEOR | 0.2321 |
| BERTScore F1 | - |
| Semantic Similarity | - |

### Category Breakdown

| Category | LLM-Judge | Questions |
|----------|-----------|-----------|
| knowledge-update | 0.9359 | 78 |
| multi-session | 0.8647 | 133 |
| single-session-assistant | 1.0000 | 56 |
| single-session-preference | 0.9667 | 30 |
| single-session-user | 1.0000 | 70 |
| temporal-reasoning | 0.8872 | 133 |

### Pipeline Status

| Stage | Failed Users | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=500 |
| answer | 0 | 0 | success=500 |
| eval | 0 | 0 | success=500 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 1863.7 | 2031.3 | 2805.3 |
| Search Latency | 474.9 | 416.1 | 822.5 |
