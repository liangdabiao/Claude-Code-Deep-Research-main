---
description: 将原始研究问题细化为结构化的深度研究提示词
argument-hint: [原始研究问题]
---

# Question Refinement

Refine the user's research question into a structured research prompt.

## Raw Question

$ARGUMENTS

## Your Task

Use the **question-refiner** skill to:

1. **Ask Clarifying Questions**: Ask 5-6 relevant questions about:
   - Specific focus areas within the topic
   - Output format requirements (report, presentation, etc.)
   - Geographic and time scope
   - Target audience
   - Special requirements

2. **Wait for User Response**: Do NOT generate the structured prompt until the user answers.

3. **Generate Structured Prompt**: Create a structured research prompt with:
   - **TASK**: Clear, concise statement of what needs to be researched
   - **CONTEXT/BACKGROUND**: Why this research matters
   - **SPECIFIC QUESTIONS**: 3-7 concrete sub-questions
   - **KEYWORDS**: Search terms and synonyms
   - **CONSTRAINTS**: Timeframe, geography, source types, length
   - **OUTPUT FORMAT**: Detailed structure with lengths and components
   - **FINAL INSTRUCTIONS**: Citation requirements

## Important Notes

- Be patient: Better to ask one more question than deliver a vague prompt
- Be specific: Every field should be filled with concrete, actionable details
- Focus on the user's needs, not what you think they should want

Begin the question refinement process.
