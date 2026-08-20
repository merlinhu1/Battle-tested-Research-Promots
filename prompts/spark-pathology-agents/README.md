# SPARK — System of Pathology Agents for Research and Knowledge

| | |
|---|---|
| **Lab** | Tolkach Lab (cpath-ukk), University Hospital Cologne |
| **Model** | ChatGPT-o1 (idea tasks) and claude-3-5-sonnet (coding tasks), via CrewAI |
| **Field** | Cancer pathology — autonomous biomarker discovery |
| **Result (yield)** | Published in *Nature Medicine* (Apr 29, 2026): SPARK autonomously generated biological hypotheses from whole-slide images, implemented them as analysis tools, and identified prognostic biomarkers validated by survival analysis (Cox regression, Kaplan–Meier) on real patient cohorts. Companion paper: independently reproduced pathology-based reasoning. |
| **Paper** | https://doi.org/10.1038/s41591-026-04357-y (companion: s41591-026-04403-9) |
| **Code + prompts** | https://github.com/cpath-ukk/SPARK |

## Why it's battle-tested

Peer-reviewed (Nature Medicine), end-to-end autonomous: idea generation →
review → duplicate detection → refinement → code generation → verification →
slide-level analysis → patient-level prognostic validation. The yield is
clinically grounded (survival-validated biomarkers), not just textual.

## Prompt files (verbatim, drop-in)

- [`agents.yaml`](agents.yaml) — the CrewAI agent definitions (role / goal /
  backstory) for every agent in the generative pipeline: idea generator,
  idea reviewer, duplicate detector, idea refiner, and more.
- [`tasks.yaml`](tasks.yaml) — the full task instructions (~128 KB) for all
  three idea-generation use cases (B: survival/progression, C: metastatic
  spread, D: multiplexed TMA), idea refinement, coding, and verification —
  the complete prompt text as used in the publication.

These are the exact configuration files the publication ran with ("you may
also use the provided configurations to ensure reproducibility"). Drop them
into the repo's `Generative_and_Prognostic_Pipeline/config/` to reproduce.

## Hidden user prompts (unpublished)

None material — the agent and task prompts above are the complete
instruction set. Surrounding context: the CrewAI framework defaults and the
code-verification pipeline's runtime prompts in the repo. Note the repo
license is CC BY-NC-SA 4.0 (non-commercial share-alike) — prompts are
reproduced here verbatim with attribution; consult the repo for terms.
