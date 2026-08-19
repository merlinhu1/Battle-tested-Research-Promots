# Problem #6 — The Real Prompt, Reconstructed From Released Components

OpenAI did not publish a single filled-in prompt. What they released in the
"First Proof?" report is the complete set of components from which every
as-run prompt is assembled, verbatim:

1. The prompt templates (Appendix A — see [`prompt-templates.md`](prompt-templates.md));
2. The exact problem statements for all ten tasks (the report reproduces each
   1stproof.org problem in full);
3. For Problem #6, the five seed ideas actually produced by the
   idea-generator prompt (Appendix A.4.1).

Filling the solve template with (1)+(2)+(3) yields the real prompt sent to the
solver. The successful runs used the "Normalize by the Laplacian" (BSS-style)
seed idea below — 3 of 4 solutions on that idea were judged correct by the
model's own verification loop.

---

## The solve prompt, filled in (Problem #6, BSS seed idea)

> 6 Large ε-light vertex subsets
>
> **Problem.** For a graph G = (V, E), let G[S] = (V, E(S, S)) denote the
> graph with the same vertex set, but only the edges between vertices in S.
> Let L be the Laplacian matrix of G and let L[S] be the Laplacian of G[S].
> I say that a set of vertices S is ε-light if the matrix εL − L[S] is
> positive semidefinite. Does there exist a constant c > 0 so that for every
> graph G and every ε between 0 and 1, V contains an ε-light subset S of size
> at least cε|V|?
>
> You should pursue the following approach:
>
> Normalize by the Laplacian: write L = Σₑ Lₑ, set Aₑ := L^(−1/2) Lₑ
> L^(−1/2) so Σₑ Aₑ = I on range(L). Then build an r-coloring with
> r = O(1/ε) via a deterministic Batson–Spielman–Srivastava-style one-sided
> barrier potential Λᵤ(M) = tr((uI − M)⁻¹), maintaining that the
> monochromatic-edge sum M = Σ₍ᵤ,ᵥ₎ same color Aᵤᵥ stays ≤ εI. Finally take
> the largest color class S, which inherits L[S] ≤ εL and has |S| = Ω(εn).
>
> Keep working hard until you have a complete and rigorous solution.

(The problem statement above is the report's verbatim text; the seed idea is
lightly de-garbled from the PDF extraction — the model's solution proves the
claim with c = 1/256.)

## All five generated ideas for Problem #6 (A.4.1, as released)

1. **Normalize by the Laplacian** (BSS barrier potential; the winning idea,
   reproduced in full above).
2. **SDP + rounding** — relaxation maximizing Σᵥ xᵥ with xᵥ ∈ [0,1] and a
   lifted constraint ensuring Σ_{uv∈E} X_{uv} A_{uv} ≼ εI where X = xxᵀ,
   diag(X) = x; then pipage/swap rounding with matrix Chernoff bounds.
3. **Interlacing polynomials / MSS approach** — view M as a random sum of
   rank-1 matrices gated by random vertex coloring; bound the expected
   characteristic polynomial and use real-rootedness + interlacing.
4. **Matrix discrepancy / paving / online load balancing** — distribute edge
   matrices across r bins and control the maximum load.
5. *(see report A.4.1 for the remaining idea and exact wording)*

## The other nine problems (statements in the report)

1. Smooth shifts of the ¾ measure on T³
2. A nonvanishing test vector for the twisted local Rankin–Selberg integral
3. A Markov chain from interpolation polynomials?
4. Finite additive convolution and a harmonic-mean inequality
5. The O-adapted slice filtration and a geometric fixed-point criterion
6. **Large ε-light vertex subsets** ← the BSS run above
7. Uniform lattices with…
8. Quadrivalent polyhedral Lagrangian surfaces are Lagrangian-smoothable
9. Algebraic relations among scaled quadri-linear determinant tensors
10. Kernelized CP–ALS subproblem with missing data: matrix-free PCG with
    Kronecker preconditioning

Each combines with the same templates to form the as-run prompts.

<!-- Machine-extracted from:
https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf
"First Proof?" (OpenAI, February 20, 2026). Math glyphs partially garbled in
extraction (ε, ≼, superscripts restored by hand here); consult the PDF for
exact typography.
-->
