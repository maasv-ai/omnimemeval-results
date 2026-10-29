# Maasv on OmniMemEval LoCoMo: run records (2026-10-29)

Contributor-run evidence for the Maasv row in OmniMemEval's reproduced LoCoMo
table. Run by the Maasv team.

| Item | Value |
| --- | --- |
| Result | 85.26% LLM-as-judge (1,313 / 1,540); single-hop 89.42, multi-hop 80.50, temporal 83.80, open-domain 67.71 |
| Context tokens | 1,461.8 per question (2,251,148 answer prompt tokens / 1,540 calls); 45,718 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter (patches in `harness/`); no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service; top-k 20; the Maasv service made no LLM calls |
| Dataset | `locomo10.json`, SHA-256 `79fa87e90f04081343b8c8debecb80a9a6842b76a7aa537dc9fdf651ea698ff4`; original answer key; categories 1–4 |
| Coverage | 1,540 searched, answered and judged; 0 failed, 0 skipped, 0 timed out; denominator 1,540 |
| Answer model | `gpt-4.1-mini-2025-04-14`, direct OpenAI API |
| Judge model | `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Commands | `./scripts/run_locomo_eval.sh --lib maasv --env .env.maasv --version maasv_v0446_r1 --to-step 2`, then the same with `--from-step 3` |
| Checkpoints | Two invocations on one run version (steps 1–2, then 3–6); no stage re-run, no records re-evaluated |

## Contents

- `results/maasv-maasv_v0446_r1/`: the harness output directory: per-question
  search results (with the retrieved context), responses, judged records,
  grades, ingestion stats, token usage, `exp_report.md`, `experiment_config.sh`
  and `snapshot_eval.env` (the harness does not record credentials).
- `harness/`: `git format-patch` of the adapter and results-row commits on top of `7c79d46`.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

## Notes

- One store per conversation (all turns once, under the speaker A user ID), searched once per question (`shared_conv_search`). The answer template prints the retrieved memories under both speakers, so context tokens count them twice.
- The adapter in `harness/` was committed after the run with documentation-only changes to its docstring; its executable code is the code that ran.
- Maasv is not open source. These records support recomputing the aggregate and replaying the answer and judge stages.
