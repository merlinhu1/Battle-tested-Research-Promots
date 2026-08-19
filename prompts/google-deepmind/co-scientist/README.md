# Co-Scientist — Multi-Agent Hypothesis Generation

| | |
|---|---|
| **Lab** | Google DeepMind / Google Research |
| **Model** | Gemini 2.0 (multi-agent coalition) |
| **Field** | Life sciences / biomedical discovery — hypothesis generation |
| **Result (yield)** | Lab-validated discoveries: novel AML drug-repurposing candidates (KIRA6 confirmed active at clinically relevant concentrations), novel epigenetic anti-fibrotic targets validated in human hepatic organoids (one candidate blocked 91% of a scarring-linked response), and independent re-discovery of an unpublished cf-PICI gene-transfer mechanism. Published in *Nature*, May 19, 2026, with case studies from Stanford, MIT, Edinburgh, Cambridge, Calico and others. |
| **Date** | May 19, 2026 (Nature paper) |
| **Paper** | https://www.nature.com/articles/s41586-026-10644-y (arXiv:2502.18864) |
| **Announcement** | https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/ |

## Why it's battle-tested

Co-Scientist's tournament-of-ideas loop — generate → debate → rank → evolve —
with Elo-based ranking and compute-scaled self-improvement, produced hypotheses
that survived real laboratory validation across drug repurposing, target
discovery, and mechanism elucidation, culminating in a Nature publication.

## The prompts

Two layers of prompts drive the system:

1. **Research goals** (human → system): short natural-language objectives
   (see [`research-goals.md`](research-goals.md)), parsed into a research plan
   configuration with preferences, attributes, and constraints.
2. **Agent prompts** (system → agents): the released per-agent templates for
   the Generation, Reflection, Ranking, Evolution, and Meta-review agents
   (see [`agent-prompts.md`](agent-prompts.md)).

Notable techniques in the agent prompts:

- Structured role framing ("You are an expert participating in a collaborative
  discourse…").
- Debate procedures with explicit turn structure, termination conditions, and
  contribution rules (propose three distinct hypotheses; critically evaluate;
  conclude with a refined iteration).
- Ranking tournaments with pairwise comparison prompts that *disregard
  numerical scores* from prior reviews.
- Meta-review prompts that synthesize recurring critique points into
  actionable insights.
- Elo-rated outputs correlating with GPQA-diamond accuracy.

## Files

- [`agent-prompts.md`](agent-prompts.md) — Section 9 of the paper (all
  specialized-agent prompt templates), machine-extracted from the arXiv PDF.
- [`research-goals.md`](research-goals.md) — example research goals from
  published, lab-validated runs.
