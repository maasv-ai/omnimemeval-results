# Maasv on OmniMemEval

Run records for Maasv's contributor-run results on
[OmniMemEval](https://github.com/MemTensor/OmniMemEval).

## Current

| Run | Benchmark | Result | Records |
| --- | --- | --- | --- |
| 2026-10-29, run 2 | LoCoMo, categories 1–4 (1,540 questions) | 86.10% LLM-as-judge; 1,472.7 context tokens per question | [`locomo-20261029-r2/`](./locomo-20261029-r2/) · [release archive](https://github.com/maasv-ai/omnimemeval-results/releases/tag/locomo-20261029-r2) |
| 2026-10-29, run 2 | BEAM 100K (400 questions) | Nugget score 75.43; 8,419.4 context tokens per question | [`beam100k-20261029-r2/`](./beam100k-20261029-r2/) · [release archive](https://github.com/maasv-ai/omnimemeval-results/releases/tag/beam100k-20261029-r2) |

Run 2 uses one Maasv store per evaluation user, the standard self-hosted
deployment.

## Superseded

Run 1 kept every evaluation user in a single shared Maasv store, which reduced
retrieval quality. Its records stay here unchanged for reference.

| Run | Benchmark | Result | Records |
| --- | --- | --- | --- |
| 2026-10-29, run 1 | LoCoMo | 85.26% | [`locomo-20261029/`](./locomo-20261029/) · [release archive](https://github.com/maasv-ai/omnimemeval-results/releases/tag/locomo-20261029) |
| 2026-10-29, run 1 | BEAM 100K | 74.83 | [`beam100k-20261029/`](./beam100k-20261029/) · [release archive](https://github.com/maasv-ai/omnimemeval-results/releases/tag/beam100k-20261029) |

Each run directory has a README with the harness commit, models, dataset
checksum, coverage, commands and a `SHA256SUMS` file.
