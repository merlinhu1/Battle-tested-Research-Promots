# Problem #6 — Prompt Provenance and Supporting Material

`problem-6-prompt.md` is the complete as-run solve prompt: copy its entire
content and send it to the model as one message. It contains nothing except
the prompt — no commentary — so it runs as-is.

## How it was assembled

The released solve template (report Appendix A.3) is:

```
{{problem}}

{% if idea %}
You should pursue the following approach:

{{idea}}

Keep working hard until you have a complete and rigorous solution.
{% endif %}
```

Filled with:

- `{{problem}}` — the verbatim Problem #6 statement from the report (title,
  "Problem", statement paragraph), as posted on 1stproof.org.
- `{{idea}}` — the "Normalize by the Laplacian" seed idea, verbatim from
  Appendix A.4.1 (the idea that produced the verified solutions). PDF math
  glyphs (ε, ≼, superscripts, subscripts) were restored by hand; wording is
  unchanged.

That is everything the original run received: no system prompt or other
context was disclosed, and none is needed — the problem statement is fully
self-contained.

## The yield this prompt produced

Per Appendix A.1/A.4: four independent solver runs on this seed idea; 3/4
solutions judged correct by the verify template; two runs needed zero
revision rounds, one needed a single revision round.

## All five generated ideas for Problem #6 (A.4.1, as released)

1. **Normalize by the Laplacian** (BSS barrier potential — the winning idea,
   used in the prompt file above).
2. **SDP + rounding** — relaxation maximizing Σᵥ xᵥ with xᵥ ∈ [0,1] and a
   lifted constraint ensuring Σ_{uv∈E} X_{uv} A_{uv} ≼ εI where X = xxᵀ,
   diag(X) = x; then pipage/swap rounding with matrix-Chernoff-style bounds.
3. **Interlacing polynomials / MSS approach** — view M as a random sum of
   rank-1 matrices gated by random vertex coloring; compute/bound the
   expected characteristic polynomial; use real-rootedness + interlacing.
4. **Matrix discrepancy / paving / online load balancing** — interpret
   vertex coloring into r bins as distributing edge matrices; control the
   maximum load.
5. *(remaining idea and exact wording: report A.4.1)*

Swap any idea into the `{{idea}}` slot of the solve template to run the
other arms.

## The other nine problems (statements in the report)

1. Smooth shifts of the ¾ measure on T³
2. A nonvanishing test vector for the twisted local Rankin–Selberg integral
3. A Markov chain from interpolation polynomials?
4. Finite additive convolution and a harmonic-mean inequality
5. The O-adapted slice filtration and a geometric fixed-point criterion
6. **Large ε-light vertex subsets** ← the proven run above
7. Uniform lattices with…
8. Quadrivalent polyhedral Lagrangian surfaces are Lagrangian-smoothable
9. Algebraic relations among scaled quadri-linear determinant tensors
10. Kernelized CP–ALS subproblem with missing data: matrix-free PCG with
    Kronecker preconditioning

Fill the solve template with any statement to run the same pipeline on it.

## Running the full pipeline

For the verify/revise steps after solving, use the templates in
[`prompt-templates.md`](prompt-templates.md) (verify → refine, up to 3
rounds). Four independent runs per idea matches the released procedure.

<!-- Machine-extracted from:
https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf
"First Proof?" (OpenAI, February 20, 2026). -->
