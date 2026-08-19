# Contributing

## Firm requirements for every entry

Never consider a prompt without a proven yield. An entry **must** satisfy all
three:

1. **The prompt is available.** Published verbatim by a credible source
   (lab PDF, official dataset, research page). Collect it as `.md` in the
   entry folder. If the source is a PDF, machine-extract the text and note the
   provenance in an HTML comment at the top of the file; always link the
   authoritative source.
2. **It is related to a research task.** Mathematics, natural sciences,
   engineering, or biomedical discovery — not demos, toys, or benchmarks
   without research significance.
3. **It is battle-tested and produced significant field yield.** The result
   must be independently verifiable: a peer-reviewed publication, wet-lab
   validation, formal verification (e.g. Lean), or expert-reviewed proof.
   State the yield concretely in the entry README (numbers beat adjectives).

## Entry layout

```
prompts/<lab>/<entry-name>/
  README.md          # metadata table + analysis of what made the prompt work
  prompt.md          # the verbatim prompt(s), with provenance comment
  transcript.md      # optional: full released transcript(s)
```

The entry `README.md` must include a metadata table with: lab, model, field,
result (yield), date, and source links — mirroring the existing entries.

## Index

Update the root `README.md` gallery table when adding an entry (lab section,
entry link, field, yield, date).

## Extraction notes

When converting source PDFs to `.md`:

- Preserve wording exactly; only reflow line wrapping.
- Document the source URL and any extraction caveats in a leading HTML comment.
- Prefer official text releases (e.g. HuggingFace prompt dumps) over PDF
  extraction when both exist.
- Inline mathematics extracted from typeset PDFs is often imperfect — say so
  and defer to the authoritative source.
