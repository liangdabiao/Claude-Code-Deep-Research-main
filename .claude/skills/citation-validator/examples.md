# Citation Validator Skill - Examples

## Example 1: Validating AI Market Research Report

### Input Content
```markdown
# AI in Healthcare Market Report

The global AI in healthcare market reached $22.4 billion in 2023 and is projected
to grow at a CAGR of 37.5% through 2030 (Grand View Research, 2024).

Major hospitals using AI include Mayo Clinic, which reports 40% faster diagnoses
with their AI imaging tools (Mayo Clinic, 2024).

According to industry studies, AI diagnostic tools achieve 95% accuracy compared
to human radiologists (Smith et al., 2023).

The FDA has approved over 500 AI medical devices as of 2024 (FDA, 2024).
```

### Validation Report

```markdown
# Citation Validation Report

## Executive Summary
- **Total Claims Analyzed**: 4
- **Claims with Citations**: 4 (100%)
- **Complete Citations**: 2 (50%)
- **Accurate Citations**: 3 (75%)
- **Potential Hallucinations**: 1
- **Overall Quality Score**: 5.5/10

## Critical Issues (Immediate Action Required)

### ⚠ HALLUCINATION DETECTED
**Claim**: "The FDA has approved over 500 AI medical devices as of 2024"
**Citation**: (FDA, 2024)
**Issue**: Number is incorrect
**Verification**:
- FDA database shows: 692 AI/ML-enabled medical devices (as of Dec 2024)
- Claim says "over 500" which is technically correct but understated
- More accurate figure: 692 devices
**Correction Required**: Update to "692 AI/ML-enabled medical devices" with source

## Citation Completeness Issues

### Claim 1: AI market size and growth
**Claim**: "The global AI in healthcare market reached $22.4 billion in 2023..."
**Citation**: (Grand View Research, 2024)
**Completeness**: ✗ INCOMPLETE
**Missing**:
- Full report title
- URL/DOI to verify
- Page numbers
**Recommended Format**:
```
(Grand View Research, 2024, "AI in Healthcare Market Size, Share & Trends")
Full: Grand View Research. (2024). "Artificial Intelligence in Healthcare Market
Size, Share & Trends Analysis Report." Retrieved [date] from [URL]
```

### Claim 3: AI diagnostic accuracy
**Claim**: "AI diagnostic tools achieve 95% accuracy compared to human radiologists"
**Citation**: (Smith et al., 2023)
**Completeness**: ✗ INCOMPLETE
**Missing**:
- Full paper title
- Journal name
- DOI
- Specific study details (sample size, conditions)
**Investigation Needed**: "Smith et al." is too generic - need to identify actual paper

## Source Quality Assessment

| Citation | Type | Rating | Justification |
|----------|------|--------|---------------|
| Grand View Research (2024) | Industry Report | B | Reputable market research firm, but verify with additional sources |
| Mayo Clinic (2024) | Organizational | C | Self-reported data, potential bias, verify with independent studies |
| Smith et al. (2023) | Academic (?) | D | Incomplete citation, cannot verify quality until full details found |
| FDA (2024) | Government | A | Official FDA database, highest quality |

## Detailed Findings

### Claim 1: Market size $22.4B, CAGR 37.5%
**Citation**: (Grand View Research, 2024)
**Verification Status**: ✓ ACCURATE
**Source Check**: Grand View Research "AI in Healthcare Market" report exists
**Figure Verification**: $22.4B for 2023 ✓
**Growth Rate**: 37.5% CAGR ✓
**Recommendation**: Add second source to corroborate (e.g., MarketsandMarkets or Fortune Business Insights)

### Claim 2: Mayo Clinic 40% faster diagnoses
**Citation**: (Mayo Clinic, 2024)
**Verification Status**: ⚠ NEEDS VERIFICATION
**Source Check**: Found Mayo Clinic press release about AI imaging
**Claim Verification**: 40% figure needs specific source
**Bias Warning**: This is self-reported data
**Recommendation**: Find independent study validating Mayo Clinic's claims or present as "self-reported"

### Claim 3: 95% diagnostic accuracy
**Citation**: (Smith et al., 2023)
**Verification Status**: ✗ CANNOT VERIFY
**Issue**: Citation too generic to locate specific paper
**Search Attempted**: "Smith AI diagnostic accuracy 2023" → Multiple results, unclear which
**Action Required**: Find actual paper or remove claim
**Potential Matches** (need verification):
- Smith, A. et al. (2023). "Deep Learning for Medical Image Analysis." Nature.
- Smith, J. et al. (2023). "AI in Radiology: A Comprehensive Review." Lancet Digital Health.

### Claim 4: FDA approved 500+ AI devices
**Citation**: (FDA, 2024)
**Verification Status**: ⚠ INACCURATE NUMBER
**Actual Data**: FDA database shows 692 AI/ML-enabled medical devices (as of Dec 2024)
**Source**: FDA AI/ML-Based Medical Device Database
**Correction**: Update to "692 devices" or "nearly 700 devices"

## Recommendations (Prioritized)

### HIGH PRIORITY
1. **Fix FDA device count**: Update from 500+ to 692 with specific database link
2. **Verify Smith et al. citation**: Find complete citation or replace with verifiable source
3. **Add URL for Grand View Research**: Include direct link to report

### MEDIUM PRIORITY
4. **Corroborate market size data**: Add second source (e.g., Fortune Business Insights)
5. **Verify Mayo Clinic claim**: Find independent source or label as self-reported
6. **Add publication details for all sources**: Include full titles and URLs

### LOW PRIORITY
7. **Standardize citation format**: Use consistent format throughout document
8. **Add access dates**: For all web sources

## Corrected Bibliography

```markdown
Grand View Research. (2024). "Artificial Intelligence in Healthcare Market Size, Share &
Trends Analysis Report, 2024-2030." Retrieved December 2024 from https://www.grandviewresearch.com/
industry-analysis/artificial-intelligence-in-healthcare-market

Mayo Clinic. (2024). "AI-Powered Medical Imaging: Diagnostic Improvements." Mayo Clinic
Press Release. Retrieved December 2024 from [URL - NEEDED]
Note: Self-reported data, independent verification recommended.

[INCOMPLETE - NEEDS FULL CITATION]: Smith et al. (2023).
Action: Locate complete citation or replace with verifiable source.

U.S. Food and Drug Administration. (2024). "Artificial Intelligence and Machine Learning
(AI/ML)-Enabled Medical Devices." FDA Database. Retrieved December 2024 from
https://www.fda.gov/medical-devices/software-medical-device-samd/artificial-intelligence-and-machine-learning-aiml-enabled-medical-devices
```

## Quality Score Breakdown

- Citation Coverage: 3/3 = 100% (3 points)
- Citation Completeness: 2/4 = 50% (1 point)
- Citation Accuracy: 3/4 = 75% (2.25 points)
- Source Quality: Average rating = (B+C+D+A)/4 = (2+1.5+1+3)/4 = 1.875 (1.88 points)
- Hallucination Penalty: -1 (for inaccurate FDA figure)

**Total Score**: 3 + 1 + 2.25 + 1.88 - 1 = **6.13/10**

**Assessment**: FAIR - Significant citation quality issues that undermine credibility.
```

---

## Example 2: Validating Technical Blog Post

### Input Content
```markdown
# WebAssembly Performance Guide

WebAssembly provides near-native performance in web browsers. According to Mozilla
developers, WebAssembly runs at 90-95% of native code speed (Mozilla, 2023).

Major companies using WebAssembly in production include AutoCAD, Figma, and Google Earth
(WebAssembly.org, 2024).

Browser support for WebAssembly is universal, with 96% of global browsers supporting it
(Caniuse, 2024).
```

### Validation Report

```markdown
# Citation Validation Report

## Executive Summary
- **Total Claims Analyzed**: 3
- **Claims with Citations**: 3 (100%)
- **Complete Citations**: 2 (67%)
- **Accurate Citations**: 3 (100%)
- **Potential Hallucinations**: 0
- **Overall Quality Score**: 7.8/10

## Detailed Findings

### Claim 1: WebAssembly 90-95% native speed
**Citation**: (Mozilla, 2023)
**Completeness**: ✗ INCOMPLETE
**Missing**: Specific article title, URL
**Verification**: ✓ CLAIM SUPPORTED
**Source Found**: Mozilla Developer Network blog on WebAssembly performance
**Accuracy**: 90-95% figure is cited correctly
**Quality Rating**: B (Mozilla is authoritative source)
**Recommendation**: Add full citation with URL

### Claim 2: Companies using WebAssembly
**Citation**: (WebAssembly.org, 2024)
**Completeness**: ✓ COMPLETE
**Verification**: ✓ ACCURATE
**Source**: WebAssembly.org case studies section
**Accuracy**: AutoCAD, Figma, Google Earth all listed ✓
**Quality Rating**: C (Industry association site, acceptable but not independent verification)
**Recommendation**: Add company blog posts or press releases for stronger support

### Claim 3: 96% browser support
**Citation**: (Caniuse, 2024)
**Completeness**: ✓ COMPLETE
**Verification**: ✓ ACCURATE
**Source**: caniuse.com search for "WebAssembly"
**Accuracy**: 96.47% global support (rounds to 96%) ✓
**Quality Rating**: A (Caniuse is authoritative for browser support data)
**No issues**: Citation is excellent

## Recommendations

### LOW PRIORITY (Quality Improvements)
1. Add Mozilla MDN specific article URL for Claim 1
2. Supplement company list (Claim 2) with independent sources
3. Consider adding WebAssembly Roadmap source for future features

## Overall Assessment

**GOOD** - All claims are accurate and properly cited. Minor improvements to citation
completeness would elevate this to excellent quality.
```

---

## Example 3: Detecting Hallucinations

### Input Content (Suspected Hallucinations)
```markdown
# AI Research Developments

A recent Harvard study proved that GPT-4 achieves 99.2% accuracy on medical board exams,
surpassing human doctors who average 87% (Chen et al., 2024).

OpenAI's latest model, GPT-5, was released in March 2024 and has 10 trillion parameters
(OpenAI, 2024).

According to Nature magazine, 83% of scientists believe AI will lead to human-level AGI
by 2027 (Nature, 2024).
```

### Validation Report

```markdown
# Citation Validation Report - CRITICAL ISSUES DETECTED

## ⚠ CRITICAL: MULTIPLE HALLUCINATIONS DETECTED

### Hallucination #1: GPT-4 medical board exam accuracy
**Claim**: "GPT-4 achieves 99.2% accuracy on medical board exams"
**Citation**: (Chen et al., 2024)
**Status**: ✗ FALSE / MISLEADING

**Investigation**:
- Searched for: "Chen GPT-4 medical board exam 2024"
- Found: Chen et al. (2023) - NOT 2024
- Actual finding: USMLE Step exams accuracy = 86.6% (NOT 99.2%)
- Real study: "Performance of ChatGPT on USMLE" (Gilson et al., 2023) - 86.6%

**Conclusion**: Both the percentage (99.2%) and citation are incorrect.
**Correction**: GPT-4 achieves approximately 86-87% on USMLE exams (not 99.2%)

### Hallucination #2: GPT-5 release
**Claim**: "GPT-5 was released in March 2024 with 10 trillion parameters"
**Citation**: (OpenAI, 2024)
**Status**: ✗ COMPLETELY FALSE

**Investigation**:
- OpenAI has NOT released GPT-5 as of December 2024
- No announcement of GPT-5 release date
- Parameter count claim (10 trillion) is unsubstantiated
- Current latest model: GPT-4o (released May 2024)

**Conclusion**: This entire claim is fabricated.
**Action Required**: REMOVE THIS CLAIM ENTIRELY

### Hallucination #3: Nature survey on AGI timeline
**Claim**: "83% of scientists believe AGI by 2027"
**Citation**: (Nature, 2024)
**Status**: ✗ MISATTRIBUTED / FALSE

**Investigation**:
- Searched Nature for AGI survey 2024
- Found: No such survey in Nature in 2024
- Closest match: AI Impacts survey (2023) - different question, different results
- Real finding: 50% of AI researchers believe HLMI (high-level machine intelligence) by 2058
- The 83% figure and 2027 date appear to be fabricated

**Conclusion**: Citation and figure are incorrect.
**Action Required**: Remove or correct with actual survey data

## Summary of Issues

| Claim | Status | Action Required |
|-------|--------|-----------------|
| GPT-4 medical exam accuracy | ✗ False data | Correct to ~86-87% with proper citation |
| GPT-5 release | ✗ Completely fabricated | REMOVE ENTIRELY |
| Scientists AGI prediction | ✗ False citation | Remove or find real survey |

## Recommendations

**IMMEDIATE ACTION REQUIRED**:
1. **DELETE** the GPT-5 claim entirely - it is completely false
2. **CORRECT** the GPT-4 medical exam accuracy with actual data
3. **REMOVE or REPLACE** the AGI survey claim with verifiable data

**CREDIBILITY ASSESSMENT**: This document contains multiple significant hallucinations
that completely undermine its credibility. The author appears to have fabricated data,
figures, and citations.

**OVERALL QUALITY SCORE**: 0.5/10 (only because 2 of 3 claims have some basis in reality)

**RECOMMENDATION**: Do not publish without complete rewrite with accurate citations.
```

---

## Example 4: Validating Academic Literature Review

### Input Content (Well-Cited)
```markdown
# Transformer Architecture Literature Review

The transformer architecture was introduced in "Attention Is All You Need" by Vaswani et al.
(2017), published at NeurIPS 2017 (Vaswani et al., 2017, p. 4).

BERT, introduced by Devlin et al. (2019), achieved state-of-the-art results on 11 NLP tasks
(Devlin et al., 2019, NAACL-HLT, https://doi.org/10.18653/v1/N19-1423).

The original GPT paper by Radford et al. (2018) demonstrated that unsupervised pre-training
could significantly improve language understanding (Radford et al., 2018, OpenAI Blog,
https://openai.com/research/language-unsupervised/).
```

### Validation Report

```markdown
# Citation Validation Report

## Executive Summary
- **Total Claims Analyzed**: 3
- **Claims with Citations**: 3 (100%)
- **Complete Citations**: 3 (100%)
- **Accurate Citations**: 3 (100%)
- **Potential Hallucinations**: 0
- **Overall Quality Score**: 9.8/10

## Detailed Findings

### Claim 1: Transformer introduction
**Citation**: (Vaswani et al., 2017, p. 4)
**Completeness**: ✓ EXCELLENT
**Verification**: ✓ ACCURATE
**Source**: "Attention Is All You Need" - NeurIPS 2017
**Quality Rating**: A (Seminal paper, top-tier conference)
**Page Number**: p. 4 is appropriate
**Assessment**: Perfect citation

### Claim 2: BERT achievements
**Citation**: (Devlin et al., 2019, NAACL-HLT, https://doi.org/10.18653/v1/N19-1423)
**Completeness**: ✓ EXCELLENT
**Verification**: ✓ ACCURATE
**Source**: "BERT: Pre-training of Deep Bidirectional Transformers"
**Quality Rating**: A (Top-tier NLP conference, DOI provided)
**Claim Accuracy**: 11 tasks mentioned correctly ✓
**Assessment**: Perfect citation

### Claim 3: GPT unsupervised pre-training
**Citation**: (Radford et al., 2018, OpenAI Blog, https://openai.com/...)
**Completeness**: ✓ GOOD
**Verification**: ✓ ACCURATE
**Source**: "Improving Language Understanding by Generative Pre-Training"
**Quality Rating**: B (OpenAI blog post, not peer-reviewed)
**Note**: While accurate, could be supplemented with journal publication if available
**Assessment**: Good citation, acceptable quality

## Recommendations

### OPTIONAL ENHANCEMENTS
1. For GPT claim: Consider adding arXiv citation (1803.06846) for academic rigor
2. Consider adding publication months for more precise references

## Overall Assessment

**EXCELLENT** - All citations are complete, accurate, and from high-quality sources.
This represents best practices for citation in academic writing.

**Quality Score**: 9.8/10
- Minor improvement possible (add arXiv for GPT paper)
- No significant issues
- Ready for publication
```

---

## Example 5: Chain-of-Verification for Medical Claim

### Critical Claim
```markdown
"Metformin reduces the risk of developing type 2 diabetes by 31% over 3 years."
```

### Chain-of-Verification Process

```markdown
# Chain-of-Verification (CoVe) Report

## Original Claim
"Metformin reduces the risk of developing type 2 diabetes by 31% over 3 years."

## Verification Round 1: Find Primary Sources

### Source 1: Diabetes Prevention Program (DPP)
**Search**: "Diabetes Prevention Program metformin 31% reduction"
**Found**: Knowler et al. (2002). "Reduction in the Incidence of Type 2 Diabetes..."
**Journal**: New England Journal of Medicine
**Finding**: 31% reduction with metformin vs placebo ✓
**Sample Size**: 2,155 participants
**Follow-up**: 2.8 years (average)
**Quality Rating**: A (Landmark RCT, top-tier journal)
**PMID**: 11832527

### Source 2: ADA Diabetes Guidelines
**Search**: "American Diabetes Association metformin prevention guidelines 2023"
**Found**: ADA Standards of Care (2023)
**Reference**: Cites DPP study
**Recommendation**: Metformin for diabetes prevention
**Quality Rating**: A (Clinical practice guidelines)

### Source 3: Systematic Review
**Search**: "metformin diabetes prevention meta-analysis 2020"
**Found**: Zhu et al. (2020). "Efficacy and Safety of Metformin..."
**Journal**: Diabetes Care
**Finding**: Confirms 28-31% reduction range
**Quality Rating**: A (Systematic review, top-tier journal)

## Verification Round 2: Cross-Check Details

### Claim Accuracy Check
| Element | Claim | Source 1 | Source 2 | Source 3 | Status |
|---------|-------|----------|----------|----------|--------|
| Drug | Metformin | ✓ | ✓ | ✓ | ✓ |
| Outcome | Diabetes risk reduction | ✓ | ✓ | ✓ | ✓ |
| Magnitude | 31% | ✓ (31%) | ✓ (cites 31%) | ✓ (28-31%) | ✓ |
| Duration | 3 years | ✓ (2.8 yrs) | ✓ (cites DPP) | ✓ (similar) | ✓ |

### Context Verification
- **Population**: High-risk individuals (prediabetes) ✓
- **Comparison**: Metformin vs placebo ✓
- **Study Design**: Randomized Controlled Trial ✓
- **Statistical Significance**: p < 0.001 ✓

## Verification Round 3: Assess Consensus

**Consensus Level**: ✓ STRONG CONSENSUS
- 3 independent high-quality sources (A-rated)
- All sources agree on 28-31% reduction range
- Original RCT + systematic review + clinical guidelines
- No contradictory evidence found

## Final Verification Result

**Claim Status**: ✓ VERIFIED AS ACCURATE

**Confidence Level**: HIGH

**Recommended Citation Format**:
```
The Diabetes Prevention Program demonstrated that metformin reduces diabetes
incidence by 31% over 2.8 years in high-risk individuals (Knowler et al., 2002,
NEJM, PMID: 11832527, https://doi.org/10.1056/NEJMoa012512). This finding is
supported by subsequent systematic reviews (Zhu et al., 2020, Diabetes Care) and
is reflected in current ADA clinical practice guidelines (ADA, 2023).
```

**Quality Assessment**: EXCELLENT
- Multiple high-quality sources
- Primary source (RCT) available
- Independent verification via systematic review
- Clinical guideline endorsement
- All details accurate and in context
```

---

## Common Citation Patterns

### Pattern 1: Progressive Improvement
```
Draft 1: "Studies show AI is growing fast."
Draft 2: "AI market growing 37% annually (Research, 2024)."
Draft 3: "AI in healthcare growing 37.5% CAGR through 2030 (Grand View Research, 2024)."
Draft 4: "AI in healthcare market: $22.4B in 2023, 37.5% CAGR to 2030 (Grand View Research, 2024; corroborated by MarketsandMarkets, 2024)."
```

### Pattern 2: Source Quality Ladder
```
Level E: "People say..."
Level D: "According to a blog post..."
Level C: "TechCrunch reported..."
Level B: "According to Gartner research..."
Level A: "A peer-reviewed study in Nature (Smith et al., 2023) demonstrated..."
```

### Pattern 3: Claim Strength Scaling
```
Speculative: "May", "might", "could", "potentially"
Likely: "Likely", "probably", "appears to"
Certain: "Shows", "demonstrates", "proves" (requires strongest sources)
```

---

## Key Takeaways

1. **Always Verify**: Never assume a citation is correct without checking
2. **Be Specific**: "Smith et al." is not enough - need full details
3. **Check Context**: Does the source actually support the specific claim?
4. **Rate Quality**: Not all sources are equal - use A-E ratings
5. **Detect Patterns**: Multiple issues suggest systemic problems
6. **Provide Fixes**: Don't just identify problems - suggest solutions
7. **Chain-of-Verification**: For critical claims, use multiple sources
