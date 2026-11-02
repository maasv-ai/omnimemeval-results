# Maasv on OmniMemEval HaluMem-Medium: run records (2026-11-01, run 3)

Contributor-run evidence for the Maasv HaluMem row on Maasv v0.4.48. Run by the
Maasv team, one Maasv store per evaluation user (the standard self-hosted
deployment). It replaces the v0.4.46 result (81.05, `halumem-20261030-r1`),
whose records stay published. Run 2 on v0.4.48 (2026-10-31) was invalid: the
answer API account stopped accepting calls during its answer stage. It is not
published.

| Item | Value |
| --- | --- |
| Result | QA accuracy (LLM-as-judge) 82.29 (2,853 / 3,467) |
| Context tokens | 2,240.5 per question (7,767,984 answer prompt tokens / 3,467 calls); 280,960 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.48, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | HaluMem-Medium (`HaluMem-Medium.jsonl` from the runner's `prepare_halumem.py`, SHA-256 `486fbc130a5c8781a2af27ffa508a1d7855245137aa449c193ac4d29c45634e7`): 20 users, 1,387 sessions, 60,146 messages, 3,467 questions |
| Coverage | 3,467 searched, answered and judged; 0 failed, 0 skipped; 0 failed users at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |

## How it ran

1. `./scripts/run_halumem_eval.sh --lib maasv --env .env.maasv --workers 1 --variant medium --version maasv_v0448_halumem_r3` (started 2026-11-01 09:08 ET): ingestion and search completed for all 3,467 questions. The run was stopped at 10:59 ET at the start of the answer stage, because the answer API key had stopped working; the answer calls made in those seconds failed and none was kept.
2. `./scripts/run_halumem_eval.sh --lib maasv --env .env.maasv --workers 1 --variant medium --version maasv_v0448_halumem_r3 --from-step 3` (11:34 to 11:43 ET, with a working key): answers, judge, metrics and report for all 3,467 questions from the saved search results. `experiment_config.sh` and `exp_report.md` record this second invocation.

By question type (QA accuracy): basic fact recall 71.72 (746), memory
boundary 91.91 (828), memory conflict 87.52 (769), generalization and
application 82.17 (746), multi-hop inference 79.80 (198), dynamic update
62.78 (180).

## Contents

- `results/maasv-maasv_v0448_halumem_r3/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
