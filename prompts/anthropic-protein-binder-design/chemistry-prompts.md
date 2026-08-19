# Analytical Chemistry — NMR and LC-MS Prompts (verbatim)

From "How Claude is accelerating protein design and analytical chemistry"
(Anthropic, Aug 18, 2026). Supplied with only a contract lab's raw instrument
files and these prompts, Claude Opus 5 (in Claude Science) returned finished
NMR and LC-MS results in 23 and 19 minutes, matching the lab's own analysis
(hydrogen counts within 0.08 ¹H; purity 96.4% vs. 96.33%).

## NMR prompt (in full)

> i have a raw 1H FID: process it: FT, phase, baseline-correct. show me the
> spectrum. then pick peaks and integrate: give me a table with δ (ppm),
> multiplicity, J (Hz), and integral.

## LC-MS prompt (in full)

> Process the raw LCMS file: extract chromatograms and mass spectra, and
> summarize with figures.

Source: footnote 10 of
https://www.anthropic.com/research/Claude-accelerates-protein-design
