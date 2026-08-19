# Battle-Tested Research Prompts

An elegant, curated gallery of research prompts with **proven yield** — the
actual prompts (and full transcripts) that frontier AI labs released alongside
significant, verified research results.

## Yield criteria (firm)

All four requirements must hold for a prompt to enter this gallery:

1. **The prompt is available** — released verbatim by its source (PDF,
   dataset, or web page) and collected here as `.md`.
2. **It is related to a research task** — mathematics, science, or engineering
   discovery, not a demo or toy.
3. **It is battle-tested** — actually used in the run that produced the
   result, not a post-hoc reconstruction.
4. **It produced significant yield in its field** — a result independently
   validated by publication in a peer-reviewed venue, wet-lab confirmation,
   formal verification (e.g. Lean), or expert review. The yield is stated
   concretely in every entry README.

**Never include a prompt without a proven yield.**

## The Gallery

### OpenAI

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Cycle Double Cover Conjecture](prompts/openai-cycle-double-cover-conjecture/) | Graph theory | Complete proof of the CDC conjecture (all finite bridgeless loopless multigraphs), via GPT 5.6 Sol Ultra with 64-agent adversarial search | 2026 |
| [First Proof? — solve/verify/refine templates](prompts/openai-first-proof/) | Competition mathematics | Programmatic pipeline producing model-verified solutions to 1stproof.org problems (3/4 correct on the BSS seed idea for Problem #6) | Feb 2026 |

### Anthropic

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Riemann zeta — 67.2% critical-line bound](prompts/anthropic-riemann-zeta-critical-line/) | Analytic number theory | Lower bound on zeros of ζ on the critical line improved from 41.6% to 67.2%; Lean-formalized; expert-reviewed. Launched by a one-line human prompt ("Take a real stab at the Riemann hypothesis") + full sub-agent transcripts | Aug 10, 2026 |
| [De novo protein binder design campaign](prompts/anthropic-protein-binder-design/) | Computational biology | Wet-lab-confirmed binders against 14/15 targets; 22–35% hit rates vs. 10–15% human baseline; state-of-the-art affinities. ~30k-token autonomous campaign prompt + kickoff messages + 2-sentence chemistry prompts | Aug 18, 2026 |

### Google DeepMind / Google Research

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Co-Scientist agent prompts & research goals](prompts/google-deepmind-co-scientist/) | Biomedical hypothesis generation | Nature-published multi-agent system; lab-validated AML repurposing (KIRA6), anti-fibrotic targets (91% response blockade), and re-discovery of unpublished cf-PICI mechanism | May 19, 2026 |

## Conventions

- Each entry lives in `prompts/<lab>-<entry>/` (flat — no per-company nesting):
  - `README.md` — metadata table (lab, model, field, **yield**, date, sources)
    and analysis of the prompt techniques that worked.
  - The verbatim prompt(s) as `.md` (machine-extracted where the source is a
    PDF — noted inline, with the authoritative source linked).
  - Full transcripts where released.
- Extraction provenance is documented in an HTML comment at the top of every
  extracted file; the original source is always linked and authoritative.
