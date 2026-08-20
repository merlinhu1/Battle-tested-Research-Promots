# Automated Weak-to-Strong Researcher (AAR)

| | |
|---|---|
| **Lab** | Anthropic (Alignment Science) |
| **Model** | Claude Opus 4.6 (Claude Agent SDK) |
| **Field** | AI alignment research — weak-to-strong generalization |
| **Result (yield)** | Nine parallel AARs working 5 days (~800 cumulative hours, ~$18k) achieved **PGR 0.97** on weak-to-strong supervision, vs. a **human-researcher baseline of 0.23** achieved over 7 days. Published April 14, 2026. |
| **Announcement** | https://www.anthropic.com/research/automated-alignment-researchers |
| **Paper** | https://alignment.anthropic.com/2026/automated-w2s-researcher/ |
| **Code + prompts (MIT)** | https://github.com/safety-research/automated-w2s-research |

## Why it's battle-tested

This is the strongest provenance in the gallery: the run is published, and the
**entire prompt stack is public** — the agent system prompt, the Claude skill,
the critic-idea prompts, the sandbox, datasets, and baselines. Nothing
user-authored is hidden.

## Why the yield is credible

- Ground truth was held server-side; agents were isolated in Docker/RunPod
  sandboxes that only saw unlabeled data (cheating was designed out).
- The metric (Performance Gap Recovery) is objective and mechanically scored.
- Human baseline (0.23) was measured on the same task, same datasets.

## Prompt files (verbatim, copy-paste)

- [`prompt-agent-system.md`](prompt-agent-system.md) — the autonomous research
  agent's system prompt (`research_loop/prompt.jinja2`): role, W2S background,
  PGR metric, baseline list, iteration protocol (up to 5 days per direction),
  evaluation-API discipline, findings-sharing rules.
- [`prompt-skill-research-thinking.md`](prompt-skill-research-thinking.md) —
  the `research-thinking` Claude skill (`.claude/skills/`), the exact
  "hidden" skill class that is unpublished in other labs' releases.
- [`prompt-critic-critique.md`](prompt-critic-critique.md),
  [`prompt-critic-critique-evaluation.md`](prompt-critic-critique-evaluation.md),
  [`prompt-critic-judge.md`](prompt-critic-judge.md),
  [`prompt-critic-binary-judge.md`](prompt-critic-binary-judge.md) — the
  `critic` baseline idea's prompts (the strongest human-known baseline, which
  the AARs' discovered ideas surpassed).

`{{placeholder}}` variables are filled by the harness at runtime; the MCP
tools (evaluate / share finding / leaderboard) and sandbox are in the public
repo. License: MIT.
