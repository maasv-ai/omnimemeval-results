# OmniMemEval Experiment Report — maasv-maasv_v0448_halumem_r3

> Generated: 2026-11-01 11:43:51

## Experiment Configuration

| Parameter | Value |
|-----------|-------|
| Benchmark | HaluMem |
| Memory Framework | maasv |
| Version | maasv_v0448_halumem_r3 |
| Run Time | 2026-11-01 11:34:47 EST |
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
| Results Directory | `results/halumem/maasv-maasv_v0448_halumem_r3` |

**Reproduce:**

```bash
./scripts/run_halumem_eval.sh --replay results/halumem/maasv-maasv_v0448_halumem_r3
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
| Context Tokens (avg) | 2240.5 |

## Evaluation Results

### Overall Scores

| Metric | Score |
|--------|-------|
| QA Accuracy (LLM-as-Judge) | 0.8229 ± 0.0000 |
| F1 | 0.2081 |
| ROUGE-1 | 0.1694 |
| ROUGE-2 | 0.0673 |
| ROUGE-L | 0.1390 |
| BLEU-1 | 0.1079 |
| BLEU-4 | 0.0263 |
| METEOR | 0.2901 |
| BERTScore F1 | - |
| Semantic Similarity | - |

### By Question Type (QA Accuracy)

| Question Type | QA Accuracy | Questions |
|---------------|-------------|-----------|
| Basic Fact Recall | 0.7172 | 746 |
| Memory Boundary | 0.9191 | 828 |
| Memory Conflict | 0.8752 | 769 |
| Generalization & Application | 0.8217 | 746 |
| Multi-hop Inference | 0.7980 | 198 |
| Dynamic Update | 0.6278 | 180 |

### By Difficulty

| Difficulty | QA Accuracy | Questions |
|------------|-------------|-----------|
| easy | 0.8274 | 1970 |
| hard | 0.7959 | 98 |
| medium | 0.8184 | 1399 |

### Pipeline Status

| Stage | Failed Users | Failed Questions | Skipped Records | Status Counts |
|-------|--------------|------------------|-----------------|---------------|
| search | 0 | 0 | 0 | success=3467 |
| answer | 0 | 0 | 0 | success=3467 |
| eval | 0 | 0 | 0 | success=3467 |

### Latency Metrics

| Metric | Avg (ms) | P50 (ms) | P95 (ms) |
|--------|----------|----------|----------|
| Add Latency | 4094.0 | 3916.7 | 7465.4 |
| Search Latency | 287.8 | 258.7 | 443.9 |
