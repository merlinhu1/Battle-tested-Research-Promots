# Battle-Tested Research Prompts

An elegant, curated gallery of research prompts with **proven yield** — the
actual prompts (and full transcripts) that frontier AI labs released alongside
significant, verified research results.

## The Gallery

### OpenAI

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Cycle Double Cover Conjecture](prompts/openai-cycle-double-cover-conjecture/) | Graph theory | Complete proof of the CDC conjecture (all finite bridgeless loopless multigraphs), via GPT 5.6 Sol Ultra with 64-agent adversarial search | 2026 |
| [First Proof? — solve/verify/refine templates](prompts/openai-first-proof/) | Competition mathematics | Programmatic pipeline producing model-verified solutions to 1stproof.org problems (3/4 correct on the BSS seed idea for Problem #6) | Feb 2026 |
| [Gluon → graviton single-minus amplitudes](prompts/openai-gluon-to-graviton/) | Quantum gravity | ChatGPT 5.2 Pro generalized the gluon amplitudes paper to gravity from a one-paragraph research instruction, producing the preprint "Single-minus graviton tree amplitudes are nonzero". Full 110-page conversation transcript released | Feb 28, 2026 |

### Anthropic

| Entry | Field | Yield | Date |
|---|---|---|---|
| [De novo protein binder design campaign](prompts/anthropic-protein-binder-design/) | Computational biology | Wet-lab-confirmed binders against 14/15 targets; 22–35% hit rates vs. 10–15% human baseline; state-of-the-art affinities. ~30k-token autonomous campaign prompt + kickoff messages | Aug 18, 2026 |
| [Automated W2S researcher](prompts/anthropic-automated-w2s-researcher/) | AI alignment research | 9 parallel Claude Opus 4.6 agents reached PGR 0.97 vs. 0.23 human baseline on weak-to-strong supervision. Full prompt stack published (system prompt + skill + critic prompts, MIT) | Apr 14, 2026 |

### Google DeepMind / Google Research

| Entry | Field | Yield | Date |
|---|---|---|---|
| [Co-Scientist agent prompts & research goals](prompts/google-deepmind-co-scientist/) | Biomedical hypothesis generation | Nature-published multi-agent system; lab-validated AML repurposing (KIRA6), anti-fibrotic targets (91% response blockade), and re-discovery of unpublished cf-PICI mechanism | May 19, 2026 |

### Academic / other labs

| Entry | Field | Yield | Date |
|---|---|---|---|
| [SPARK — System of Pathology Agents](prompts/spark-pathology-agents/) | Cancer pathology | Nature Medicine: autonomous hypothesis→code→validation pipeline produced survival-validated prognostic biomarkers on real patient cohorts. Full CrewAI agent/task prompts published | Apr 29, 2026 |

## Yield criteria (firm)

All four requirements must hold for a prompt to enter this gallery:

1. **The prompt is available** — released verbatim by its source (PDF,
   dataset, or web page) and collected here as a copy-paste-runnable `.md`
   file.
2. **It is related to a research task** — mathematics, science, or engineering
   discovery, not a demo or toy.
3. **It is battle-tested** — actually used in the run that produced the
   result, not a post-hoc reconstruction.
4. **It produced significant yield in its field** — a result independently
   validated by publication in a peer-reviewed venue, wet-lab confirmation,
   formal verification (e.g. Lean), or expert review. The yield is stated
   concretely in every entry README.

**Never include a prompt without a proven yield.**

**Usability requirement:** the published prompt must carry the causal weight
of the yield. Entries whose published prompts are one-liners (or otherwise
insubstantial) while the actual instructions lived in undisclosed harness
system prompts, skills, or project instructions are **unusable** and are
excluded — this repository collects useful prompts, not exercises in
reverse-engineering hidden context. Every entry README still discloses
whatever user-authored context remains unpublished (harness configs, tool
schemas) so yields are never overstated.

## Conventions

- **Hard requirement: every entry contains one or more pure prompt files
  (named `prompt*.md`) whose entire content is the prompt — no commentary, no
  headers, no provenance notes. Copy the file's full content and run it
  verbatim.** Supporting material (provenance, analysis, transcripts,
  context) lives in separate files (`README.md`, `*-context.md`,
  `transcript.md`, etc.).
- Each entry lives in `prompts/<lab>-<entry>/` (flat — no per-company nesting) with:
  - `README.md` — metadata table (lab, model, field, **yield**, date, sources)
    and analysis of the prompt techniques that worked.
  - `prompt*.md` — the verbatim, runnable prompt(s).
  - Full transcripts where released.
- Extraction provenance is documented in the entry README or context file;
  the original source is always linked and authoritative.

## Rejected entries

| Candidate | Rejected because |
|---|---|
| Anthropic — Riemann zeta 67.2% critical-line bound (Aug 10, 2026) | Has hidden, undiscoverable user prompts: the published human inputs are one-liners ("Take a real stab at the Riemann hypothesis", "Keep going / Believe in yourself"); the yield derives from an unreleased research model's hidden harness system prompt, skills, and CLAUDE.md-style instructions. Unusable — deleted. |
| Anthropic — NMR / LC-MS analytical-chemistry one-liners (Aug 18, 2026) | Same character: two-sentence prompts whose yield is attributable to the unpublished Claude Science harness and skills. Deleted from the protein-design entry. |
| OpenAI — Graviton amplitudes preprint alone (cdn.openai.com/pdf/graviton.pdf, Mar 4, 2026) | The preprint itself contains no prompts. The graviton work was ACCEPTED via its companion transcript release (gluon-to-graviton-paper.pdf), which publishes the full ChatGPT conversation — see the [Gluon → graviton entry](prompts/openai-gluon-to-graviton/). |
