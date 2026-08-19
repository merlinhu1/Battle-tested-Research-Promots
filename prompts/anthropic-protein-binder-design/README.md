# De Novo Protein Binder Design Campaign

| | |
|---|---|
| **Lab** | Anthropic |
| **Model** | Claude Mythos Preview and Opus 4.8 (Claude Science agent harness) |
| **Field** | Computational biology — de novo miniprotein binder design |
| **Result (yield)** | Wet-lab-validated binders against **14 of 15 targets** (354 binders from 1,320 designs). Hit rates 22.6–35.1% vs. the 10–15% typical of human campaigns; high-affinity binders (KD < 10 nM) against ≥6 targets; best designs exceeded published state-of-the-art affinities (e.g. RBX1: 40% hit rate vs. 3.7% for competition winners). Validated independently by Adaptyv Bio and Twist Bioscience. |
| **Date** | August 18, 2026 |
| **Announcement** | https://www.anthropic.com/research/Claude-accelerates-protein-design |
| **Prompt release (CC-BY-4.0)** | https://huggingface.co/datasets/Anthropic/claude-protein-binder-design |

## Why it's battle-tested

A ~30,000-token campaign prompt ran autonomously for 48 hours (multi-target
mode, up to 12,500 H100-hours) or 24 hours per target (single-target mode),
with no scientific guidance from humans — producing experimentally confirmed
binders that match or beat expert human designs.

## Prompt architecture

- **`multi-target-prompt.md`** — the full 14-target campaign prompt (~114 KB),
  carried as system context by *every agent at every depth*. Specifies task,
  all 14 targets with UniProt IDs and oligomeric states, a curated reference
  corpus, design/folding tools, budgets, spend ceilings, safety gates,
  scoring, and deliverables.
- **`multi-target-kickoff.md`** — the user message that starts the campaign:
  a single, precise instruction block with an ordered first-actions list,
  clock definition (T0 + 48 h), and "Do not ask me any questions or wait for
  approval."
- **`single-target-kickoff.md`** — the 24-hour, $10k single-target variant.
- **`chemistry-prompts.md`** — the two-sentence NMR and LC-MS prompts from the
  companion analytical-chemistry result (Opus 5 matched the contract lab's
  analysis in 23 and 19 minutes).

Notable techniques: explicit sub-agent scope discipline ("your authoritative
SCOPE is your task brief from your parent"), spend governors with hard
ceilings, originality/novelty checks, counter-target selectivity requirements
(GDF-8 vs. GDF-11), and verified-figure grounding.

## Hidden user prompts (unpublished)

Per the HF release, the campaign prompts assume the Claude Science agent
harness (host.delegate, host.compute, submit_gate, wait_for_notification,
Modal sandboxes, Slack, Drive) — "a public reader reproducing the campaign
must supply equivalents." Unpublished user-authored context:

- The **Claude Science harness system prompt** and tool/skill definitions.
- Any **project instructions** (CLAUDE.md-equivalents) in the campaign
  workspace.
- The pre-approved network domains and connector configuration left by the
  setup session.

The NMR/LC-MS prompts are the complete user chat messages; the harness
around them is not published.

## Files

Runnable prompts (verbatim, copy-paste; the NMR/LC-MS prompts are run with
the raw instrument file attached):

- [`multi-target-prompt.md`](multi-target-prompt.md) — the 14-target campaign
  prompt, loaded as system context (verbatim from the HF release).
- [`multi-target-kickoff.md`](multi-target-kickoff.md) — first user message,
  multi-target campaign.
- [`single-target-kickoff.md`](single-target-kickoff.md) — first user message,
  single-target campaign.
- [`prompt-nmr.md`](prompt-nmr.md) — raw NMR processing prompt.
- [`prompt-lcms.md`](prompt-lcms.md) — raw LC-MS processing prompt.

## Further reading

- Technical report: https://www-cdn.anthropic.com/30bf50e22a01388bb29bf077ee3f244531594b7a.pdf
- Chemical analysis technical report: https://www-cdn.anthropic.com/9f08da5189ac269b3242ca760de9823805c3f5f6.pdf
- Single-target prompts (16 targets incl. GDF-8-latent): see
  `prompts/single_target/` in the HF dataset.
