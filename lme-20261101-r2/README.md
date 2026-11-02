# Maasv on OmniMemEval LongMemEval-S: run records (2026-11-01)

Contributor-run evidence for the Maasv LongMemEval row on Maasv v0.4.48. Run by
the Maasv team, one Maasv store per evaluation user (the standard self-hosted
deployment). It replaces the v0.4.46 result (92.20, `lme-20261031-r1`), whose
records stay published.

| Item | Value |
| --- | --- |
| Result | QA accuracy (LLM-as-judge) 91.20 (456 / 500) |
| Context tokens | 3,999.4 per question (1,999,686 answer prompt tokens / 500 calls); 82,519 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.48, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | LongMemEval-S (`longmemeval_s_cleaned.json` from the runner's `prepare_longmemeval.py --variant s`, SHA-256 `d6f21ea9d60a0d56f34a05b609c79c88a451d2ae03597821ea3d5a9678c3a442`): 500 questions, 23,867 sessions, 246,750 messages |
| Coverage | 500 searched, answered and judged; 0 failed, 0 skipped; 0 failed users at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_lme_eval.sh --lib maasv --env .env.maasv --workers 1 --version maasv_v0448_lme_r2` (one invocation, non-streaming; started 2026-11-01 13:01 ET, finished 17:07 ET) |

By question type (QA accuracy): single-session-user 98.57 (70),
single-session-assistant 98.21 (56), single-session-preference 93.33 (30),
knowledge-update 89.74 (78), temporal-reasoning 89.47 (133), multi-session
86.47 (133).

## Contents

- `results/maasv-maasv_v0448_lme_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
