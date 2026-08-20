You are evaluating two critiques of a mathematical solution. Compare them and provide a detailed analysis.

PROBLEM:
{{ problem }}

SOLUTION BEING CRITIQUED:
{{ solution }}

GROUND TRUTH: This solution is {{ ground_truth }}.

REFERENCE CRITIQUE (from Claude 3.5 Haiku):
{{ reference_critique }}

COMPARISON CRITIQUE:
{{ comparison_critique }}

Please analyze both critiques and provide a JSON response with the following structure:
{
  "reference_critique": {
    "mathematical_correctness": {
      "score": <0-10>,
      "valid_errors": ["list of errors correctly identified (real issues)"],
      "invalid_errors": ["list of errors incorrectly claimed (false accusations)"],
      "notes": "brief assessment of mathematical reasoning"
    },
    "fluency": {
      "score": <0-10>,
      "has_code_mixing": <true/false>,
      "has_repetition": <true/false>,
      "notes": "brief fluency assessment"
    },
    "overall_quality": <0-10>
  },
  "comparison_critique": {
    "mathematical_correctness": {
      "score": <0-10>,
      "valid_errors": ["list of errors correctly identified (real issues)"],
      "invalid_errors": ["list of errors incorrectly claimed (false accusations)"],
      "notes": "brief assessment of mathematical reasoning"
    },
    "fluency": {
      "score": <0-10>,
      "has_code_mixing": <true/false>,
      "has_repetition": <true/false>,
      "notes": "brief fluency assessment"
    },
    "overall_quality": <0-10>
  },
  "comparison": {
    "winner": "reference" or "comparison" or "tie",
    "reasoning": "explanation based on mathematical correctness and fluency"
  }
}

EVALUATION CRITERIA:

## 1. MATHEMATICAL CORRECTNESS

Assess whether the critique correctly identifies errors in the solution:

**score (0-10)**: Overall mathematical correctness score
- 9-10: Identifies all real errors, no false claims, excellent reasoning
- 7-8: Identifies most errors, few/no false claims, good reasoning
- 5-6: Identifies some errors, may have some false claims
- 3-4: Misses important errors or has significant false claims
- 0-2: Mostly wrong, misses critical errors, many false claims

**valid_errors**: List actual errors that the critique correctly identifies
- Each entry should briefly describe the real issue found
- Only include errors that are genuinely present in the solution

**invalid_errors**: List false claims made by the critique
- Errors that don't actually exist in the solution
- Misunderstandings or incorrect mathematical reasoning by the critique

**notes**: Brief assessment of the critique's mathematical reasoning

## 2. FLUENCY

Assess the readability and language quality of the critique:

**score (0-10)**: Overall fluency considering all factors below
- 9-10: Exceptionally fluent, polished human-like writing
- 7-8: Very fluent with minor imperfections
- 5-6: Understandable but some awkward phrasing
- 3-4: Choppy, confusing, or hard to read
- 0-2: Severely broken, nearly incomprehensible

**has_code_mixing (true/false)**: Does the critique mix languages or code inappropriately?
- true if: mixing English/Chinese, programming syntax in prose, code-like constructs
- false if: consistent language, proper mathematical notation ($x$, LaTeX is OK)

**has_repetition (true/false)**: Does the critique have excessive repetition?
- true if: same text/formula repeated 3+ times, copy-paste patterns, degenerative loops
- false if: natural flow, each idea expressed once or twice

**notes**: Brief explanation of fluency issues (if any)

## 3. OVERALL QUALITY (0-10)

Combined assessment considering BOTH mathematical correctness AND fluency:

- 9-10: Excellent math + excellent fluency
- 7-8: Good math + good fluency (minor issues in either)
- 5-6: Adequate - some math errors OR some fluency issues
- 3-4: Poor - significant math errors OR significant fluency issues
- 0-2: Very poor - major problems in math AND/OR fluency

**Important**: A mathematically correct critique with poor fluency (code mixing, repetition) should score lower. A fluent critique with wrong math should also score lower. Both matter.

## 4. WINNER SELECTION

Choose winner based on overall quality, considering:

1. **Mathematical correctness** (primary for tie-breaking between readable critiques):
   - More valid_errors identified = better
   - Fewer invalid_errors = better
   - Better reasoning_quality = better

2. **Fluency** (can override math if severe issues):
   - If one has code_mixing or repetition and other doesn't → clean one wins (unless severe math errors)
   - If both have fluency issues → prefer fewer issues

3. **Decision examples**:
   - Both clean fluency, similar math → compare valid_errors count → more = wins
   - One has code_mixing, other is clean → clean wins (even if slightly worse math)
   - Both have poor fluency → prefer the one with better math

Respond with ONLY valid JSON, no additional text.
