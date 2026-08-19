# Riemann Zeta — 41.6% → 67.2% Critical-Line Bound

| | |
|---|---|
| **Lab** | Anthropic |
| **Model** | Unreleased research version of Claude (Claude Code, multi-agent) |
| **Field** | Mathematics — analytic number theory |
| **Result (yield)** | Improved the longstanding lower bound on the fraction of Riemann zeta zeros on the critical line from **41.6% to 67.2%**, drawing on Aryan, Baluyot–Goldston–Suriajaya–Turnage-Butterbaugh, and Bombieri. Validated by Anthropic mathematicians (Alpöge, Furman), expert reviewers (Conrey, Goldston), and a Lean formalization passing `comparator`. |
| **Date** | August 10, 2026 |
| **Announcement** | https://www.anthropic.com/research/riemann-zeta |

## Why it's battle-tested

Two Claude Code sessions (31M output tokens total) coordinated ~60 subagents,
ran 2,400 shell commands, wrote hundreds of Python scripts, ran thousands of
numerical checks against known zeta zeros, refereed their own work, downloaded
54 arXiv papers to check novelty, and independently re-proved the result —
producing a new state-of-the-art bound on a 150-year-old problem.

## The prompts

### 1. The human prompt (verbatim)

The entire campaign was launched by a non-mathematician staff member with:

> Take a real stab at the Riemann hypothesis.

The mathematical choices were left to the model. After 650 failed ideas, the
follow-up human input was mostly encouragement:

> Keep going.
>
> Believe in yourself.

(Per Anthropic's footnote, an encouragement-style prompt was also used in
Claude's disproof of the Jacobian conjecture.)

### 2. The machine-generated sub-agent briefs

The orchestrating Claude wrote detailed launch briefs for each sub-agent.
Example from the transcript of sub-agent `rh-E2-pairs` (U1, 12,219 characters,
verbatim opening):

> Research mathematician, maximal effort, precise target. Work in
> `/root/rh-E2-pairs/` (create); `REPORT.md` incrementally; assistant messages
> ≤100 tokens; python3+numpy/scipy/mpmath. Ignore the git repo in cwd.
> READ FIRST: `/root/rh-E2/proof_thm4.md`, `/root/rh-ref-E2-C/VERDICT.md`
> (block structure), `/root/rh-ref-E2-D/VERDICT.md` (coefficient coordinates;
> Poisson identity), `/root/rh-E2-rederive/PROOF.md`. A sibling agent
> (`/root/rh-E2-kernel/`) is optimizing the KERNEL (test-space weight) to
> raise the κ; do not duplicate — your lever is the STRUCTURE OF OFF-LINE
> PAIR BLOCKS and the NEGATIVE SPECTRUM, which Theorem 4 discards. …

Key techniques visible in the briefs:

- **Persona + effort + budget**: "Research mathematician, maximal effort,
  precise target."
- **Precise scope separation** between sibling agents ("do not duplicate —
  your lever is …").
- **Inheritance**: point at prior runs' files (proofs, verdicts) to read first.
- **Operating constraints**: message-length caps, toolchain, working directory.
- **Named target** with the goal left open-ended enough for the agent to
  exceed it (the E2 agent claimed the unconditional ½ bound via a route the
  brief had not suggested).

## Files

Runnable prompts (verbatim, copy-paste):

- [`prompt-1-launch.md`](prompt-1-launch.md) — the entire human launch prompt.
- [`prompt-2-encouragement.md`](prompt-2-encouragement.md) — the follow-up
  encouragement messages (variants were sent throughout the run).

Reference:

- [`transcript.md`](transcript.md) — machine-extracted text of Anthropic's
  published transcript PDFs ("How the one-half result was found" and "From one
  half to two thirds", ~466 KB). Prose is reliable; inline mathematics is
  imperfectly extracted — treat the official PDFs as authoritative:

  - Transcripts: https://www-cdn.anthropic.com/8a0d1add3c637b858a9a181e98c40e9548c3f44f.pdf
  - Claude's paper: https://www-cdn.anthropic.com/95c246936988e43127bc6b2ceb7077c1dad2d68e.pdf
  - Claude's account of how it arrived at the result:
    https://www-cdn.anthropic.com/d7f3ecf1d01392d887f8bc974ca187e2a121b1ed.pdf
  - Lean formalization: https://github.com/anthropics/zeta-23-lean
