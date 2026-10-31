# Maasv on OmniMemEval LongMemEval-S: run records (2026-10-30/31)

Contributor-run evidence for the Maasv LongMemEval row. Run by the Maasv team,
one Maasv store per evaluation user (the standard self-hosted deployment).

| Item | Value |
| --- | --- |
| Result | QA accuracy (LLM-as-judge) 92.20 (461 / 500) |
| Context tokens | 3,967.0 per question (1,983,484 answer prompt tokens / 500 calls); 81,136 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | LongMemEval-S (`longmemeval_s_cleaned.json` from the runner's `prepare_longmemeval.py --variant s`, SHA-256 `d6f21ea9d60a0d56f34a05b609c79c88a451d2ae03597821ea3d5a9678c3a442`): 500 questions, 23,867 sessions, 246,750 messages |
| Coverage | 500 searched, answered and judged; 0 failed, 0 skipped; 0 failed users at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_lme_eval.sh --lib maasv --env .env.maasv --workers 1 --version maasv_v0446_lme_r1` (one invocation, non-streaming; started 2026-10-30 15:38 ET, finished 2026-10-31 04:06 ET) |

By question type (QA accuracy): single-session-user 100.00 (70),
single-session-assistant 100.00 (56), single-session-preference 96.67 (30),
knowledge-update 93.59 (78), temporal-reasoning 88.72 (133), multi-session
86.47 (133).

## Contents

- `results/maasv-maasv_v0446_lme_r1/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
