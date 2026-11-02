# OmniMemEval Experiment Report — maasv-maasv_v0448_locomo_r2

> Generated: 2026-10-31 22:36:06

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | LoCoMo |
| Memory Framework | maasv |
| Version | maasv_v0448_locomo_r2 |
| Run Time | 2026-10-31 22:21:25 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| NUM_RUNS | 1 |
| SAVE_MODEL_INPUT | 0 |
| CLEAR | 0 |
| WAIT_AFTER_INGEST | 0 |
| ALLOW_EMPTY_SEARCH | 1 |
| SKIP_FAILED_SEARCH | 0 |
| SKIP_FAILED_ANSWER | 0 |
| SKIP_FAILED_JUDGE | 0 |
| Results Directory | `results/locomo/maasv-maasv_v0448_locomo_r2` |

**Reproduce:**

```bash
./scripts/run_locomo_eval.sh --replay results/locomo/maasv-maasv_v0448_locomo_r2
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
| Answer API Calls | 1,540 |
| Context Tokens (avg) | 1550.8 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| LLM-as-Judge | 0.8773 ± 0.0000 |
| F1 | 0.2742 |
| ROUGE-1 | 0.2804 |
| ROUGE-2 | 0.1460 |
| ROUGE-L | 0.2624 |
| BLEU-1 | 0.1713 |
| BLEU-4 | 0.0660 |
| METEOR | 0.4115 |
| BERTScore F1 | - |
| Semantic Similarity | - |

### Category Breakdown

| Category | LLM-Judge | Questions |
|----------|-----------|-----------|
| multi hop | 0.8298 | 282 |
| temporal reasoning | 0.8598 | 321 |
| open domain | 0.7188 | 96 |
| single hop | 0.9180 | 841 |

### Pipeline Status

| Stage | Failed Groups | Skipped Records | Status Counts |
|-------|---------------|-----------------|---------------|
| search | 0 | 0 | success=1540 |
| answer | 0 | 0 | success=1540 |
| eval | 0 | 0 | success=1540 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 1074.1 | 967.5 | 1855.0 |
| Search Latency | 251.5 | 237.0 | 401.8 |
