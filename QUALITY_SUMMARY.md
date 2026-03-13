# EP API Quality Summary

This summary explains the latest valid quality benchmark release in plain language.

## What was tested

- 10 fixed prompts
- 2 providers: local and OpenAI
- Same EP API surface
- Same request structure and response schema
- Real local backend run, not simulation

## Main conclusion

The latest valid rerun confirms that both providers completed the full quality benchmark successfully through the same EP API surface. OpenAI achieved the higher average quality score, while the local backend remained competitive and reached parity on several prompts.

## Provider totals

| Provider | Runs | Successes | Avg quality score | Avg latency ms | Avg total tokens | Avg content words |
|---|---:|---:|---:|---:|---:|---:|
| Local | 10 | 10 | 24.5 | 7178.5 | 292.0 | 150.6 |
| OpenAI | 10 | 10 | 26.2 | 4921.7 | 293.4 | 157.1 |

## Pairwise comparison

- OpenAI quality wins: 7
- Local quality wins: 0
- Quality ties: 3
- OpenAI faster: 6
- Local faster: 4
- Speed ties: 0

## Interpretation

- OpenAI remains stronger on average for compressed, polished, public-facing output.
- The local backend is already usable for internal analytical work and stays close on several prompts.
- The benchmark now supports routing-policy work because the comparison uses a real local model instead of a simulation stub.

## Decision baseline

This file refers only to the latest valid real-local rerun. Earlier invalid or simulation-based quality comparisons should not be used as the decision baseline.

## Source files

- reports/quality/latest_quality_benchmark.txt
- reports/quality/latest_quality_benchmark.json

## Generated

- Benchmark timestamp: 2026-03-13T14:34:41+00:00
