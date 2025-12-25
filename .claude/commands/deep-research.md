---
description: 对指定主题执行完整的深度研究流程，从问题细化到最终报告生成
argument-hint: [研究主题或问题]
allowed-tools: Task, WebSearch, WebFetch, mcp__web_reader__webReader, Read, Write, TodoWrite
---

# Deep Research

Execute comprehensive deep research on the given topic using the 7-phase research methodology and Graph of Thoughts framework.

## Topic

$ARGUMENTS

## Research Workflow

This command will execute the following steps:

### Step 1: Question Refinement
Use the **question-refiner** skill to ask clarifying questions and generate a structured research prompt.

### Step 2: Research Planning
Break down the research topic into 3-7 subtopics and create a detailed execution plan.

### Step 3: Multi-Agent Research
Deploy multiple parallel research agents to gather information from different sources:
- Web Research Agents (3-5 agents): Current information, trends, news
- Academic/Technical Agent (1-2 agents): Research papers, technical specifications
- Cross-Reference Agent (1 agent): Fact-checking and verification

### Step 4: Source Triangulation
Compare findings across multiple sources and validate claims using the A-E quality rating system.

### Step 5: Knowledge Synthesis
Use the **synthesizer** skill to combine findings into a coherent report with inline citations.

### Step 6: Citation Validation
Use the **citation-validator** skill to verify all claims have accurate, complete citations.

### Step 7: Output Generation
Generate structured research outputs in the `RESEARCH/[topic]/` directory:
- README.md
- executive_summary.md
- full_report.md
- data/
- visuals/
- sources/
- research_notes/
- appendices/

## Citation Requirements

Ensure every factual claim includes:
1. Author/Organization name
2. Publication date
3. Source title
4. Direct URL/DOI
5. Page numbers (if applicable)

Begin the deep research process now.
