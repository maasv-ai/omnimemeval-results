# Maasv on OmniMemEval BEAM 10M: run records (2026-11-01)

Contributor-run evidence for the Maasv BEAM 10M row on Maasv v0.4.48. Run by
the Maasv team, one Maasv store per evaluation user (the standard self-hosted
deployment). It replaces the v0.4.46 result (61.69, `beam10m-20261030-r2`),
whose records stay published.

| Item | Value |
| --- | --- |
| Result | Nugget score 65.09 ± 38.85 (per-question SD), 200 questions |
| Context tokens | 8,656.1 per question (1,731,213 answer prompt tokens / 200 calls); 119,439 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter (ordered batches of 50 messages per add request); no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.48, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | BEAM 10M (`beam_10m_10m.json` from the runner's `prepare_beam.py --scale 10m`): 10 conversations, 208,696 messages, 200 questions |
| Coverage | 200 searched, answered and judged; 0 failed, 0 skipped; 0 failed conversations at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_beam_eval.sh --lib maasv --env .env.maasv --workers 1 --scale 10m --version maasv_v0448_beam10m_r2` (one invocation, non-streaming; started 2026-11-01 17:07 ET, finished 20:38 ET) |

By dimension (nugget score, 20 questions each): abstention 80.00,
contradiction resolution 63.12, event ordering 22.78, information extraction
77.50, instruction following 87.50, knowledge update 72.50, multi-session
reasoning 26.08, preference following 85.00, summarization 82.64, temporal
reasoning 53.75.

## Contents

- `results/maasv-maasv_v0448_beam10m_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
