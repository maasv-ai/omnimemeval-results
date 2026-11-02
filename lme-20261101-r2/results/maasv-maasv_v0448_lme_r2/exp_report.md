# OmniMemEval Experiment Report — maasv-maasv_v0448_lme_r2

> Generated: 2026-11-01 17:07:37

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | LongMemEval |
| Memory Framework | maasv |
| Version | maasv_v0448_lme_r2 |
| Run Time | 2026-11-01 13:01:39 EST |
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
| Results Directory | `results/lme/maasv-maasv_v0448_lme_r2` |

**Reproduce:**

```bash
./scripts/run_lme_eval.sh --replay results/lme/maasv-maasv_v0448_lme_r2
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
| Context Tokens (avg) | 3999.4 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| LLM-as-Judge | 0.9120 ± 0.0000 |
| F1 | 0.1543 |
| ROUGE-1 | 0.1236 |
| ROUGE-2 | 0.0639 |
| ROUGE-L | 0.1114 |
| BLEU-1 | 0.0709 |
| BLEU-4 | 0.0256 |
| METEOR | 0.2268 |
| BERTScore F1 | - |
| Semantic Similarity | - |

### Category Breakdown

| Category | LLM-Judge | Questions |
|----------|-----------|-----------|
| knowledge-update | 0.8974 | 78 |
| multi-session | 0.8647 | 133 |
| single-session-assistant | 0.9821 | 56 |
| single-session-preference | 0.9333 | 30 |
| single-session-user | 0.9857 | 70 |
| temporal-reasoning | 0.8947 | 133 |

### Pipeline Status

| Stage | Failed Users | Skipped Records | Status Counts |
|-------|--------------|-----------------|---------------|
| search | 0 | 0 | success=500 |
| answer | 0 | 0 | success=500 |
| eval | 0 | 0 | success=500 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 601.9 | 606.3 | 868.8 |
| Search Latency | 547.5 | 487.7 | 949.6 |
