# Maasv on OmniMemEval LoCoMo: run records (2026-10-29, run 2)

Contributor-run evidence for the Maasv LoCoMo row. Run by the Maasv team. This
run supersedes run 1 (`locomo-20261029`), which kept every evaluation user in a
single shared Maasv store; run 2 uses one Maasv store per evaluation user, the
standard self-hosted deployment.

| Item | Value |
| --- | --- |
| Result | 86.10% LLM-as-judge (1,326 / 1,540); single-hop 90.01, multi-hop 80.85, temporal 84.11, open-domain 73.96 |
| Context tokens | 1,472.7 per question |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | `locomo10.json`, SHA-256 `79fa87e90f04081343b8c8debecb80a9a6842b76a7aa537dc9fdf651ea698ff4`; original answer key; categories 1–4 |
| Coverage | 1,540 searched, answered and judged; 0 failed, 0 skipped; denominator 1,540 |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |

## How it ran

1. `./scripts/run_locomo_eval.sh --lib maasv --env .env.maasv --workers 1 --version maasv_v0446_r2`: steps 1–6. Ingestion, search and answers completed for all 1,540 questions. The judge stage marked one conversation (81 questions) failed because one judge reply was not valid JSON (`JSONDecodeError`), so the run ended without a complete score.
2. `./scripts/run_locomo_eval.sh --lib maasv --env .env.maasv --version maasv_v0446_r2 --from-step 4`: re-ran the judge stage for all 1,540 answers (not only the failed conversation), then metrics and report. The judged records, grades and report in this bundle are from this second judge pass. This invocation rewrote `experiment_config.sh` with the runner's default `WORKERS=2`; ingestion and search ran with `--workers 1` in invocation 1.

## Contents

- `results/maasv-maasv_v0446_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
