# Gluon → Graviton: Generalize Single-Minus Amplitudes to Gravity

| | |
|---|---|
| **Lab** | OpenAI |
| **Model** | ChatGPT 5.2 Pro (custom GPT "GR singmin", 2/28/26 session) |
| **Field** | Theoretical physics — quantum gravity scattering amplitudes |
| **Result (yield)** | The model generalized the gluon single-minus amplitudes paper to gravity, deriving and verifying nonzero graviton tree amplitudes — the content of the preprint "Single-minus graviton tree amplitudes are nonzero" (Guevara, Lupsasca, Skinner, Strominger, Weil, on behalf of OpenAI, Mar 4, 2026), with the author list crediting the ChatGPT session. |
| **Date** | February 28 – March 4, 2026 |
| **Transcript (110-page PDF)** | https://cdn.openai.com/pdf/gluon-to-graviton-paper.pdf |
| **Published preprint** | https://cdn.openai.com/pdf/graviton.pdf / https://openai.com/index/extending-single-minus-amplitudes-to-gravitons/ |

## Why it's battle-tested

The released transcript documents the complete causal chain: the user sends the
gluon paper with one instruction line, the model re-derives the key appendices
("Thought for 30m 32s"), the user then sends the gravity-generalization
instruction, and through a series of short follow-ups the model derives the
unordered Berends–Giele recursion, the permutation-invariance and soft-theorem
checks, and writes the full graviton paper in LaTeX — whose abstract matches
the published preprint. The paper's author block itself credits the ChatGPT
session ("ChatGPT 5.2 Pro … on behalf of OpenAI").

## The prompts

- [`prompt-1-launch.md`](prompt-1-launch.md) — the launch instruction (run with
  the gluon paper attached — the full source is embedded in the transcript PDF).
- [`prompt-2-gravity-task.md`](prompt-2-gravity-task.md) — the gravity
  generalization task, the substantive research instruction: swap the ordered
  BG recursion for the unordered gravity version (extra [A,B] power), replace
  color checks with full permutation invariance, swap Weinberg soft theorems,
  and the sign-off "Good luck! You are a brilliant theoretical physicist."
- [`prompt-3-followups.md`](prompt-3-followups.md) — the short steering
  messages sent as the derivation progressed.

Extraction note: machine-extracted from the transcript PDF (each page is a
ChatGPT-conversation render); word spacing in the plain-language parts has
been restored by hand, LaTeX equations are verbatim, and "proerties" is a
typo present in the original. The transcript PDF is authoritative.

## Hidden user prompts (unpublished)

Minimal — this was a plain ChatGPT session, not a harness: the visible
conversation is the complete instruction set. The custom GPT ("GR singmin")
configuration and instructions, if any beyond defaults, are not published.
