# First Proof? — Seed-Idea / Solve / Verify / Refine Templates

| | |
|---|---|
| **Lab** | OpenAI |
| **Model** | GPT 5.6-class internal model |
| **Field** | Mathematics — ten competition problems (1stproof.org) |
| **Result (yield)** | Model-generated solution attempts for all ten problems; for Problem #6, 3/4 runs on the BSS seed idea were judged correct by model verification, several with zero revision rounds. |
| **Date** | February 20, 2026 |
| **Source (PDF)** | https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf |

## Why it's battle-tested

These are the programmatic prompt templates OpenAI released for orchestrating
model attempts on the ten https://1stproof.org/ tasks. The full loop —
generate ideas → solve per idea → verify → revise — produced verified solutions,
and the templates are deliberately problem-independent.

## The pipeline

1. **Generate** — an "idea generator" prompt produces FIVE high-level approaches
   (JSON output) for the problem.
2. **Solve** — the problem + one seed idea is given to a solver, with the
   instruction *"Keep working hard until you have a complete and rigorous solution."*
3. **Verify** — a referee prompt checks the solution for critical gaps and
   validates bibliographic references, outputting structured `<CORRECT>`/`<GAPS>` blocks.
4. **Refine** — if gaps are found, a revision prompt feeds the referee's issues
   back, demanding a fix or a new approach. Repeat up to 3 times.

## Files

- [`prompt-templates.md`](prompt-templates.md) — Appendix A of the report
  (strategy + all four templates), machine-extracted from the source PDF.
- [`problem-6-filled-prompt.md`](problem-6-filled-prompt.md) — the real
  as-run prompt for Problem #6, reconstructed verbatim from the released
  components (problem statement + solve template + the winning BSS seed idea),
  plus all five generated ideas and the list of the other nine problems.
