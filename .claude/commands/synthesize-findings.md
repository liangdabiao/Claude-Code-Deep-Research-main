---
description: 综合多个研究智能体的发现，生成统一的研究报告
argument-hint: [研究结果目录]
allowed-tools: Read, Write
---

# Synthesize Findings

Combine findings from multiple research agents into a coherent, well-structured research report.

## Findings Directory

$ARGUMENTS

## Your Task

Use the **synthesizer** skill to:

1. **Review and Organize**: Read all research findings from the specified directory

2. **Identify Themes**: Group findings by common themes and topics

3. **Build Consensus**:
   - Strong Consensus: Findings supported by 3+ high-quality sources
   - Moderate Consensus: Findings supported by 2 sources
   - Weak Consensus: Findings from only 1 source
   - No Consensus: Contradictory findings with no resolution

4. **Resolve Contradictions**:
   - Type A: Numerical Discrepancies
   - Type B: Causal Claims
   - Type C: Temporal Changes
   - Type D: Scope Differences

5. **Create Structured Report**:
   ```markdown
   # [Research Topic]: Comprehensive Report

   ## Executive Summary
   ## 1. Introduction
   ## 2. [Theme 1] - Consensus Findings
   ## 3. [Theme 2]
   ## 4. [Theme with Contradictions] - Resolution
   ## 5. Integrated Analysis
   ## 6. Gaps and Limitations
   ## 7. Conclusions and Recommendations
   ## References
   ```

6. **Maintain Citations**: Preserve all source attributions throughout

## Quality Checklist

- [ ] All major findings are included
- [ ] Contradictions are acknowledged and addressed
- [ ] Consensus is clearly distinguished from minority views
- [ ] Citations are preserved and accurate
- [ ] Narrative is coherent and logical
- [ ] Insights are actionable
- [ ] Gaps are acknowledged

## Output

Save the synthesized report to `full_report.md` in the research directory.

Begin synthesis now.
