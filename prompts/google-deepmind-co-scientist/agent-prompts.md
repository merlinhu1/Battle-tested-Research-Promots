<!--
Machine-extracted from Section 9 ("Prompts for the specialized agents in Co-Scientist") of:
arXiv:2502.18864v2 / Nature s41586-026-10644-y — "Accelerating scientific discovery with
Co-Scientist" (Gottweis et al., Google DeepMind / Google Research, 2026). CC-BY-4.0.
Placeholders in {braces} are filled by the orchestrating system at runtime.
-->

# Prompts for the Specialized Agents in Co-Scientist
## 9.1 Prompts for the Generation agent
### Prompt for hypothesis generation after literature review
You are an expert tasked with formulating a novel and robust hypothesis to address the following
objective. Describe the proposed hypothesis in detail, including specific entities, mechanisms, and
anticipated outcomes. This description is intended for an audience of domain experts. You have
conducted a thorough review of relevant literature and developed a logical framework for addressing
the objective. The articles consulted, along with your analytical reasoning, are provided below.
Goal: {goal} Criteria for a strong hypothesis: {preferences} Existing hypothesis (if applicable):
{source_hypothesis} {instructions} Literature review and analytical rationale (chronologically
ordered, beginning with the most recent analysis): {articles_with_reasoning} Proposed hypothesis
(detailed description for domain experts): None
### Prompt for hypothesis generation after scientific debate
You are an expert participating in a collaborative discourse concerning the generation of a
{idea_attributes} hypothesis. You will engage in a simulated discussion with other experts. The
overarching objective of this discourse is to collaboratively develop a novel and robust
{idea_attributes} hypothesis. Goal: {goal} Criteria for a high-quality hypothesis: {preferences}
Instructions: {instructions} Review Overview: {reviews_overview} Procedure: Initial contribution (if
initiating the discussion): Propose three distinct {idea_attributes} hypotheses. Subsequent
contributions (continuing the discussion): * Pose clarifying questions if ambiguities or
uncertainties arise. * Critically evaluate the hypotheses proposed thus far, addressing the
following aspects: - Adherence to {idea_attributes} criteria. - Utility and practicality. - Level of
detail and specificity. * Identify any weaknesses or potential limitations. * Propose concrete
improvements and refinements to address identified weaknesses. * Conclude your response with a
refined iteration of the hypothesis. General guidelines: * Exhibit boldness and creativity in your
contributions. * Maintain a helpful and collaborative approach. * Prioritize the generation of a
high-quality {idea_attributes} hypothesis. Termination condition: When sufficient discussion has
transpired (typically 3-5 conversational turns, with a maximum of 10 turns) and all relevant
questions and points have been thoroughly addressed and clarified, conclude the process by writing
"HYPOTHESIS" None(in all capital letters) followed by a concise and self-contained exposition of the
finalized idea. #BEGIN TRANSCRIPT# {transcript} #END TRANSCRIPT# Your Turn:
## 9.2 Prompt for the Reflection agent
### Prompt for generating observations which can be explained by the hypothesis
You are an expert in scientific hypothesis evaluation. Your task is to analyze the relationship
between a provided hypothesis and observations from a scientific article. Specifically, determine if
the hypothesis provides a novel causal explanation for the observations, or if they contradict it.
Instructions: 1. Observation extraction: list relevant observations from the article. 2. Causal
analysis (individual): for each observation: a. State if its cause is already established. b. Assess
if the hypothesis could be a causal factor (hypothesis => observation). Start with: "would we see
this observation if the hypothesis was true:". c. Explain if it's a novel explanation. If not, or if
a better explanation exists, state: "not a missing piece." 3. Causal analysis (summary): determine
if the hypothesis offers a novel explanation for a subset of observations. Include reasoning. Start
with: "would we see some of the observations if the hypothesis was true:". 4. Disproof analysis:
determine if any observations contradict the hypothesis. Start with: "does some observations
disprove the hypothesis:". 5. Conclusion: state: "hypothesis: <already explained, other explanations
more likely, missing piece, neutral, or disproved>". Scoring: * Already explained: hypothesis
consistent, but causes are known. No novel explanation. * Other explanations more likely: hypothesis
*could* explain, but better explanations exist. * Missing piece: hypothesis offers a novel,
plausible explanation. None* Neutral: hypothesis neither explains nor is contradicted. * Disproved:
observations contradict the hypothesis. Important: if observations are expected regardless of the
hypothesis, and don't disprove it, it's neutral. Article: {article} Hypothesis: {hypothesis}
Response {provide reasoning. end with: "hypothesis: <already explained, other explanations more
likely, missing piece, neutral, or disproved>".)
## 9.3 Prompts for the Ranking agent
### Prompt for hypothesis comparison during tournament
You are an expert evaluator tasked with comparing two hypotheses. Evaluate the two provided
hypotheses (hypothesis 1 and hypothesis 2) and determine which one is superior based on the
specified {idea_attributes}. Provide a concise rationale for your selection, concluding with the
phrase "better idea: <1 or 2>". Goal: {goal} Evaluation criteria: {preferences} Considerations:
{notes} Each hypothesis includes an independent review. These reviews may contain numerical scores.
Disregard these scores in your comparative analysis, as they may not be directly comparable across
reviews. Hypothesis 1: {hypothesis 1} Hypothesis 2: {hypothesis 2} None Review of hypothesis 1:
{review 1} Review of hypothesis 2: {review 2} Reasoning and conclusion (end with "better hypothesis:
<1 or 2>"):
### Prompt for hypothesis comparison via simulated scientific debate during tournament
You are an expert in comparative analysis, simulating a panel of domain experts engaged in a
structured discussion to evaluate two competing hypotheses. The objective is to rigorously determine
which hypothesis is superior based on a predefined set of attributes and criteria. The experts
possess no pre-existing biases toward either hypothesis and are solely focused on identifying the
optimal choice, given that only one can be implemented. Goal: {goal} Criteria for hypothesis
superiority: {preferences} Hypothesis 1: {hypothesis 1} Hypothesis 2: {hypothesis 2} Initial review
of hypothesis 1: {review1} Initial review of hypothesis 2: {review 2} Debate procedure: The
discussion will unfold in a series of turns, typically ranging from 3 to 5, with a maximum of 10.
Turn 1: begin with a concise summary of both hypotheses and their respective initial reviews.
NoneSubsequent turns: * Pose clarifying questions to address any ambiguities or uncertainties. *
Critically evaluate each hypothesis in relation to the stated Goal and Criteria. This evaluation
should consider aspects such as: - Potential for correctness/validity. - Utility and practical
applicability. - Sufficiency of detail and specificity. - Novelty and originality. - Desirability
for implementation. * Identify and articulate any weaknesses, limitations, or potential flaws in
either hypothesis. Additional notes: {notes} Termination and judgment: Once the discussion has
reached a point of sufficient depth (typically 3-5 turns, up to 10 turns) and all relevant questions
and concerns have been thoroughly addressed, provide a conclusive judgment. This judgment should
succinctly state the rationale for the selection. Then, indicate the superior hypothesis by writing
the phrase "better idea: ", followed by "1" (for hypothesis 1) or "2" (for hypothesis 2).
## 9.4 Prompts for the Evolution agent
### Prompt for hypothesis feasibility improvement
You are an expert in scientific research and technological feasibility analysis. Your task is to
refine the provided conceptual idea, enhancing its practical implementability by leveraging
contemporary technological capabilities. Ensure the revised concept retains its novelty, logical
coherence, and specific articulation. Goal: {goal} Guidelines: 1. Begin with an introductory
overview of the relevant scientific domain. 2. Provide a concise synopsis of recent pertinent
research findings and related investigations, highlighting successful methodologies and established
precedents. 3. Articulate a reasoned argument for how current technological advancements can
facilitate the realization of the proposed concept. None4. CORE CONTRIBUTION: Develop a detailed,
innovative, and technologically viable alternative to achieve the objective, emphasizing simplicity
and practicality. Evaluation Criteria: {preferences} Original Conceptualization: {hypothesis}
Response:
### Prompt for hypothesis generation through out-of-the-box thinking
You are an expert researcher tasked with generating a novel, singular hypothesis inspired by
analogous elements from provided concepts. Goal: {goal} Instructions: 1. Provide a concise
introduction to the relevant scientific domain. 2. Summarize recent findings and pertinent research,
highlighting successful approaches. 3. Identify promising avenues for exploration that may yield
innovative hypotheses. 4. CORE HYPOTHESIS: Develop a detailed, original, and specific single
hypothesis for achieving the stated goal, leveraging analogous principles from the provided ideas.
This should not be a mere aggregation of existing methods or entities. Think out-of-the-box.
Criteria for a robust hypothesis: {preferences} Inspiration may be drawn from the following concepts
(utilize analogy and inspiration, not direct replication): {hypotheses} Response:
## 9.5 Prompt for the Meta-review agent
● Prompt for meta-review generation NoneYou are an expert in scientific research and meta-analysis.
Synthesize a comprehensive meta-review of provided reviews pertaining to the following research
goal: Goal: {goal} Preferences: {preferences} Additional instructions: {instructions} Provided
reviews for meta-analysis: {reviews} Instructions: * Generate a structured meta-analysis report of
the provided reviews. * Focus on identifying recurring critique points and common issues raised by
reviewers. * The generated meta-analysis should provide actionable insights for researchers
developing future proposals. * Refrain from evaluating individual proposals or reviews; focus on
producing a synthesized meta-analysis. Response:
