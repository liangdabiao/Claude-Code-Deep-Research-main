# GoT Controller Skill - Examples

## Example 1: Balanced Exploration - AI in Healthcare

### Research Topic
"AI applications in clinical diagnosis and treatment"

### GoT Execution

**Iteration 1: Initial Exploration**
```markdown
**Operation**: Generate(5) from root

Launched 5 parallel research agents:
┌─────────────────────────────────────────────────────────────┐
│ Agent 1: Current Market Landscape                          │
│ Focus: Market size, adoption rates, production deployments  │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│ Agent 2: Technology Assessment                             │
│ Focus: Accuracy, capabilities, technical maturity           │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│ Agent 3: Implementation Challenges                          │
│ Focus: Costs, integration, regulatory barriers              │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│ Agent 4: Vendor Landscape                                   │
│ Focus: Key players, differentiators, market shares          │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│ Agent 5: Case Studies                                       │
│ Focus: Successful implementations, lessons learned          │
└─────────────────────────────────────────────────────────────┘

Results:
- Node 1 (Market): Score 7.8/10 - Good industry data, some gaps
- Node 2 (Technology): Score 8.9/10 - Excellent sources, comprehensive
- Node 3 (Implementation): Score 7.2/10 - Adequate, limited real-world data
- Node 4 (Vendors): Score 6.8/10 - Some bias concerns, incomplete coverage
- Node 5 (Case Studies): Score 8.5/10 - Strong examples, good citations

**Decision**: KeepBestN(4) - prune Node 4 (score < 7.0)
```

**Iteration 2: Strategic Expansion**
```markdown
**Operation**: Diversified strategy based on scores

High Score (Node 2, Technology: 8.9) → Generate(2) deeper:
├─ Node 2a: Diagnostic accuracy benchmarks → Score 9.2/10
└─ Node 2b: Comparison by medical specialty → Score 8.7/10

High Score (Node 5, Case Studies: 8.5) → Generate(1) deeper:
└─ Node 5a: ROI and cost-benefit analysis → Score 8.1/10

Medium Scores → Refine(1) each:
├─ Node 1 (Market): 7.8 → 8.2 (improved with recent data)
└─ Node 3 (Implementation): 7.2 → 7.6 (clarified regulatory aspects)
```

**Iteration 3: Aggregation**
```markdown
**Operation**: Aggregate(8)

Input nodes: [1, 2, 2a, 2b, 3, 5, 5a]
(Corrected: 7 nodes after refinement)

Aggregation process:
1. Identify consensus points across all nodes
2. Resolve contradictions (e.g., adoption rates differ)
3. Extract key insights by category
4. Create unified narrative

Result:
- Aggregated Node: Score 9.4/10
- Comprehensive synthesis combining:
  * Market landscape with latest data
  * Technical assessment with benchmarks
  * Implementation considerations
  * Real-world case studies with ROI
```

**Iteration 4: Final Polish**
```markdown
**Operation**: Refine(1) aggregated node

Refinements:
- Improved citation completeness (added missing DOIs)
- Enhanced structure (better flow between sections)
- Clarified recommendations (more actionable)
- Added visual element descriptions

Final Output Score: 9.7/10 (Excellent)
```

**Final Graph State**:
```
Nodes: 11 total
  - 5 initial (1 pruned)
  - 3 generated from high-scoring nodes
  - 2 refined
  - 1 aggregated
  - 1 final (refined aggregate)

Operations: 4 iterations
  - Generate: 5 + 3 = 8 operations
  - Score: 11 operations
  - KeepBestN: 1 operation
  - Refine: 3 operations
  - Aggregate: 1 operation

Research Quality: Excellent (9.7/10)
  - Comprehensive coverage of all aspects
  - High-quality sources throughout
  - No unresolved contradictions
  - Actionable insights for healthcare executives
```

---

## Example 2: Depth-First Exploration - Quantum Computing Security

### Research Topic
"Post-quantum cryptography threats and preparation strategies"

### GoT Execution

**Iteration 1: Initial Exploration**
```markdown
**Operation**: Generate(3) from root

Launched 3 parallel agents:
- Agent 1: Current quantum computing capabilities → Score 7.5/10
- Agent 2: Cryptographic vulnerabilities → Score 8.8/10
- Agent 3: NIST post-quantum standards → Score 7.9/10

**Decision**: Node 2 has highest score (8.8) - this is the critical path
```

**Iteration 2: Deep Dive on Critical Path**
```markdown
**Operation**: Generate(3) from Node 2 (vulnerabilities)

Launched 3 specialized agents:
├─ Node 2a: RSA/ECC vulnerability timeline → Score 9.1/10
├─ Node 2b: Specific quantum algorithms (Shor, Grover) → Score 9.3/10
└─ Node 2c: Current quantum computer capabilities vs requirements → Score 8.6/10

**Analysis**: Node 2b (quantum algorithms) is most critical - deep dive further
```

**Iteration 3: Deepest Dive**
```markdown
**Operation**: Generate(2) from Node 2b (quantum algorithms)

Launched 2 ultra-specialized agents:
├─ Node 2b-i: Shor's algorithm implementation status → Score 9.5/10
└─ Node 2b-ii: Quantum resources required for breaking encryption → Score 9.4/10

**Both nodes excellent - aggregate to create definitive threat analysis**
```

**Iteration 4: Lateral Integration**
```markdown
**Operation**: Aggregate(5)

Now combine deep technical analysis with other aspects:
- Node 2b-i (Shor's algorithm): 9.5
- Node 2b-ii (Quantum resources): 9.4
- Node 2a (Vulnerability timeline): 9.1
- Node 3 (NIST standards): 7.9 → Refine to 8.3
- Node 1 (Current capabilities): 7.5 → Refine to 8.0

Create comprehensive "Post-Quantum Threat Assessment"
```

**Iteration 5: Final Synthesis**
```markdown
**Operation**: Refine(1) aggregated node

Focus on:
- Actionable timeline (when to act)
- Specific recommendations (what to migrate)
- Risk assessment (who is most vulnerable)

Final Output Score: 9.6/10
```

**Strategy Analysis**:
```
This was a DEPTH-FIRST approach:
- Identified critical path early (vulnerabilities)
- Drilled down 3 levels deep on that path
- Achieved exceptional depth on most critical aspect
- Then integrated with other important aspects

Best for: High-stakes, technically complex topics where depth > breadth
```

---

## Example 3: Breadth-First Exploration - Emerging Technology Trends

### Research Topic
"Emerging AI trends that will impact software development (2025-2028)"

### GoT Execution

**Iteration 1: Wide Exploration**
```markdown
**Operation**: Generate(8) from root

Launched 8 parallel trend-analysis agents:
├─ Agent 1: AI coding assistants (Copilot, Cursor) → Score 8.2/10
├─ Agent 2: AI in testing/QA → Score 7.8/10
├─ Agent 3: AI for documentation → Score 7.1/10
├─ Agent 4: AI in DevOps/CI/CD → Score 7.9/10
├─ Agent 5: AI-powered code refactoring → Score 8.5/10
├─ Agent 6: AI for legacy modernization → Score 6.9/10
├─ Agent 7: AI in security/auditing → Score 7.4/10
└─ Agent 8: AI for requirements engineering → Score 6.5/10

**Decision**: KeepBestN(5) - prune Agents 6 (6.9) and 8 (6.5)
```

**Iteration 2: Second-Level Exploration**
```markdown
**Operation**: Generate(2) from each of top 5 nodes

From Node 1 (AI coding assistants: 8.2):
├─ Node 1a: Multi-file understanding → Score 8.7/10
└─ Node 1b: Personalization and learning → Score 8.3/10

From Node 5 (AI refactoring: 8.5):
├─ Node 5a: Automated refactoring at scale → Score 9.0/10
└─ Node 5b: Language translation between codebases → Score 8.4/10

From Node 4 (AI in DevOps: 7.9):
├─ Node 4a: Predictive CI/CD → Score 8.1/10
└─ Node 4b: AI incident response → Score 7.8/10

From Node 2 (AI in testing: 7.8):
├─ Node 2a: Test generation and coverage → Score 8.2/10
└─ Node 2b: Visual/UI testing with AI → Score 7.6/10

From Node 7 (AI in security: 7.4):
├─ Node 7a: Vulnerability detection → Score 7.9/10
└─ Node 7b: Code review AI → Score 7.5/10

**10 new nodes created**
```

**Iteration 3: Selection and Aggregation**
```markdown
**Operation**: KeepBestN(8) then Aggregate(8)

Top 8 nodes (by score):
1. Node 5a: Automated refactoring (9.0)
2. Node 1a: Multi-file understanding (8.7)
3. Node 5: AI refactoring parent (8.5)
4. Node 1b: Personalization (8.3)
5. Node 5b: Code translation (8.4)
6. Node 2a: Test generation (8.2)
7. Node 1: Coding assistants parent (8.2)
8. Node 4a: Predictive CI/CD (8.1)

Aggregate into 3 thematic groups:

Group 1: Code Creation & Enhancement
└─ Nodes: [1, 1a, 1b, 5, 5a, 5b]
  → Synthesis: "AI-Augmented Development Workflow" (Score: 9.3)

Group 2: Quality & Testing
└─ Nodes: [2, 2a, 2b]
  → Synthesis: "AI-Driven Quality Assurance" (Score: 8.5)

Group 3: Operations & Security
└─ Nodes: [4, 4a, 4b, 7, 7a, 7b]
  → Synthesis: "AI in DevSecOps" (Score: 8.4)
```

**Iteration 4: Final Aggregation**
```markdown
**Operation**: Aggregate(3) thematic groups

Combine the 3 thematic syntheses into:
"AI in Software Development: 2025-2028 Strategic Outlook"

Final Score: 9.5/10

Output structure:
1. Executive Summary
2. Thematic Analysis (3 sections)
3. Implementation Timeline (2025-2028)
4. Recommendations by Role (Developer, Manager, CTO)
5. Risk Assessment
```

**Strategy Analysis**:
```
This was a BREADTH-FIRST approach:
- Explored 8 trends initially
- Pruned to 5 high-quality trends
- Explored each to 2nd level (10 sub-topics)
- Grouped thematically
- Created comprehensive landscape overview

Best for: Trend analysis, landscape surveys, "what's happening" topics
```

---

## Example 4: Problem-Solving Focus - Reducing Cloud Costs

### Research Topic
"Strategies for reducing AWS cloud costs for mid-sized SaaS companies"

### GoT Execution

**Iteration 1: Problem Decomposition**
```markdown
**Operation**: Generate(4) from root

Launched 4 parallel research agents:
├─ Agent 1: Quick wins (immediate cost savings) → Score 8.7/10
├─ Agent 2: Architecture optimization → Score 8.3/10
├─ Agent 3: Tooling and automation → Score 7.9/10
└─ Agent 4: Financial engineering (RI, SP, Savings Plans) → Score 8.5/10

**All nodes high quality - proceed differently on each**
```

**Iteration 2: Diversified Strategy**
```markdown
**Strategy**: Apply different operations based on node nature

Node 1 (Quick wins, 8.7) → Refine(1) immediately
└─ Quick wins are actionable now, polish for immediate use
└─ Improved: 8.7 → 9.1

Node 2 (Architecture, 8.3) → Generate(2) deeper
├─ Node 2a: Serverless migration patterns → Score 8.8/10
└─ Node 2b: Database optimization → Score 8.5/10

Node 3 (Tooling, 7.9) → Refine(1) for completeness
└─ Need specific tool recommendations
└─ Improved: 7.9 → 8.4

Node 4 (Financial, 8.5) → Generate(1) deeper
└─ Node 4a: Reserved instance optimization strategies → Score 8.9/10
```

**Iteration 3: Solution Synthesis**
```markdown
**Operation**: Aggregate(8) with SOLUTION focus

Input nodes: [1, 2, 2a, 2b, 3, 4, 4a]

Aggregation approach:
1. Group by time-to-implement:
   - Immediate (Node 1): Quick wins
   - Short-term (Nodes 3, 4): Tooling + financial engineering
   - Medium-term (Nodes 2, 2a, 2b): Architecture changes

2. For each group, create:
   - Action items
   - Expected savings (with sources)
   - Implementation effort
   - Risk level

Result: Prioritized action plan with ROI estimates
Score: 9.4/10
```

**Iteration 4: Final Polish**
```markdown
**Operation**: Refine(1) with focus on ACTIONABILITY

Enhancements:
- Added implementation checklist
- Created savings calculator framework
- Added vendor comparison tables
- Provided step-by-step migration guides

Final Output Score: 9.7/10
```

**Output Structure**:
```
Phase 1: Immediate Actions (Week 1-2, 10-20% savings)
Phase 2: Tooling & Optimization (Month 1-3, 15-30% savings)
Phase 3: Architecture Evolution (Quarter 1-2, 20-40% savings)

Each phase includes:
- Specific actions
- AWS services involved
- Estimated savings
- Implementation steps
- Risk mitigation
```

---

## Example 5: Comparative Analysis - Cloud Providers Comparison

### Research Topic
"Comparative analysis: AWS vs Azure vs Google Cloud for AI/ML workloads"

### GoT Execution

**Iteration 1: Parallel Provider Analysis**
```markdown
**Operation**: Generate(3) from root

Launched 3 parallel research agents:
├─ Agent 1: AWS AI/ML services → Score 8.4/10
├─ Agent 2: Azure AI/ML services → Score 8.2/10
└─ Agent 3: Google Cloud AI/ML services → Score 8.6/10

**All good, but Google Cloud slightly higher (native AI focus)**
```

**Iteration 2: Deepen Each Provider**
```markdown
**Operation**: Generate(2) from each provider node

AWS (Node 1, 8.4):
├─ Node 1a: SageMaker capabilities → Score 8.6/10
└─ Node 1b: AWS AI infrastructure (Trainium, Inferentia) → Score 8.8/10

Azure (Node 2, 8.2):
├─ Node 2a: Azure Machine Learning → Score 8.4/10
└─ Node 2b: Azure OpenAI Service integration → Score 8.9/10

Google Cloud (Node 3, 8.6):
├─ Node 3a: Vertex AI → Score 9.0/10
├─ Node 3b: TPUs and AI infrastructure → Score 9.2/10
```

**Iteration 3: Cross-Cutting Analysis**
```markdown
**Operation**: Generate(3) comparative dimensions

Launched 3 specialized comparison agents:
├─ Agent 4: Pricing comparison → Score 8.7/10
├─ Agent 5: Ease of use & developer experience → Score 8.3/10
└─ Agent 6: Enterprise features & security → Score 8.5/10
```

**Iteration 4: Synthesis & Recommendations**
```markdown
**Operation**: Aggregate(12)

Input: All 12 nodes (3 providers × 2 deep + 3 comparative)

Synthesis structure:
1. Detailed comparison by provider
2. Dimensional comparison (price, UX, security)
3. Use case mapping:
   - Best for research → Google Cloud
   - Best for enterprise → Azure
   - Best for breadth → AWS
4. Decision framework (flowchart)
5. Hybrid/multi-cloud strategies

Result Score: 9.5/10
```

**Final Output**:
```
Comprehensive comparison report with:
- Side-by-side feature matrix
- Total cost of ownership calculator
- Maturity assessment for each provider
- Recommendations by use case (training, inference, edge, etc.)
- Migration considerations
```

---

## GoT Operation Quick Reference

### Decision Tree: Which Operation to Use?

```
                 ┌─────────────────────┐
                 │  Starting Research  │
                 └──────────┬──────────┘
                            │
                   ┌────────┴────────┐
                   │  Generate(k)     │
                   │  k = 3-8         │
                   └────────┬────────┘
                            │
                 ┌──────────┴──────────┐
                 │  Score All Nodes    │
                 └──────────┬──────────┘
                            │
            ┌───────────────┴───────────────┐
            │                               │
    ┌───────┴────────┐            ┌────────┴───────┐
    │ Score ≥ 7.0    │            │ Score < 7.0    │
    │                │            │                │
    │ Diversify:     │            │ Prune:         │
    │ - High: Gen(2) │            │ KeepBestN(3)   │
    │ - Med: Refine  │            │                │
    └───────┬────────┘            └────────┬───────┘
            │                             │
            └──────────┬──────────────────┘
                       │
              ┌────────┴────────┐
              │ 2-3 Rounds of   │
              │ Generate/Score  │
              └────────┬────────┘
                       │
              ┌────────┴────────┐
              │  Aggregate(k)   │
              │ Combine findings│
              └────────┬────────┘
                       │
              ┌────────┴────────┐
              │  Refine(1)      │
              │  Final polish   │
              └────────┬────────┘
                       │
              ┌────────┴────────┐
              │  Final Output   │
              │  Score ≥ 8.5    │
              └─────────────────┘
```

---

## Key Takeaways

1. **No Universal Pattern**: Choose exploration strategy based on research goals
   - Depth-first: Critical topics, technical deep-dives
   - Breadth-first: Trend analysis, landscape surveys
   - Balanced: Most general research topics

2. **Score Guides Strategy**: Let scores determine next actions
   - High scores (8-10): Explore deeper
   - Medium scores (7-8): Refine or aggregate
   - Low scores (<7): Prune

3. **Aggregate at Right Time**: Not too early, not too late
   - Too early: Missing diverse perspectives
   - Too late: Graph becomes unmanageable
   - Sweet spot: After 2-3 generation rounds

4. **Refine Selectively**: Only refine what's already good
   - Threshold: Score ≥ 7.0
   - One refinement usually sufficient
   - Focus on citation quality and clarity

5. **Track Everything**: Maintain clear graph state
   - Nodes, scores, operations, decisions
   - Enables reproducible research
   - Helps explain research choices
