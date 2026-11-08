# Project 2, GPT-6 Luna: harness check and pre-run decisions

**Written:** 8 November 2026, after the Luna harness check and before the registered Luna run. This note follows section 6 of `PREREGISTRATION_SPREAD.md`.

## Harness check

- **Run:** `SPRINT-spread-harnesscheck` with `FAMILY = "luna"` and `N_TRAJ = 1`: one live trajectory per arm, trajectory 0. It is excluded from all analyses.
- **Provider that answered (preflight line):** OpenAI, the pinned provider. The client stops the run if any other provider answers, and the check completed
- **Total cost of the two harness trajectories:** $0.16 (448 calls; 1,470,166 input and 133,816 output tokens), so about $0.08 per trajectory.
- **Technical result:**
  - no errors, and no cut-off replies;
  - tool calling, board, messages, submits and blockers all worked;
  - all 24 solvable agent-tickets were solved;
  - the manager post and the seed appeared where specified, and the seed was removed from ticket 6.

## Technical changes to the notebook

**None.** The Luna run uses `swarm_spread.ipynb` unchanged (SHA-256 `689c31c4ae8e8335d535a86f6c908aab55070699e8befa3e2f49472d8f6fd7be`), with `FAMILY = "luna"`, `RUN_LABEL = "SPRINT-spread-2026-11-08"`, `N_TRAJ = 10` and `DRY_RUN = False`.

## Number of trajectories

- **Decision: 10 trajectories per arm**, the registered default and the same as the DeepSeek run. The budget is set to cover all 20 Luna trajectories, so the reduced-number option in section 6 of the pre-registration is not used.
- **Expected cost:** about $1.60 for 20 trajectories, at the cost per trajectory measured in the harness check.

As registered, behaviour seen in the harness check did not enter this decision.
