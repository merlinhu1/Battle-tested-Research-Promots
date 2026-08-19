# Battle-Tested Research Prompts

An elegant, curated gallery of research prompts with **proven yield** — the
actual prompts (and full transcripts) that frontier AI labs released alongside
significant, verified research results.

## Inclusion criteria (firm)

A prompt enters this gallery only if:

1. **The prompt is available** — published/released verbatim (PDF, dataset, or
   page) and collected here as `.md`.
2. **It targets a research task** — mathematics, science, or engineering
   discovery, not a demo.
3. **It is battle-tested with proven yield** — it produced a significant,
   independently validated result in its field (published paper, wet-lab
   validation, formal verification, or expert-reviewed proof).

No prompt without a proven yield is ever included.

## The Gallery

### OpenAI

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Cycle Double Cover Conjecture](prompts/openai/cycle-double-cover-conjecture/) | Graph theory | Complete proof of the CDC conjecture (all finite bridgeless loopless multigraphs), via GPT 5.6 Sol Ultra with 64-agent adversarial search | 2026 |
| [First Proof? — solve/verify/refine templates](prompts/openai/first-proof/) | Competition mathematics | Programmatic pipeline producing model-verified solutions to 1stproof.org problems (3/4 correct on the BSS seed idea for Problem #6) | Feb 2026 |

### Anthropic

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Riemann zeta — 67.2% critical-line bound](prompts/anthropic/riemann-zeta-critical-line/) | Analytic number theory | Lower bound on zeros of ζ on the critical line improved from 41.6% to 67.2%; Lean-formalized; expert-reviewed. Launched by a one-line human prompt ("Take a real stab at the Riemann hypothesis") + full sub-agent transcripts | Aug 10, 2026 |
| [De novo protein binder design campaign](prompts/anthropic/protein-binder-design/) | Computational biology | Wet-lab-confirmed binders against 14/15 targets; 22–35% hit rates vs. 10–15% human baseline; state-of-the-art affinities. ~30k-token autonomous campaign prompt + kickoff messages + 2-sentence chemistry prompts | Aug 18, 2026 |

### Google DeepMind / Google Research

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Co-Scientist agent prompts & research goals](prompts/google-deepmind/co-scientist/) | Biomedical hypothesis generation | Nature-published multi-agent system; lab-validated AML repurposing (KIRA6), anti-fibrotic targets (91% response blockade), and re-discovery of unpublished cf-PICI mechanism | May 19, 2026 |

## Conventions

- Each entry lives in `prompts/<lab>/<entry>/` with:
  - `README.md` — metadata table (lab, model, field, **yield**, date, sources)
    and analysis of the prompt techniques that worked.
  - The verbatim prompt(s) as `.md` (machine-extracted where the source is a
    PDF — noted inline, with the authoritative source linked).
  - Full transcripts where released.
- Extraction provenance is documented in an HTML comment at the top of every
  extracted file; the original source is always linked and authoritative.
