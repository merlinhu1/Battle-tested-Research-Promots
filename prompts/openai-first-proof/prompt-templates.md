<!--
Machine-extracted from Appendix A of:
https://cdn.openai.com/pdf/26177a73-3b75-4828-8c91-e8f1cf27aaa0/oai_first_proof.pdf
"First Proof?" (OpenAI, February 20, 2026).
Line-wrapping reflowed; wording unchanged. Bullets may render as "≱" and
ligatures as "≁/⪊" (PDF glyph artifacts); consult the PDF for exact typography.

IMPORTANT: per the report, the main-body solutions were orchestrated MANUALLY.
These templates are the simple programmatic setup tried AFTER the original
deadline, which OpenAI expects to produce results of roughly equivalent quality.
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

I need you to check the following solution very carefully and let me know

if you find any gaps that cannot easily be fixed.

{% if check_refs %}You should also carefully check that all the

bibliographic references are valid.{% endif %}

# Problem

{{problem}}

# Solution?

{{solution}}

# Instructions

Something is considered a "gap" if it is a critical error that cannot

easily be fixed. If the proposed solution has no gaps, you should set

the "correct" key to true below and you provide an empty list "[]"

for the "gaps" key. If there are gaps, you should set the "correct"

key to false below and you should provide a list of gaps as specified.

Your output should be in the format:

<CORRECT>one of 'true' or 'false'</CORRECT>

<GAPS>

[required section if correct is false]

- Brief explanation of gap_1

- Brief explanation of gap_2

- ...

</GAPS>

A.3.2 Solution re≁nement template

You previously submitted a solution to the given problem, which you

will find below. Unfortunately, the referee found some issues with your

solution that you will need to address carefully and rigorously.

Keep working until you have revised the argument, or if you find it to

be impossible to fix, you should work on a new approach.

# Problem

70

{{problem}}

# Solution

{{solution}}

# Critique

{{gaps}}

A.3.3 Typesetting template

# Problem

{{problem}}

# Solution

{{solution}}

Please give me a full, rigorous, and complete latex draft of the provided argument.

The draft should be written in a professional mathematical style.

Clearly demarcate the problem and the solution.

Use a single \section{...} (but as many subsection as you wish).

If you need citations to known literature, you may include a bibliography

(use the "\bibitem" format for bibliography entries).
