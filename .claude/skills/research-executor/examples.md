# Research Executor Skill - Examples

## Example 1: AI in Healthcare Research

### Structured Input
```markdown
### TASK
Analyze the current state and future trends of AI applications in clinical diagnosis and treatment,
with emphasis on market adoption, technology maturity, and implementation considerations for healthcare
executives making adoption decisions.

### CONTEXT/BACKGROUND
Healthcare organizations are evaluating AI tools for clinical diagnosis and treatment. This research
will inform C-suite executives (CEOs, CTOs, CMOs) at hospital systems and healthcare providers who are
considering AI adoption.

### SPECIFIC QUESTIONS OR SUBTASKS
1. Current Market Landscape: What AI clinical applications are currently in production use?
2. Technology Assessment: What is the current accuracy and reliability of AI diagnostic tools?
3. Implementation Considerations: What are the costs and integration challenges?
4. Vendor Landscape: Who are the leading vendors and what are their differentiators?
5. Future Outlook (2025-2028): What technological breakthroughs are expected?
6. Case Studies: What are detailed examples of successful AI clinical implementations?

### KEYWORDS
AI clinical diagnosis, medical AI adoption, healthcare AI market, computer vision medical imaging,
AI diagnostic accuracy, FDA AI medical devices, clinical decision support systems

### CONSTRAINTS
- Timeframe: Emphasis on 2022-present, with projections to 2028
- Geography: Global scope but prioritize US and European markets
- Source Types: Peer-reviewed clinical trials, industry market reports, FDA regulatory documents

### OUTPUT FORMAT
1. Executive Summary (2-3 pages)
2. Full Report (25-30 pages)
3. Decision Support Tools (checklists, ROI framework)
4. Visual Elements (market charts, vendor comparison tables)
```

### Research Executor Response

**Phase 2: Retrieval Planning**
```markdown
## Research Plan

### Subtopics to Research:
1. **Current Market Landscape**
   - Search queries: ["AI clinical diagnosis market size 2024", "AI healthcare adoption rates statistics",
                      "FDA approved AI medical devices list", "clinical AI production deployments 2024"]
   - Target sources: Industry reports (Gartner, McKinsey Healthcare), FDA databases, market research

2. **Technology Assessment**
   - Search queries: ["AI diagnostic accuracy vs human clinicians studies", "computer vision medical imaging benchmarks",
                      "clinical decision support system effectiveness", "AI radiology accuracy meta-analysis"]
   - Target sources: Peer-reviewed journals, clinical validation studies, systematic reviews

3. **Implementation & ROI**
   - Search queries: ["AI clinical implementation costs case study", "healthcare AI ROI analysis",
                      "EHR AI integration challenges", "AI clinical workflow integration"]
   - Target sources: Case studies, vendor whitepapers, healthcare IT publications

4. **Vendor Landscape**
   - Search queries: ["leading AI clinical diagnosis vendors 2024", "medical AI companies comparison",
                      "healthcare AI vendor market share", "AI radiology vendors evaluation"]
   - Target sources: Industry analyst reports, vendor comparison studies, G2/Capterra reviews

5. **Case Studies**
   - Search queries: ["Mayo Clinic AI implementation case study", "Cleveland Clinic AI diagnostic tools",
                      "European hospital AI deployment success stories", "AI clinical implementation failures lessons"]
   - Target sources: Hospital press releases, academic case studies, healthcare conferences

6. **Future Trends**
   - Search queries: ["AI healthcare trends 2025-2028 predictions", "emerging medical AI technologies",
                      "FDA AI regulation roadmap", "AI clinical trials future applications"]
   - Target sources: Industry trend reports, expert forecasts, regulatory roadmaps

### Multi-Agent Deployment Strategy:
- **Phase 3**: Deploy 6 parallel research agents (1 per subtopic)
- **Phase 4**: Deploy 1 cross-reference agent for fact verification
- **Phase 5**: Synthesize findings into comprehensive report

### Output Structure:
```
RESEARCH/
└── AI_Clinical_Diagnosis_2024/
    ├── README.md
    ├── executive_summary.md
    ├── full_report.md
    ├── data/
    │   ├── market_statistics.md
    │   └── vendor_comparison.md
    ├── visuals/
    │   └── charts_descriptions.md
    ├── sources/
    │   ├── bibliography.md
    │   └── source_quality_table.md
    ├── research_notes/
    │   └── agent_findings_summary.md
    └── appendices/
        └── methodology.md
```

Ready to proceed with research execution?
```

**Phase 3: Iterative Querying** (Launches 6 parallel Task agents)

**Phase 7: Final Output**
```markdown
# AI in Clinical Diagnosis - Research Report

## Executive Summary
[2-3 page summary with key findings and recommendations]

## Full Report
[25-30 page comprehensive analysis with full citations]

## Sources
[Complete bibliography with A-E quality ratings]

## Research Notes
[Detailed findings from each research agent]
```

---

## Example 2: Technology Assessment - WebAssembly

### Structured Input
```markdown
### TASK
Evaluate WebAssembly technology for production web applications, focusing on technical feasibility,
performance benefits, and implementation considerations.

### CONTEXT/BACKGROUND
Development team is considering adopting WebAssembly for performance-critical components.
This research will inform architecture decisions.

### SPECIFIC QUESTIONS OR SUBTASKS
1. What is the current maturity level of WebAssembly?
2. What are the performance improvements over JavaScript?
3. What are the key use cases and successful implementations?
4. What tooling and frameworks are available?
5. What are the limitations and browser compatibility issues?

### KEYWORDS
WebAssembly, WASM, browser performance, JavaScript alternatives, web performance optimization

### CONSTRAINTS
- Timeframe: Emphasis on 2023-2025
- Sources: Technical documentation, benchmark studies, developer community insights

### OUTPUT FORMAT
- Technical assessment report (10-15 pages)
- Performance comparison tables
- Implementation recommendations
- Code examples
```

### Research Executor Response

**Phase 2: Retrieval Planning**
```markdown
## Research Plan

### Subtopics to Research:
1. **WebAssembly Maturity & Adoption**
   - Search queries: ["WebAssembly browser support 2024", "WebAssembly production usage statistics",
                      "companies using WebAssembly", "WebAssembly roadmap features"]
   - Target sources: MDN documentation, browser vendor blogs, usage statistics

2. **Performance Benchmarks**
   - Search queries: ["WebAssembly vs JavaScript performance benchmark 2024",
                      "WebAssembly performance real world studies", "WASM computation speed tests"]
   - Target sources: Technical blogs, benchmark studies, academic papers

3. **Use Cases & Implementations**
   - Search queries: ["WebAssembly success stories case studies", "WebAssembly video encoding",
                      "WebAssembly image processing", "WebAssembly game engines"]
   - Target sources: Company blog posts, GitHub repositories, conference talks

4. **Tooling & Ecosystem**
   - Search queries: ["WebAssembly frameworks 2024", "wasm-bindgen tutorial", "WASM tooling comparison",
                      "WebAssembly development workflow"]
   - Target sources: Documentation sites, developer forums, GitHub projects

5. **Limitations & Challenges**
   - Search queries: ["WebAssembly limitations", "WebAssembly debugging challenges",
                      "WebAssembly garbage collection status", "WASM security concerns"]
   - Target sources: Technical discussions, issue trackers, expert analyses

### Output Structure:
```
RESEARCH/
└── WebAssembly_Assessment_2024/
    ├── README.md
    ├── technical_assessment.md
    ├── performance_benchmarks.md
    ├── use_cases.md
    ├── tooling_guide.md
    ├── limitations.md
    └── sources/
        └── bibliography.md
```
```

---

## Example 3: Market Research - Project Management Software

### Structured Input
```markdown
### TASK
Analyze the project management software market for competitive intelligence and product positioning.

### CONTEXT/BACKGROUND
Our company is launching a new PM tool targeting software development teams.
This research will inform product differentiation and go-to-market strategy.

### SPECIFIC QUESTIONS OR SUBTASKS
1. What is the current market size and growth trajectory?
2. Who are the key competitors and what are their market positions?
3. What are the key features and pricing models?
4. What are the unmet needs and gaps in the market?
5. What are the emerging trends and disruptions?

### KEYWORDS
Project management software, SaaS PM tools, Jira alternatives, software development workflow,
agile project management, dev team productivity tools

### CONSTRAINTS
- Timeframe: 2022-2025 with projections to 2027
- Geography: Global market with emphasis on North America
- Sources: Industry reports, competitor analysis, user reviews

### OUTPUT FORMAT
- Market landscape report (15-20 pages)
- Competitive positioning matrix
- Feature comparison tables
- SWOT analysis for top 5 competitors
- Market opportunity assessment
```

### Research Executor Response

**Phase 2: Retrieval Planning**
```markdown
## Research Plan

### Subtopics to Research:
1. **Market Size & Growth**
   - Search queries: ["project management software market size 2024", "PM tools CAGR forecast",
                      "collaborative software market growth", "work management market trends"]
   - Target sources: Market research reports (Gartner, Forrester, IDC), industry analysis

2. **Competitive Landscape**
   - Search queries: ["project management software market share 2024", "Jira vs Asana vs Linear",
                      "PM tools for software teams comparison", "developer PM tool preferences"]
   - Target sources: Industry reports, user reviews, analyst rankings

3. **Feature Analysis**
   - Search queries: ["project management software features comparison", "agile PM tools must-have features",
                      "software development PM workflow features", "PM tool pricing models 2024"]
   - Target sources: Product documentation, comparison sites, user forums

4. **Market Gaps & Opportunities**
   - Search queries: ["project management software pain points", "developer PM tool frustrations",
                      "PM tool feature requests", "software team PM needs unmet"]
   - Target sources: User reviews, Reddit discussions, feedback forums

5. **Emerging Trends**
   - Search queries: ["project management software trends 2025", "AI in project management tools",
                      "future of work management software", "PM tool integration trends"]
   - Target sources: Industry predictions, trend reports, expert forecasts

### Output Structure:
```
RESEARCH/
└── PM_Software_Market_2024/
    ├── README.md
    ├── market_overview.md
    ├── competitive_landscape.md
    ├── feature_analysis.md
    ├── market_opportunities.md
    ├── trends_2025.md
    ├── data/
    │   ├── market_size_data.md
    │   └── competitor_features.md
    └── sources/
        └── bibliography.md
```
```

---

## Example 4: Academic Literature Review - Transformer Models

### Structured Input
```markdown
### TASK
Conduct a comprehensive literature review of transformer architectures in AI,
focusing on architectural innovations and efficiency improvements.

### CONTEXT/BACKGROUND
This literature review will support a PhD dissertation on efficient transformer architectures.
Target audience: AI researchers and graduate students.

### SPECIFIC QUESTIONS OR SUBTASKS
1. What are the foundational transformer architectures since "Attention Is All You Need" (2017)?
2. What efficiency improvements have been proposed (distillation, quantization, pruning)?
3. What are the key applications across different domains (NLP, vision, multimodal)?
4. What are the theoretical analyses and interpretability studies?
5. What are the current research gaps and future directions?

### KEYWORDS
Transformer architecture, attention mechanism, BERT, GPT, ViT, efficient transformers,
model distillation, quantization, pruning, scaling laws, transformer interpretability

### CONSTRAINTS
- Timeframe: 2017-present (from original transformer paper)
- Sources: Peer-reviewed papers, preprints (arXiv), top conferences (NeurIPS, ICML, ICLR, ACL)
- Quality: Prioritize papers with high citation counts and published in top-tier venues

### OUTPUT FORMAT
- Academic literature review (30-40 pages)
- Categorization by theme (architecture, efficiency, applications, theory)
- Timeline visualization of key developments
- Table comparing architectural innovations
- Bibliography with 50-100 key papers
```

### Research Executor Response

**Phase 2: Retrieval Planning**
```markdown
## Research Plan

### Subtopics to Research:
1. **Foundational Architectures**
   - Search queries: ["transformer architecture seminal papers 2017-2024",
                      "BERT GPT T5 architecture comparison", "vision transformer ViT review",
                      "transformer variants survey"]
   - Target sources: arXiv, Google Scholar, conference proceedings

2. **Efficiency Improvements**
   - Search queries: ["efficient transformer architectures survey", "model distillation transformer",
                      "transformer quantization pruning techniques", "sparse attention mechanisms"]
   - Target sources: Peer-reviewed papers, meta-analyses

3. **Applications by Domain**
   - Search queries: ["transformer NLP applications review", "vision transformer applications",
                      "multimodal transformer models", "transformer in biology chemistry"]
   - Target sources: Domain-specific conferences and journals

4. **Theoretical Analysis**
   - Search queries: ["transformer attention mechanism theoretical analysis",
                      "transformer scaling laws", "transformer interpretability techniques",
                      "why transformers work explanation"]
   - Target sources: Theoretical papers, analysis papers

5. **Research Gaps**
   - Search queries: ["transformer architecture limitations", "open problems transformer research",
                      "future directions transformer models", "unsolved transformer challenges"]
   - Target sources: Position papers, survey papers, workshop proceedings

### Output Structure:
```
RESEARCH/
└── Transformer_Literature_Review/
    ├── README.md
    ├── executive_summary.md
    ├── full_review.md
    ├── architectural_innovations.md
    ├── efficiency_techniques.md
    ├── applications_by_domain.md
    ├── theoretical_foundations.md
    ├── research_gaps.md
    ├── timeline/
    │   └── key_developments.md
    ├── tables/
    │   └── architecture_comparison.md
    └── bibliography.md
```
```

---

## Example 5: Policy Research - GDPR Compliance

### Structured Input
```markdown
### TASK
Provide a comprehensive analysis of GDPR compliance requirements for SaaS companies,
with focus on practical implementation guidance for US-based companies serving European customers.

### CONTEXT/BACKGROUND
US-based SaaS company is preparing to launch in European markets.
This research will guide compliance implementation and legal discussions.

### SPECIFIC QUESTIONS OR SUBTASKS
1. What are the core GDPR requirements for SaaS companies?
2. What data handling and consent management practices are required?
3. What technical controls and security measures must be implemented?
4. What are the documentation and compliance demonstration requirements?
5. What are the penalties for non-compliance and enforcement trends?
6. What are the recent regulatory updates and court interpretations (2022-2024)?

### KEYWORDS
GDPR compliance, SaaS data protection, EU data regulation, Article 25 privacy by design,
data processing agreement, DPIA, DSAR, GDPR fines, EDPB guidance

### CONSTRAINTS
- Timeframe: Current GDPR requirements (2024) with emphasis on 2022-2024 updates
- Geography: EU/EEA requirements, UK GDPR post-Brexit
- Sources: Official EU documents, EDPB guidance, legal analysis, case law

### OUTPUT FORMAT
- Compliance implementation guide (20-25 pages)
- Requirement checklist with priority levels
- Technical control recommendations
- Documentation templates overview
- Risk assessment framework
```

### Research Executor Response

**Phase 2: Retrieval Planning**
```markdown
## Research Plan

### Subtopics to Research:
1. **Core GDPR Requirements**
   - Search queries: ["GDPR requirements SaaS companies 2024", "GDPR data controller processor",
                      "GDPR compliance checklist software", "EDPB guidance SaaS"]
   - Target sources: Official EU GDPR text, EDPB guidelines, ICO documentation

2. **Data Handling & Consent**
   - Search queries: ["GDPR consent management requirements", "lawful basis data processing SaaS",
                      "data subject rights implementation", "cookie consent GDPR 2024"]
   - Target sources: Regulatory guidance, case law, compliance frameworks

3. **Technical Controls**
   - Search queries: ["GDPR technical security measures", "privacy by design implementation SaaS",
                      "data anonymization pseudonymization", "GDPR encryption requirements"]
   - Target sources: Technical guidelines, security frameworks, ENISA standards

4. **Documentation & Demonstration**
   - Search queries: ["GDPR documentation requirements", "records of processing activities template",
                      "DPIA requirement SaaS", "GDPR compliance evidence"]
   - Target sources: Regulatory templates, official guidance

5. **Enforcement & Penalties**
   - Search queries: ["GDPR fines 2022 2023 2024", "GDPR enforcement trends SaaS",
                      "Article 83 GDPR penalties", "EDPB sanction guidelines"]
   - Target sources: Enforcement decisions, penalty databases, legal analysis

6. **Recent Updates**
   - Search queries: ["GDPR updates 2024", "Schrems II decision impact", "EDPB guidelines 2022-2024",
                      "Data Act EU 2024", "UK GDPR changes post-Brexit"]
   - Target sources: Recent regulatory updates, court decisions, legal analysis

### Output Structure:
```
RESEARCH/
└── GDPR_Compliance_Guide_2024/
    ├── README.md
    ├── executive_summary.md
    ├── compliance_guide.md
    ├── requirements_checklist.md
    ├── technical_implementation.md
    ├── documentation_templates/
    │   └── overview.md
    ├── risk_assessment.md
    ├── enforcement_overview.md
    ├── recent_updates.md
    └── sources/
        └── legal_references.md
```
```

---

## Pattern Recognition

Across these examples, the Research Executor consistently:

1. **Decomposes complex topics** into 3-7 actionable subtopics
2. **Generates targeted search queries** for each subtopic
3. **Identifies appropriate sources** based on constraints
4. **Creates clear output structure** before research begins
5. **Presents plan for approval** before launching agents
6. **Launches parallel agents** for efficient research
7. **Delivers structured outputs** matching user requirements

### Key Success Factors:

- **Thorough Planning**: Research plans are detailed and specific
- **Source Awareness**: Matches sources to research domain (academic vs industry vs legal)
- **User Communication**: Presents plans clearly and seeks approval
- **Structured Outputs**: Organizes findings in accessible formats
- **Citation Discipline**: Always maintains source traceability
