---
description: 为研究主题创建详细的执行计划，包括子主题分解、智能体部署策略
argument-hint: [已结构化的研究提示词]
---

# Research Planning

Create a detailed research execution plan for the given structured research prompt.

## Structured Prompt

$ARGUMENTS

## Your Task

Use the **research-executor** skill (Phase 2: Retrieval Planning only) to:

1. **Decompose the Main Question**: Break down into 3-7 subtopics based on SPECIFIC_QUESTIONS

2. **Generate Search Queries**: Create specific search queries for each subtopic

3. **Identify Data Sources**: Select appropriate sources based on CONSTRAINTS

4. **Create Research Plan**:
   - List subtopics with research questions
   - Specify search queries for each subtopic
   - Identify target sources (academic, industry, news, etc.)
   - Define multi-agent deployment strategy
   - Estimate timeline

5. **Present Plan for Approval**: Show the plan and ask if user wants to proceed

## Output Format

```markdown
## Research Plan

### Subtopics to Research:
1. **[Subtopic 1 Name]**
   - Research questions: [specific questions]
   - Search queries: [query 1, query 2, query 3]
   - Target sources: [source types]

2. **[Subtopic 2 Name]**
   - Research questions: [specific questions]
   - Search queries: [query 1, query 2, query 3]
   - Target sources: [source types]

...

### Multi-Agent Deployment Strategy:
- **Total Agents**: [number]
- **Agent Types**: [web research, academic, verification]
- **Expected Timeline**: [estimate]

### Output Structure:
[Describe the folder and file structure]

Ready to proceed? (Yes/No/Modifications needed)
```

Create the research plan now.
