# Claude Code Deep Research Agent - Implementation Guide

## Overview

This guide explains how to use the Claude Code Deep Research Agent framework to conduct comprehensive, multi-agent research with proper citations and high-quality outputs.

## Quick Start

### 1. Basic Usage - Single Command

The simplest way to conduct deep research:

```
/deep-research [your research topic]
```

**Example**:
```
/deep-research AI applications in clinical diagnosis
```

This command will:
1. Refine your research question (ask clarifying questions)
2. Create a research plan
3. Deploy multiple research agents in parallel
4. Synthesize findings into a comprehensive report
5. Validate all citations
6. Output results to `RESEARCH/[topic]/` directory

### 2. Step-by-Step Usage

For more control, use commands sequentially:

#### Step 1: Refine Your Question
```
/refine-question [your raw question]
```

The Question Refiner will:
- Ask 5-6 clarifying questions
- Understand your specific needs
- Generate a structured research prompt

#### Step 2: Plan Research (Optional)
```
/plan-research [structured prompt from Step 1]
```

This creates a detailed research execution plan showing:
- How the topic will be broken into subtopics
- Which agents will be deployed
- Expected timeline

#### Step 3: Execute Research
```
/deep-research [your topic]
```

Or use the research-executor skill directly with the structured prompt.

#### Step 4: Synthesize Findings (If needed)
```
/synthesize-findings RESEARCH/[topic]/research_notes/
```

#### Step 5: Validate Citations
```
/validate-citations RESEARCH/[topic]/full_report.md
```

## Project Structure

```
claude-code-deep-research/
├── .claude/
│   ├── skills/                    # Skills definitions
│   │   ├── question-refiner/      # Question refinement skill
│   │   │   ├── skill.json
│   │   │   ├── instructions.md
│   │   │   └── examples.md
│   │   ├── research-executor/     # Main research execution skill
│   │   │   ├── skill.json
│   │   │   ├── instructions.md
│   │   │   └── examples.md
│   │   ├── got-controller/        # Graph of Thoughts controller
│   │   │   ├── skill.json
│   │   │   ├── instructions.md
│   │   │   └── examples.md
│   │   ├── citation-validator/    # Citation validation skill
│   │   │   ├── skill.json
│   │   │   ├── instructions.md
│   │   │   └── examples.md
│   │   └── synthesizer/           # Research synthesis skill
│   │       ├── skill.json
│   │       ├── instructions.md
│   │       └── examples.md
│   └── commands/                  # User-facing commands
│       ├── deep-research/         # Main deep research command
│       ├── refine-question/       # Question refinement command
│       ├── plan-research/         # Research planning command
│       ├── validate-citations/    # Citation validation command
│       └── synthesize-findings/   # Synthesis command
├── CLAUDE.md                      # Main documentation
├── CLAUDE2.md                     # GoT framework documentation
├── PROJECT_UNDERSTANDING.md       # Project understanding
├── IMPLEMENTATION_GUIDE.md        # This file
├── deepresearchprocess.md         # 7-phase research process
└── RESEARCH/                      # Research outputs (created during use)
    └── [topic_name]/
        ├── README.md
        ├── executive_summary.md
        ├── full_report.md
        ├── data/
        ├── visuals/
        ├── sources/
        ├── research_notes/
        └── appendices/
```

## Skills Reference

### Question Refiner

**Purpose**: Transform raw research questions into structured research prompts

**When to Use**:
- You have a vague topic or question
- You need help defining research scope
- You want to clarify output requirements

**What it Does**:
1. Asks clarifying questions about:
   - Specific focus areas
   - Output format requirements
   - Geographic and time scope
   - Target audience
   - Special requirements
2. Generates structured prompt with:
   - TASK (clear objective)
   - CONTEXT/BACKGROUND (why this matters)
   - SPECIFIC QUESTIONS (3-7 concrete sub-questions)
   - KEYWORDS (search terms)
   - CONSTRAINTS (time, geography, source types)
   - OUTPUT FORMAT (detailed structure)

**File**: `.claude/skills/question-refiner/`

### Research Executor

**Purpose**: Execute the full 7-phase deep research process

**When to Use**:
- You have a structured research prompt
- You want comprehensive research with proper citations
- You need multi-agent parallel research

**What it Does**:
1. **Phase 1**: Verifies question scoping (already done by Question Refiner)
2. **Phase 2**: Creates retrieval plan with subtopics
3. **Phase 3**: Deploys multiple parallel research agents
4. **Phase 4**: Triangulates sources (cross-validation)
5. **Phase 5**: Synthesizes knowledge
6. **Phase 6**: Performs quality assurance
7. **Phase 7**: Generates formatted output

**File**: `.claude/skills/research-executor/`

### GoT Controller

**Purpose**: Manage research as a Graph of Thoughts for complex topics

**When to Use**:
- Research topic is complex or multifaceted
- You need strategic exploration (depth vs breadth)
- High-stakes research where quality is critical

**What it Does**:
- Maintains graph state (nodes, edges, scores)
- Executes GoT operations:
  - **Generate(k)**: Spawn k parallel research paths
  - **Aggregate(k)**: Combine k findings
  - **Refine(1)**: Improve existing finding
  - **Score**: Rate quality (0-10)
  - **KeepBestN(n)**: Prune to top n nodes
- Optimizes research quality through strategic operations

**File**: `.claude/skills/got-controller/`

**Patterns**:
- **Balanced**: Generate(4-5) → Score best → Deepen top paths → Aggregate
- **Depth-first**: Generate(3) → Take best → Generate(3) from it → Deep dive
- **Breadth-first**: Generate(8) → KeepBestN(5) → Generate(2) from each → Aggregate

### Citation Validator

**Purpose**: Ensure all claims have accurate, complete, high-quality citations

**When to Use**:
- Finalizing a research report
- Reviewing someone else's research
- Before publishing or sharing research

**What it Does**:
1. Checks every factual claim has a citation
2. Verifies citation completeness (author, date, title, URL, pages)
3. Rates source quality (A-E scale)
4. Verifies citations support the claims
5. Detects hallucinations
6. Provides correction recommendations

**Quality Scale**:
- **A**: Peer-reviewed, systematic reviews, RCTs
- **B**: Cohort studies, clinical guidelines, reputable analysts
- **C**: Expert opinion, case reports, mechanistic studies
- **D**: Preprints, preliminary research, blogs
- **E**: Anecdotal, theoretical, speculative

**File**: `.claude/skills/citation-validator/`

### Synthesizer

**Purpose**: Combine multiple research findings into coherent reports

**When to Use**:
- Multiple agents have completed research
- You need to combine findings into unified report
- There are contradictions between sources

**What it Does**:
1. Groups findings by themes
2. Identifies consensus and contradictions
3. Resolves conflicting information
4. Creates logical narrative flow
5. Extracts actionable insights
6. Identifies research gaps

**File**: `.claude/skills/synthesizer/`

## Commands Reference

### `/deep-research`

**Usage**: `/deep-research [research topic]`

**Description**: Execute complete deep research workflow

**Workflow**:
1. Question Refiner (ask clarifying questions)
2. Research Executor (7-phase process)
3. Synthesizer (combine findings)
4. Citation Validator (verify quality)

**Output**: Complete research package in `RESEARCH/[topic]/`

### `/refine-question`

**Usage**: `/refine-question [raw question]`

**Description**: Refine question into structured prompt

**Output**: Structured research prompt ready for research

### `/plan-research`

**Usage**: `/plan-research [structured prompt]`

**Description**: Create detailed research execution plan

**Output**: Research plan with subtopics and agent deployment

### `/validate-citations`

**Usage**: `/validate-citations [file path]`

**Description**: Validate citations in research document

**Output**: Validation report with issues and corrections

### `/synthesize-findings`

**Usage**: `/synthesize-findings [directory path]`

**Description**: Synthesize multiple research findings

**Output**: Unified research report

## Usage Examples

### Example 1: Market Research

```
User: /deep-research AI in healthcare market

Claude: I'll help you research AI in healthcare. Let me ask some questions:

1. What specific aspects interest you most?
   - Clinical diagnosis and treatment
   - Drug discovery
   - Hospital operations
   - All of the above

2. What output format do you prefer?
   - Executive summary (3-5 pages)
   - Comprehensive report (20-30 pages)
   - Market analysis with projections

[... more questions ...]

User: Focus on clinical diagnosis, comprehensive report, last 3 years data,
    global scope, audience is healthcare executives

Claude: Perfect. I'll create a research plan and execute multi-agent research.

[Deploys 6 parallel research agents...]

[Synthesizes findings...]

[Validates citations...]

Research complete! Output in RESEARCH/AI_Clinical_Diagnosis_2024/
```

### Example 2: Technical Assessment

```
User: /refine-question Should I use WebAssembly for my project?

Claude: I'll help you research WebAssembly. Quick questions:

1. What type of project?
   - Web application
   - Game development
   - Data processing
   - Other

2. What's your main concern?
   - Performance
   - Browser compatibility
   - Development complexity
   - All of the above

[... generates structured research prompt ...]

User: /deep-research [uses the structured prompt]

[Research executes with technical focus]
```

### Example 3: Academic Literature Review

```
User: /deep-research Transformer architectures in AI, focus on efficiency improvements

Claude: [Asks academic-level questions]

User: Peer-reviewed sources only, 2017-present, comprehensive literature review

Claude: [Deploys academic research agents focusing on:
      - Seminal papers
      - Efficiency techniques (distillation, quantization)
      - Recent advances (2022-2024)
      - Theoretical analyses]

[Generates academic literature review with proper citations]
```

## Research Output Structure

Every `/deep-research` command creates a structured output:

```
RESEARCH/[topic_name]/
├── README.md                    # Overview and navigation
├── executive_summary.md         # 1-2 page key findings
├── full_report.md               # Complete research report
├── data/
│   ├── statistics.md            # Key numbers and facts
│   └── key_facts.md             # Important findings
├── visuals/
│   └── descriptions.md          # Chart/graph descriptions
├── sources/
│   ├── bibliography.md          # Complete citations
│   └── source_quality_table.md  # A-E quality ratings
├── research_notes/
│   └── agent_findings_summary.md # Raw agent outputs
└── appendices/
    ├── methodology.md           # Research methods
    └── limitations.md           # What couldn't be determined
```

## Best Practices

### 1. Be Specific with Your Research Question

**Bad**: "Research AI"

**Good**: "Research AI applications in clinical diagnosis and treatment for healthcare executives making adoption decisions, focusing on US and European markets, 2022-2024 data with projections to 2028"

### 2. Answer Clarifying Questions Thoroughly

The Question Refiner asks questions for a reason. Detailed answers lead to better research.

### 3. Review the Research Plan

When using `/plan-research`, review the plan before execution. Adjust if needed.

### 4. Validate Citations Before Publishing

Always use `/validate-citations` on final reports to ensure quality.

### 5. Start with Executive Summary

Read `executive_summary.md` first, then dive into `full_report.md` for details.

## Advanced Usage

### Using Specific Skills Directly

You can invoke skills without commands:

```
"Use the question-refiner skill to help refine my research question about [topic]"
```

```
"Use the got-controller skill to manage this research using balanced exploration pattern"
```

### Custom Research Patterns

**For comprehensive research**:
```
1. /refine-question [topic]
2. /plan-research [structured prompt]
3. Review and adjust plan
4. Execute research (agents will be deployed)
5. /synthesize-findings [research_notes/]
6. /validate-citations [full_report.md]
```

**For quick research**:
```
/deep-research [specific, well-defined topic]
```

### Combining with GoT Operations

For complex research, explicitly request GoT patterns:

```
"Use the got-controller with depth-first exploration for research on [technical topic]"
```

```
"Use the got-controller with breadth-first exploration for [trend analysis topic]"
```

## Troubleshooting

### Issue: Research takes too long

**Solution**: Narrow the scope. Be more specific about:
- Geographic focus (one country instead of global)
- Time period (last 2 years instead of last 10)
- Specific aspects (one application instead of all applications)

### Issue: Too many results, hard to synthesize

**Solution**: The synthesizer skill handles this. If overwhelmed:
1. Focus on executive summary first
2. Read specific sections of full report
3. Check research_notes for raw agent outputs

### Issue: Citations fail validation

**Solution**: Common citation problems:
- Missing URLs → Use WebSearch to find sources
- Incomplete citations → Add author, date, title
- Dead links → Use archive.org or find alternatives
- Run citation validator again after corrections

### Issue: Contradictory findings

**Solution**: This is normal. The synthesizer will:
1. Acknowledge contradictions
2. Explain why sources might disagree
3. Present multiple perspectives
4. Note uncertainty where it exists

## Integration with Existing Workflows

### As a Pre-writing Step

Use deep research to gather information before writing:
1. `/deep-research [topic]`
2. Review `executive_summary.md` and `full_report.md`
3. Use findings as foundation for your writing
4. Include citations from bibliography

### For Decision Making

Use deep research to inform decisions:
1. `/deep-research [decision topic]`
2. Focus on "Recommendations" section
3. Review "Contradictions" to understand risks
4. Check "Limitations" for unknowns

### For Academic Work

Use deep research for literature reviews:
1. Specify "peer-reviewed sources only"
2. Use citation validator to ensure quality
3. Review bibliography for relevant papers
4. Build on identified research gaps

## Performance Considerations

### Research Time Estimates

- **Quick research** (narrow topic): 10-15 minutes
- **Standard research** (moderate scope): 20-30 minutes
- **Comprehensive research** (broad scope): 30-60 minutes
- **Academic literature review**: 45-90 minutes

Factors affecting time:
- Number of subtopics (3-7)
- Number of agents deployed (3-8)
- Source availability
- Web search speed

### Optimizing for Speed

1. **Be specific**: Narrower topics = faster research
2. **Limit timeframes**: "Last 2 years" faster than "Last 10 years"
3. **Limit geography**: "US market" faster than "Global"
4. **Specify source types**: "Industry reports only" faster than "All sources"

### Optimizing for Quality

1. **Use GoT for complex topics**: Higher quality through strategic exploration
2. **Request citation validation**: Ensures accuracy
3. **Specify source quality requirements**: "A-B rated sources only"
4. **Allow more time**: Quality research takes time

## Future Enhancements

### Planned Features

1. **Additional Skills**:
   - Domain-specific refinements (healthcare.md, financial.md, legal.md)
   - Translation and localization
   - Automated presentation generation

2. **Enhanced GoT Operations**:
   - Backtracking operations
   - Dynamic frontier management
   - Parallel aggregation

3. **Integration Options**:
   - Export to different formats (PDF, PowerPoint)
   - API access for programmatic research
   - Web interface for non-technical users

### Contributing

To contribute new skills or improvements:

1. Follow the skill structure in `.claude/skills/`
2. Include skill.json, instructions.md, examples.md
3. Test with diverse research topics
4. Document usage in this guide

## Support and Documentation

- **CLAUDE.md**: Main documentation with 7-phase process
- **CLAUDE2.md**: Graph of Thoughts framework details
- **PROJECT_UNDERSTANDING.md**: Project architecture and design
- **deepresearchprocess.md**: 7-phase deep research methodology
- **Skill examples**: Each skill has examples.md with detailed examples

## Version History

- **v1.0** (2024-12-25): Initial implementation
  - Question Refiner skill
  - Research Executor skill
  - GoT Controller skill
  - Citation Validator skill
  - Synthesizer skill
  - 5 commands for common workflows

---

**For questions or issues**, refer to the skill-specific examples.md files or the main CLAUDE.md documentation.
