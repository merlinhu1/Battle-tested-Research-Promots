# First Proof? — Runnable Solve/Verify/Refine Prompt Pipeline

| | |
|---|---|
| **Lab** | OpenAI |
| **Model** | GPT 5.6-class |
| **Field** | Mathematics — competition problems (1stproof.org) |
| **Result (yield)** | Run as released on Problem #6: four solver runs on the BSS seed idea, 3/4 judged correct by the verification loop — two with zero revision rounds, one after a single revision. |
| **Date** | February 20, 2026 |
| **Source (PDF)** | https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf |

## Why it's battle-tested

This exact pipeline was executed as released and produced the reported yield:
on Problem #6, OpenAI generated four solutions per seed idea using the solve
template, passed each through the verify/revise loop, and the BSS seed idea
yielded 3/4 model-verified correct solutions (Section A.4/B of the report).

The prompts are complete and runnable. Nothing is withheld: the report
publishes the templates, the verbatim problem statements, and the generated
seed ideas, which is everything the pipeline consumes.

## Running it

Execute the loop as specified (Appendix A.1):

1. **Generate** — run the idea-generator template on the problem → FIVE
   approaches (JSON).
2. **Solve** — for each idea, run **four** independent solver runs of the
   solve template (problem + idea).
3. **Verify** — run the verify template on each solution (`<CORRECT>`/`<GAPS>`).
4. **Revise** — on gaps, run the refinement template; repeat up to **3 times**.

The filled solve prompt for the proven Problem #6 run (winning BSS seed idea)
is in [`problem-6-filled-prompt.md`](problem-6-filled-prompt.md) — runnable
as-is.

## Files

- [`prompt-templates.md`](prompt-templates.md) — all five templates
  (generate / solve / verify / refine / typeset), machine-extracted from the
  source PDF.
- [`problem-6-filled-prompt.md`](problem-6-filled-prompt.md) — the complete
  as-run solve prompt for Problem #6 (problem statement + BSS seed idea),
  plus all five generated ideas and the other nine problem statements.
