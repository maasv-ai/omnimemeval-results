# Maasv on OmniMemEval HaluMem-Medium: run records (2026-10-30)

Contributor-run evidence for the Maasv HaluMem row. Run by the Maasv team,
one Maasv store per evaluation user (the standard self-hosted deployment).

| Item | Value |
| --- | --- |
| Result | QA accuracy (LLM-as-judge) 81.05 (2,810 / 3,467) |
| Context tokens | 2,139.7 per question (7,418,455 answer prompt tokens / 3,467 calls); 263,266 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | HaluMem-Medium (`HaluMem-Medium.jsonl` from the runner's `prepare_halumem.py`, SHA-256 `486fbc130a5c8781a2af27ffa508a1d7855245137aa449c193ac4d29c45634e7`): 20 users, 1,387 sessions, 60,146 messages, 3,467 questions |
| Coverage | 3,467 searched, answered and judged; 0 failed, 0 skipped; 0 failed users at ingestion |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_halumem_eval.sh --lib maasv --env .env.maasv --workers 1 --variant medium --version maasv_v0446_halumem_r1` (one invocation, non-streaming; started 2026-10-30 08:59 ET, finished 12:35 ET) |

By question type (QA accuracy): basic fact recall 71.98 (746), memory
boundary 89.98 (828), memory conflict 85.57 (769), generalization and
application 81.64 (746), multi-hop inference 77.27 (198), dynamic update
60.00 (180).

## Contents

- `results/maasv-maasv_v0446_halumem_r1/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
