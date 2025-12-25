---
description: 验证研究文档中的引用准确性、完整性和质量
argument-hint: [文件路径]
allowed-tools: Read, WebSearch, WebFetch, Write
---

# Citation Validation

Verify all citations in a research document for accuracy, completeness, and quality.

## File Path

$ARGUMENTS

## Your Task

Use the **citation-validator** skill to:

### Step 1: Claim Detection
Identify all factual claims in the document:
- Statistics and numbers
- Dates and timelines
- Technical specifications
- Market data
- Performance claims
- Quotes and paraphrases

### Step 2: Citation Presence Check
Verify every factual claim has a citation

### Step 3: Citation Completeness Check
Verify each citation includes:
1. Author/Organization
2. Publication Date
3. Source Title
4. URL/DOI
5. Page Numbers (if applicable)

### Step 4: Source Quality Assessment
Rate each source using the A-E scale:
- **A**: Peer-reviewed, systematic reviews, RCTs
- **B**: Cohort studies, clinical guidelines, reputable analysts
- **C**: Expert opinion, case reports, mechanistic studies
- **D**: Preprints, preliminary research, blogs
- **E**: Anecdotal, theoretical, speculative

### Step 5: Citation Accuracy Verification
Use WebSearch or WebFetch to verify sources actually support the claims

### Step 6: Hallucination Detection
Identify claims with no supporting sources or incorrect citations

### Step 7: Generate Validation Report

```markdown
# Citation Validation Report

## Executive Summary
- **Total Claims Analyzed**: [number]
- **Claims with Citations**: [number] ([percentage]%)
- **Complete Citations**: [number] ([percentage]%)
- **Accurate Citations**: [number] ([percentage]%)
- **Potential Hallucinations**: [number]
- **Overall Quality Score**: [score]/10

## Critical Issues (Immediate Action Required)
[List any hallucinations or serious accuracy issues]

## Detailed Findings
[Line-by-line or claim-by-claim analysis]

## Recommendations
[Prioritized list of fixes]
```

## Output

Save the validation report to `sources/citation_validation_report.md` in the research directory.

Begin citation validation now.
