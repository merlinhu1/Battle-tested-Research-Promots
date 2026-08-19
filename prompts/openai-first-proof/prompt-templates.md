<!--
Machine-extracted from Appendix A of:
https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf
"First Proof?" (OpenAI, February 20, 2026).
Line-wrapping reflowed; wording unchanged. Some bullets render as "≱" (the PDF's
bullet glyph); consult the PDF for exact typography.
-->

A Appendix: Prompting strategy

For the solutions presented in the main body, we orchestrated the model work manually. Here

we describe a simple, programmatic, and problem-independent setup that we tried after the

original deadline and we expect it produces results of roughly equivalent quality.

A.1 Solution strategy

The framework is simple:

• Generate a small number of seed ideas.

• Prompt the model to solve the given problem using each of the seed ideas.

• Repeat up to 3 times:

≧̸ Verify (i) correctness of the proof and (ii) validity of any cited material and biblio-

graphic references.

≧̸ If gaps are found, prompt the model to revise the drafted solution.

• If the veri≁cations pass, typeset the resulting solution.

In Section B , we share the solutions to Problem #6 for one such run. Here we generated four

solutions for every seed idea (see Section A.4.1 ). For the idea of using BSS, our internal model

produced 3/4 solutions that were then judged (by the same model) to be correct. For two of

the veri≁ed runs, there were zero rounds of revisions; for the third run, there was one round of

revisions.

A.2 Prompt templates

A.2.1 Generate ideas template

You are a problem idea generator! Your goal is to generate FIVE powerful

high-level approaches to solving the given problem. You can use your own

knowledge or a literature search. Your ideas will be passed along to a team

of technical problem solvers who will work on each idea in parallel.

# Problem

{{problem}}

# Instructions

You should output a JSON dictionary inside a markdown block in the

following format:

```json

{

"idea_1": "brief description of the first promising idea",

"idea_2": "brief description of the second promising idea",

"idea_3": "brief description of the third promising idea",

"idea_4": "brief description of the fourth promising idea",

"idea_5": "brief description of the fifth promising idea",

}

```

69

A.3 Solve template

{{problem}}

{% if idea %}

You should pursue the following approach:

{{idea}}

Keep working hard until you have a complete and rigorous solution.

{% endif %}

A.3.1 Verify template
