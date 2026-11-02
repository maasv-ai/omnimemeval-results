# Maasv on OmniMemEval LoCoMo: run records (2026-10-31, run 2)

Contributor-run evidence for the Maasv LoCoMo row on Maasv v0.4.48. Run by the
Maasv team, one Maasv store per evaluation user (the standard self-hosted
deployment). It replaces the v0.4.46 result (86.10, `locomo-20261029-r2`),
whose records stay published. Run 1 on v0.4.48 (2026-10-31, 86.30) is not
published: the local Maasv service used for it did not return results the way
the shipped service does.

| Item | Value |
| --- | --- |
| Result | 87.73% LLM-as-judge (1,351 / 1,540); single-hop 91.80, multi-hop 82.98, temporal 85.98, open-domain 71.88 |
| Context tokens | 1,550.8 per question (2,388,178 answer prompt tokens / 1,540 calls); 47,137 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.48, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | `locomo10.json`, SHA-256 `79fa87e90f04081343b8c8debecb80a9a6842b76a7aa537dc9fdf651ea698ff4`; original answer key; categories 1 to 4 |
| Coverage | 1,540 searched, answered and judged; 0 failed, 0 skipped; denominator 1,540 |
| Answer / judge | `gpt-4.1-mini-2025-04-14` / `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_locomo_eval.sh --lib maasv --env .env.maasv --workers 1 --version maasv_v0448_locomo_r2` (one invocation, non-streaming; started 2026-10-31 22:21 ET, finished 22:36 ET) |

## Contents

- `results/maasv-maasv_v0448_locomo_r2/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
