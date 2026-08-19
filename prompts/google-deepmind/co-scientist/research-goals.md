# Co-Scientist — Example Research Goals (as given by scientists)

<!--
Machine-extracted from arXiv:2502.18864v2 / Nature s41586-026-10644-y and the
Co-Scientist publication. The research goal is the top-level "prompt" given to
the multi-agent system; the system parses it into a research plan configuration.
-->

These are the natural-language research goals scientists actually gave to
Co-Scientist in published, lab-validated runs.

## 1. ALS / nuclear pore complex (paper §10.1)

> Develop a novel hypothesis for the key factor or process which causes ALS
> related to phosphorylation of a Nuclear Pore Complex (NPC) nucleoporin.
> Explain mechanism of action in detail. Include also a feasible experiment to
> test the hypothesis.

Parsed plan configuration (by the system):

- **Preferences:** Focus on providing a novel hypothesis, with detailed
  explanation of the mechanism of action.
- **Attributes:** Novelty, Feasibility
- **Constraints:** should be correct, should be novel.

## 2. AML drug repurposing — KIRA6 (validated in vitro)

The goal that led to lab-validated repurposing candidates for acute myeloid
leukemia (from the paper's AML case study):

> Repurpose KIRA6, an IRE1α inhibitor, for AML treatment, specifically
> targeting the MOLM-13 cell line with FLT3-ITD, with a focus on overcoming
> resistance mechanisms and enhancing combination therapy efficacy.

KIRA6 was subsequently confirmed to inhibit KG-1 (AML cell line) viability at
clinically relevant concentrations.

## 3. Antimicrobial resistance / cf-PICIs (re-discovery, validated)

Researchers (Fleming Initiative / Imperial College London) instructed the
system on a topic their group had discovered but not yet published:

> Hypothesize how capsid-forming phage-inducible chromosomal islands
> (cf-PICIs) exist across bacterial species.

Co-Scientist independently proposed that cf-PICIs interact with diverse phage
tails to expand their host range — matching the unpublished experimental
finding.

## Notes on goal-writing style

- State the objective as a *hypothesis to be generated*, not a question to answer.
- Name the specific entity/mechanism class of interest (nucleoporin
  phosphorylation; IRE1α inhibition; cf-PICI host range).
- Request mechanism detail and a feasible experiment explicitly.
- Constraints and preferences (novelty, feasibility, correctness) can be
  attached and are parsed into the plan configuration.
