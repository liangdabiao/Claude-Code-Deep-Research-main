# Question Refiner Skill - Examples

## Example 1: Business Intelligence Research

### User Input
```
"I need research on AI in healthcare"
```

### Question Refiner Response
```
I'll help you research AI in healthcare. Let me ask some questions to ensure I deliver exactly what you need:

**1. Specific Focus**: What aspects of AI in healthcare interest you most?
   - Clinical diagnosis and treatment
   - Drug discovery and development
   - Hospital operations and management
   - Patient care and monitoring
   - Medical imaging and radiology
   - All of the above

**2. Output Format**: What type of deliverable would be most useful?
   - Comprehensive report (20-30 pages)
   - Executive summary (3-5 pages)
   - Presentation slides
   - Data analysis with visualizations

**3. Scope**: Any specific constraints?
   - Geographic focus (US, Europe, Global?)
   - Time period (current state, last 5 years, future projections?)
   - Healthcare sectors (hospitals, pharma, insurance, tech companies?)

**4. Audience**: Who will be reading this research?
   - Technical team
   - Business executives
   - Healthcare professionals
   - General audience
```

### User Provides Clarification
```
"Focus on clinical diagnosis, comprehensive report, global scope but emphasize US and Europe,
last 3 years plus future trends. Audience is healthcare executives considering AI adoption."
```

### Final Structured Prompt Generated
```markdown
### TASK

Analyze the current state and future trends of AI applications in clinical diagnosis and treatment,
with emphasis on market adoption, technology maturity, and implementation considerations for healthcare
executives making adoption decisions.

### CONTEXT/BACKGROUND

Healthcare organizations are evaluating AI tools for clinical diagnosis and treatment. This research
will inform C-suite executives (CEOs, CTOs, CMOs) at hospital systems and healthcare providers who are
considering AI adoption. The goal is to provide a strategic roadmap based on current market realities,
proven use cases, and realistic future projections.

### SPECIFIC QUESTIONS OR SUBTASKS

1. Current Market Landscape:
   - What AI clinical applications are currently in production use (not just pilot programs)?
   - What are the adoption rates among different healthcare provider segments?
   - Which clinical specialties have the most mature AI solutions?

2. Technology Assessment:
   - What is the current accuracy and reliability of AI diagnostic tools compared to human clinicians?
   - What are the technical limitations and failure modes?
   - How do different AI approaches (computer vision, NLP, predictive analytics) compare in clinical effectiveness?

3. Implementation Considerations:
   - What are the costs (implementation, training, maintenance) of AI clinical systems?
   - What integration challenges exist with existing healthcare IT systems (EHR, PACS, etc.)?
   - What regulatory approvals (FDA, CE marking) are required and what's the approval timeline?

4. Vendor Landscape:
   - Who are the leading vendors for AI clinical tools?
   - What are the key differentiators between vendors?
   - Which vendors have proven track records with large-scale deployments?

5. Future Outlook (2025-2028):
   - What technological breakthroughs are expected in the next 3 years?
   - How will regulatory landscapes evolve?
   - What emerging clinical applications show the most promise?

6. Case Studies:
   - What are 3-5 detailed case studies of successful AI clinical implementations?
   - What were the realized benefits (reduced diagnosis time, improved accuracy, cost savings)?
   - What lessons were learned from failures or challenges?

### KEYWORDS

AI clinical diagnosis, medical AI adoption, healthcare AI market, computer vision medical imaging,
AI diagnostic accuracy, FDA AI medical devices, clinical decision support systems, AI radiology,
AI pathology, healthcare AI ROI, telemedicine AI, AI treatment recommendations

### CONSTRAINTS

- **Timeframe**: Emphasis on 2022-present, with projections to 2028
- **Geography**: Global scope but prioritize US and European markets
- **Source Types**:
  - Peer-reviewed clinical trials and validation studies
  - Industry market reports (Gartner, Forrester, McKinsey healthcare)
  - FDA and EMA regulatory documents and approvals
  - Vendor case studies and technical documentation
  - Healthcare system press releases and implementation reports
- **Quality**: Prioritize sources with actual clinical deployment data over theoretical papers

### OUTPUT FORMAT

1. **Executive Summary** (2-3 pages)
   - Key findings and actionable recommendations
   - Market maturity assessment (Ready/Pilot/Experimental)
   - Top 3 strategic recommendations for healthcare executives

2. **Full Report** (25-30 pages)
   - Introduction and market overview
   - Current applications by clinical specialty (radiology, pathology, cardiology, etc.)
   - Technology deep-dive with accuracy benchmarks
   - Implementation guide with cost-benefit analysis
   - Vendor comparison matrix
   - Case studies (3-5 detailed examples)
   - Future roadmap with timelines
   - Risk assessment and mitigation strategies

3. **Decision Support Tools**:
   - Vendor evaluation checklist
   - ROI calculation framework
   - Implementation timeline template
   - Risk assessment matrix

4. **Visual Elements**:
   - Market size and growth charts (2022-2028)
   - Technology maturity timeline
   - Vendor comparison tables
   - Implementation flow diagram

5. **Citation Format**:
   - Inline numeric superscripts [1], [2], [3]
   - Full bibliography with URLs/DOIs
   - Include publication dates and source credibility ratings (A-E)

### FINAL INSTRUCTIONS

Remain concise yet comprehensive. Prioritize actionable insights over theoretical discussion.
Focus on what healthcare executives NEED TO KNOW to make adoption decisions.

**CRITICAL REQUIREMENTS**:
- Every claim must include: Author/Organization, Date, Source Title, URL/DOI
- Clinical accuracy claims must cite specific studies with sample sizes
- Cost/benefit claims must cite specific implementations or credible market research
- Distinguish between what's theoretically possible vs. what's production-ready
- Acknowledge limitations and uncertainties where they exist

If any aspect of this research scope is unclear, ask for clarification before proceeding.
```

---

## Example 2: Technical Deep-Dive

### User Input
```
"Research WebAssembly for me"
```

### Question Refiner Response
```
I'll help you research WebAssembly. To provide the most relevant information, I need to understand your specific needs:

**1. Research Angle**: What aspect of WebAssembly interests you most?
   - Technical architecture and how it works
   - Browser support and compatibility
   - Use cases and applications
   - Performance benchmarks
   - Comparison with alternatives (JavaScript, native code)
   - Future roadmap and upcoming features
   - All of the above

**2. Purpose**: Why are you researching WebAssembly?
   - Evaluating whether to use it in a project
   - Technical presentation or training material
   - Investment or product decision
   - General learning/curiosity
   - Other?

**3. Technical Depth**: What's your technical background?
   - Web developer (frontend/backend)
   - Systems programmer (C++, Rust, etc.)
   - Technical manager/architect
   - Non-technical

**4. Output Format**: What would be most useful?
   - Technical whitepaper
   - Implementation guide
   - Comparison report
   - Executive summary

**5. Specific Questions**: Is there anything specific you want to know?
   - Current browser support percentages?
   - Performance improvements over JavaScript?
   - How to compile code to WASM?
   - Leading companies using it in production?
```

---

## Example 3: Policy/Legal Research

### User Input
```
"I need to understand GDPR compliance for SaaS companies"
```

### Question Refiner Response
```
I'll help you research GDPR compliance for SaaS companies. Let me clarify a few things:

**1. Company Stage**: What describes your situation best?
   - Early-stage startup (pre-product)
   - Growth-stage (launching in Europe)
   - Established (already operating, reviewing compliance)
   - Preparing for GDPR audit

**2. Specific Concerns**: What aspects of GDPR are most relevant?
   - Data collection and consent management
   - Data storage and processing requirements
   - User rights (access, deletion, portability)
   - Data breach notification procedures
   - Cross-border data transfer
   - Vendor/supplier management
   - All of the above

**3. Geography**:
   - EU/EEA countries only?
   - Include UK (post-Brexit GDPR)?
   - European companies serving US customers?
   - US companies serving European customers?

**4. Output Format**:
   - Compliance checklist
   - Implementation guide
   - Legal analysis (for discussions with lawyers)
   - Technical recommendations for engineers

**5. Timeline**:
   - Focus on current (2024-2025) requirements?
   - Include upcoming regulatory changes?
```

---

## Example 4: Academic/Literature Review

### User Input
```
"Write a literature review on transformer models"
```

### Question Refiner Response
```
I'll help you create a literature review on transformer models. Let me clarify your requirements:

**1. Scope**: What aspect of transformers should I focus on?
   - Architecture and theoretical foundations
   - Applications (NLP, computer vision, multimodal)
   - Efficiency improvements (distillation, quantization, pruning)
   - Training techniques and optimizations
   - Interpretability and analysis
   - Specific domain applications (healthcare, finance, etc.)
   - Comprehensive overview of all aspects

**2. Academic Level**:
   - Undergraduate survey
   - Master's thesis literature review
   - PhD-level comprehensive review
   - Survey paper for publication

**3. Timeframe**:
   - From original "Attention Is All You Need" (2017) to present?
   - Focus on recent developments (last 2-3 years)?
   - Include historical context and earlier related work?

**4. Length**:
   - Brief overview (5-10 pages)
   - Standard literature review (15-25 pages)
   - Comprehensive survey (40+ pages)

**5. Key Papers**: Are there specific papers you want included?
   - Must-cite seminal papers?
   - Recent breakthroughs to highlight?
   - Your own work (if this is for a thesis)?

**6. Output Format**:
   - Academic paper with citations
   - Annotated bibliography
   - Visual timeline of developments
   - Categorization by application/domain
```

---

## Example 5: Competitive Analysis

### User Input
```
"Research the project management software market"
```

### Question Refiner Response
```
I'll help you research the project management software market. To provide the most valuable insights:

**1. Research Purpose**: What will this research inform?
   - Product development for a new PM tool
   - Investment decision (due diligence)
   - Marketing strategy (positioning against competitors)
   - Technology selection (which tool to adopt)

**2. Market Segment**:
   - Enterprise PM tools (Jira, Microsoft Project)
   - Collaborative/work management (Asana, Monday, Notion)
   - Technical/project tracking (Linear, Shortcut)
   - All-in-one suites (ClickUp, Smartsheet)
   - Open-source/self-hosted alternatives

**3. Key Metrics**: What data points matter most?
   - Market size and growth (CAGR)
   - User adoption and retention
   - Pricing models and revenue
   - Feature comparison matrix
   - User satisfaction scores
   - Technical capabilities and limitations

**4. Geography**:
   - Global market
   - North America focus
   - Europe focus
   - Specific countries

**5. Timeframe**:
   - Current state (2024-2025)
   - Historical trends (last 5 years)
   - Future projections (next 3-5 years)

**6. Output**:
   - Market landscape report
   - Competitive positioning map
   - Feature comparison tables
   - SWOT analysis for key players
```

---

## Pattern Recognition

Across these examples, notice the Question Refiner consistently:

1. **Starts with "I'll help you..."** - establishes collaborative tone
2. **Asks 4-6 focused questions** - not too many, not too few
3. **Provides multiple-choice options** - makes it easy for user to respond
4. **Probes for context/purpose** - understands WHY research is needed
5. **Clarifies technical depth** - matches output to user's expertise
6. **Confirms format preferences** - ensures deliverable matches needs
7. **Identifies constraints** - time, geography, source types

The structured prompts generated are:
- **Highly specific** - every field filled with concrete details
- **Action-oriented** - tell researchers exactly what to do
- **Well-structured** - clear hierarchy and organization
- **Citation-focused** - emphasize source requirements
- **User-centric** - reflect the user's stated needs
