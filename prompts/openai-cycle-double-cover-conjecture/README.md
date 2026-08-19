# Cycle Double Cover Conjecture — GPT 5.6 Sol Ultra

| | |
|---|---|
| **Lab** | OpenAI |
| **Model** | GPT 5.6 Sol Ultra |
| **Field** | Mathematics — graph theory |
| **Result (yield)** | Complete proof of the Cycle Double Cover Conjecture, a 1973-era open problem (Szekeres 1973 / Seymour 1979). Verified by adversarial multi-agent audit. |
| **Date** | 2026 |
| **Source (PDF)** | https://cdn.openai.com/pdf/04d1d1e4-bc75-476a-97cf-49055cd98d31/cdc_prompt.pdf |

## Why it's battle-tested

The prompt produced a full, unconditional proof of the Cycle Double Cover Conjecture for all
finite bridgeless loopless multigraphs. The document above is OpenAI's verbatim release of the
prompt as given.

## Key prompt techniques

- **Precise, self-contained problem statement** — all definitions (multigraph, bridge, cycle,
  cycle double cover) are given explicitly; no terms left to interpretation.
- **Explicit completion criteria** — partial progress, special graph classes, bounded-length
  variants, reductions to other unproved conjectures, and fixed-size computational verification
  are named and excluded as *insufficient*.
- **Anti-circularity guards** — forbids "proving" the conjecture via equivalent statements.
- **Aggressive dynamic multi-agent orchestration** — up to 64 concurrent agents, portfolio
  diversity, independence preservation, approach-family registry, adversarial verification.
- **Anti-persuasion-by-optimism** — status reports and "routine" hand-waves are rejected;
  concrete lemmas, constructions, equations or counterexamples are demanded.
- **Minimum time budget** — "Spend at least 8 hours on this before even thinking of returning."
- **Scoped web use** — background literature only; no searching for the solution itself, and no
  declaring the problem open.

## Hidden user prompts (unpublished)

The task prompt above is complete as the agent message. However, these
user-authored inputs to the run were never published and are therefore
missing here:

- The harness **system prompt** of OpenAI's internal agent runtime.
- The **"multiagent v2" orchestration configuration** (64-agent setup,
  sub-agent briefs, tool schemas).

A reproduction must supply equivalents; yield is not attributable to the
task prompt alone.

## Files

- [`prompt.md`](prompt.md) — the full prompt, nothing else. Machine-extracted
  from the source PDF and stripped of the PDF's title/abstract framing; the
  file begins at the prompt's own "Current task statement" heading and ends at
  the prompt's final line. Copy the whole file and send it as one message.
  (The PDF's typography is authoritative for exact glyphs.)
