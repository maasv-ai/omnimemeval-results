# Maasv on OmniMemEval PersonaMem v2: run records (2026-10-30)

Contributor-run evidence for the Maasv PersonaMem v2 row. Run by the Maasv team,
one Maasv store per evaluation user (the standard self-hosted deployment).

| Item | Value |
| --- | --- |
| Result | Accuracy 35.48 (1,774 / 5,000), option matching, no LLM judge; four options per question |
| Context tokens | 2,831.7 per question (14,158,503 answer prompt tokens / 5,000 calls); 23,042 completion tokens |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter; no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service, one store per evaluation user; top-k 20; the Maasv service made no LLM calls |
| Dataset | PersonaMem v2 from the runner's `prepare_personamem.py` (`benchmark/text/benchmark.csv`, SHA-256 `95f2a8a324aab7baf2af937feae12731369e2abf7cad5ab3e170594cb25a3e52`, plus 200 `chat_history_32k` files): 200 personas, 5,000 questions |
| Coverage | 5,000 searched and answered; 0 failed, 0 skipped |
| Answer model | `gpt-4.1-mini-2025-04-14`, direct OpenAI API |
| Command | `./scripts/run_pmv2_eval.sh --lib maasv --env .env.maasv --workers 1 --version maasv_v0446_pmv2_r1` (one invocation, non-streaming; started 2026-10-30 12:38 ET, finished 15:32 ET) |

By preference type (accuracy): anti-stereotypical 35.67 (855), ask-to-forget
37.21 (1,048), health and medical 30.28 (568), neutral 34.62 (858), sensitive
33.86 (511), stereotypical 39.77 (533), therapy background 35.89 (627).

## Contents

- `results/maasv-maasv_v0446_pmv2_r1/`: the harness output directory.
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer stage.
