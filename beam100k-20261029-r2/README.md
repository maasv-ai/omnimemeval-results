# Maasv on OmniMemEval BEAM 100K: run records (2026-10-29, run 2)

Contributor-run evidence for the Maasv BEAM 100K row. Run by the Maasv team.
This run supersedes run 1 (`beam100k-20261029`), which kept every evaluation
user in a single shared Maasv store; run 2 uses one Maasv store per evaluation
user, the standard self-hosted deployment.

| Item | Value |
| --- | --- |
| Result | Nugget score 75.43 ± 32.08 (per-question SD), 400 questions |
| Context tokens | 8,419.4 per question |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | BEAM 100K from `prepare_beam.py --scale 100k`: 20 conversations, 5,732 messages, 400 questions |
| Coverage | 400 searched, answered and judged; 0 failed, 0 skipped; 0 failed conversations at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_beam_eval.sh --lib maasv --env .env.maasv --workers 1 --scale 100k --version maasv_v0446_beam100k_r2` (one invocation, non-streaming) |

By dimension (nugget score, 40 questions each): abstention 87.50,
contradiction resolution 65.31, event ordering 41.77, information extraction
95.10, instruction following 90.00, knowledge update 65.00, multi-session
reasoning 67.34, preference following 92.71, summarization 78.98, temporal
reasoning 70.63.

## Contents

- `results/maasv-maasv_v0446_beam100k_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
