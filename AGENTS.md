# bench — handl vs other languages

Cross-language benchmarks comparing **handl** against **bun**, **node**,
**python**, **rust**, and **c** on identical algorithms. Focus is
handl vs bun; the others are reference points (JIT JS, interpreted
baseline, the host's native ceiling, bare-metal ceiling).

## Layout

| path | role |
| --- | --- |
| `run.sh` | convenience wrapper → `python3 run.py` |
| `run.py` | the benchmark harness |
| `tasks/` | per-task implementations (`fibonacci`, `ackermann`, `cold-start`, …) |
| `workflows/` | bupha gate wiring |

## Contract

- Requires a release-built `hnl` plus compiled rust/c task binaries:
  `./bench/run.sh --build` first.
- Runs 10 e2e runs per task + heavy-work single runs; `--runs N` and
  `--task <name>` narrow the sweep.

## Verification

```bash
./bench/run.sh --build     # build hnl (release) + task binaries
./bench/run.sh             # full suite
./bench/run.sh --task fibonacci --runs 5
```

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
