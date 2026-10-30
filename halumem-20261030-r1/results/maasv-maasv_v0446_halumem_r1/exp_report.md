# OmniMemEval Experiment Report — maasv-maasv_v0446_halumem_r1

> Generated: 2026-10-30 12:35:22

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | HaluMem |
| Memory Framework | maasv |
| Version | maasv_v0446_halumem_r1 |
| Run Time | 2026-10-30 08:59:10 EDT |
| Git | `e1fbfff` (maasv-adapter) |
| WORKERS | 1 |
| LLM_WORKERS | 10 |
| TOPK | 20 |
| VARIANT | medium |
| NUM_RUNS | 1 |
| SAVE_MODEL_INPUT | 0 |
| CLEAR | 0 |
| WAIT_AFTER_INGEST | 0 |
| ALLOW_EMPTY_SEARCH | 1 |
| SKIP_FAILED_SEARCH | 0 |
| SKIP_FAILED_ANSWER | 0 |
| SKIP_FAILED_JUDGE | 0 |
| Results Directory | `results/halumem/maasv-maasv_v0446_halumem_r1` |

**Reproduce:**

```bash
./scripts/run_halumem_eval.sh --replay results/halumem/maasv-maasv_v0446_halumem_r1
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
| Answer API Calls | 3,467 |
| Context Tokens (avg) | 2139.7 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| QA Accuracy (LLM-as-Judge) | 0.8105 ± 0.0000 |
| F1 | 0.2133 |
| ROUGE-1 | 0.1726 |
| ROUGE-2 | 0.0689 |
| ROUGE-L | 0.1426 |
| BLEU-1 | 0.1118 |
| BLEU-4 | 0.0278 |
| METEOR | 0.2962 |
| BERTScore F1 | - |
| Semantic Similarity | - |

### By Question Type (QA Accuracy)

| Question Type | QA Accuracy | Questions |
|---------------|-------------|-----------|
| Basic Fact Recall | 0.7198 | 746 |
| Memory Boundary | 0.8998 | 828 |
| Memory Conflict | 0.8557 | 769 |
| Generalization & Application | 0.8164 | 746 |
| Multi-hop Inference | 0.7727 | 198 |
| Dynamic Update | 0.6000 | 180 |

### By Difficulty

| Difficulty | QA Accuracy | Questions |
|------------|-------------|-----------|
| easy | 0.8132 | 1970 |
| hard | 0.7755 | 98 |
| medium | 0.8091 | 1399 |

### Pipeline Status

| Stage | Failed Users | Failed Questions | Skipped Records | Status Counts |
|-------|--------------|------------------|-----------------|---------------|
| search | 0 | 0 | 0 | success=3467 |
| answer | 0 | 0 | 0 | success=3467 |
| eval | 0 | 0 | 0 | success=3467 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 8187.2 | 8167.8 | 11503.0 |
| Search Latency | 265.1 | 252.6 | 402.3 |
