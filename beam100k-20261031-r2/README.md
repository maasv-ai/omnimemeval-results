# Maasv on OmniMemEval BEAM 100K: run records (2026-10-31, run 2)

Contributor-run evidence for the Maasv BEAM 100K row on Maasv v0.4.48. Run by
the Maasv team, one Maasv store per evaluation user (the standard self-hosted
deployment). It replaces the v0.4.46 result (75.43, `beam100k-20261029-r2`),
whose records stay published. Run 1 on v0.4.48 was stopped before ingestion
began, for the reason given in `locomo-20261031-r2`; it produced no results.

| Item | Value |
| --- | --- |
| Result | Nugget score 76.38 ± 32.50 (per-question SD), 400 questions |
| Context tokens | 8,525.6 per question (3,410,257 answer prompt tokens / 400 calls); 219,315 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter (ordered batches of 50 messages per add request); no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.48, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | BEAM 100K from `prepare_beam.py --scale 100k`: 20 conversations, 5,732 messages, 400 questions |
| Coverage | 400 searched, answered and judged; 0 failed, 0 skipped; 0 failed conversations at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_beam_eval.sh --lib maasv --env .env.maasv --workers 1 --scale 100k --version maasv_v0448_beam100k_r2` (one invocation, non-streaming; started 2026-10-31 22:36 ET, finished 22:48 ET) |

By dimension (nugget score, 40 questions each): abstention 86.25,
contradiction resolution 65.31, event ordering 42.22, information extraction
90.94, instruction following 88.75, knowledge update 70.00, multi-session
reasoning 68.49, preference following 96.88, summarization 82.48, temporal
reasoning 72.50.

## Contents

- `results/maasv-maasv_v0448_beam100k_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
