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

## Hidden user prompts (unpublished)

The per-agent templates are the real agent prompts. Unpublished
user-authored context:

- Any **harness/supervisor system prompts** and the orchestration code.
- **Tool-use instructions** for the integrated systems (web search, ChEMBL,
  UniProt, AlphaFold) and safety classifiers.

## Files

Runnable prompt templates (verbatim, one per file; `{placeholders}` are filled
by the orchestrator at runtime):

- [`prompt-generation-literature-review.md`](prompt-generation-literature-review.md) — Generation agent
- [`prompt-generation-debate.md`](prompt-generation-debate.md) — Generation agent (debate mode)
- [`prompt-generation-observations.md`](prompt-generation-observations.md) — observations explained by a hypothesis
- [`prompt-ranking-tournament.md`](prompt-ranking-tournament.md) — Ranking agent (pairwise comparison)
- [`prompt-ranking-debate.md`](prompt-ranking-debate.md) — Ranking agent (simulated debate)
- [`prompt-evolution-feasibility.md`](prompt-evolution-feasibility.md) — Evolution agent (feasibility improvement)
- [`prompt-evolution-out-of-box.md`](prompt-evolution-out-of-box.md) — Evolution agent (out-of-the-box thinking)
- [`prompt-meta-review.md`](prompt-meta-review.md) — Meta-review agent

Reference:

- [`agent-prompts.md`](agent-prompts.md) — Section 9 of the paper with all
  templates in context (headings and provenance note included).
- [`research-goals.md`](research-goals.md) — example research goals from
  published, lab-validated runs (the top-level prompts given by scientists).
