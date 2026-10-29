# Maasv on OmniMemEval BEAM 100K: run records (2026-10-29)

Contributor-run evidence for the Maasv row in OmniMemEval's reproduced BEAM
table. Run by the Maasv team.

| Item | Value |
| --- | --- |
| Result | Nugget score 74.83 ± 32.87 (per-question SD), 400 questions |
| Context tokens | 8,675.5 per question (3,470,215 answer prompt tokens / 400 calls); 208,362 completion tokens |
| Judge calls | 878 (808,039 prompt tokens, 42,177 completion tokens) |
| Harness | MemTensor/OmniMemEval `7c79d46e31dd85f3da2509b430bba9406656dd28` + the `maasv` adapter (same executable code as the LoCoMo run); no pipeline, prompt or metric changes |
| Backend | Maasv v0.4.46, self-hosted service; top-k 20; the Maasv service made no LLM calls |
| Dataset | BEAM 100K (`beam_100k.json` from the runner's `prepare_beam.py --scale 100k`): 20 conversations, 5,732 messages, 400 probing questions |
| Coverage | 400 searched, answered and judged; 0 failed, 0 skipped; 0 failed conversations at ingestion |
| Answer model | `gpt-4.1-mini-2025-04-14`, direct OpenAI API |
| Judge model | `gpt-4o-mini-2024-07-18`, direct OpenAI API; one judge run |
| Command | `./scripts/run_beam_eval.sh --lib maasv --env .env.maasv --version maasv_v0446_beam100k_r1 --scale 100k` (one invocation, non-streaming) |

By dimension (nugget score, 40 questions each): abstention 88.75,
contradiction resolution 64.38, event ordering 33.50, information extraction
96.25, instruction following 87.50, knowledge update 62.50, multi-session
reasoning 69.57, preference following 92.92, summarization 79.83, temporal
reasoning 73.12.

## Contents

- `results/maasv-maasv_v0446_beam100k_r1/`: the harness output directory:
  per-question search results (with the retrieved context), responses, judged
  records, grades, ingestion stats, token usage, `exp_report.md`,
  `experiment_config.sh` and `snapshot_eval.env` (the harness does not record credentials).
- `SHA256SUMS`: checksums of every file in this bundle.

Edits to the harness output, nothing else changed: in `experiment_config.sh`
the local home directory path is replaced with `~`; in `snapshot_eval.env` a
two-line comment with local service start-up instructions is replaced with
`# Start the Maasv service first.`

Maasv is not open source. These records support recomputing the aggregate and
replaying the answer and judge stages.
