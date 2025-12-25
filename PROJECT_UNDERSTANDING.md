# Claude Code Deep Research Agent - 项目理解文档

## 1. 项目概述

这是一个基于 **Claude Code** 的深度研究框架，旨在实现类似 OpenAI Deep Research 和 Google Gemini Deep Research 的功能。项目的核心理念是利用 Anthropic Claude Code 的能力，通过系统化的方法论和多智能体协作，完成复杂的、多步骤的深度研究任务。

### 1.1 项目定位
- **名称**: Claude Deep Research Agent
- **目标**: 使用 Claude Code 实现高质量、带引用的深度研究报告
- **核心理念**: 通过 Graph of Thoughts (GoT) 框架和 7 阶段深度研究流程，超越传统的单次查询模式

### 1.2 当前工作流程

```
[用户原始问题]
       ↓
[ChatGPT (o3/o3-pro)] - 问题细化和结构化
       ↓
[Claude Code (opus)] - 执行深度研究
       ↓
[带引用的综合研究报告]
```

**关键问题**: 目前依赖 ChatGPT 来预处理问题，用户希望能够完全用 Claude Code 实现。

---

## 2. 核心文件分析

### 2.1 README.md
**作用**: 项目说明和快速开始指南

**核心内容**:
- 解释项目存在的理由：LLM 在单次查询上表现良好，但在需要迭代查询、来源验证和引用的复杂多步骤研究上存在困难
- 定义了仓库结构：
  - `CLAUDE.md` - Claude Code 的主指令文件
  - `Claude2.md` - 更深度的版本，更接近 Graph of Thoughts 模式
  - `Deep Research Question Generator System Prompt.md` - ChatGPT 系统提示词
  - `deepresearchprocess.md` - 7 阶段深度研究流程基础文档
  - `.template_mcp.json` - 可选的 MCP 服务器配置

### 2.2 CLAUDE.md (主指令文件)
**作用**: Claude Code 的核心操作指南

**核心架构**:

#### A. 7 阶段深度研究流程
1. **Phase 1: Question Scoping** - 问题范围界定
2. **Phase 2: Retrieval Planning** - 检索计划
3. **Phase 3: Iterative Querying** - 迭代查询
4. **Phase 4: Source Triangulation** - 来源三角验证
5. **Phase 5: Knowledge Synthesis** - 知识综合
6. **Phase 6: Quality Assurance** - 质量保证
7. **Phase 7: Output & Packaging** - 输出和打包

#### B. 多智能体研究策略
```
Phase 2: 检索规划
├── 主题分解智能体
└── 并行研究智能体 (每个子主题一个)

Phase 3: 迭代查询
├── 网络研究智能体 (3-5个) - 当前信息、趋势、新闻
├── 学术/技术智能体 (1-2个) - 研究论文、技术规范
└── 交叉引用智能体 (1个) - 事实核查和验证
```

#### C. 工具使用协议
- **WebSearch**: 通用网络搜索
- **WebFetch**: 提取特定 URL 内容
- **Read/Write**: 管理研究文档
- **Task**: 生成自主智能体
- **TodoWrite**: 跟踪研究进度
- **MCP 服务器**:
  - `mcp__filesystem__`: 文件系统操作
  - `mcp__puppeteer__`: 浏览器自动化（动态网页内容）

### 2.3 Claude2.md
**作用**: 更深度的 GoT (Graph of Thoughts) 实现版本

**关键区别**:
- 更完整的 Graph of Thoughts 实现
- 使用 Task 智能体模拟 GoT 操作
- 无需外部 Python 设置
- 自动执行图状态维护

**核心概念**:
```
图结构:
- 节点 (Nodes) = 研究发现
- 边 (Edges) = 依赖关系
- 分数 (Scores) = 质量 (0-10)
- 前沿 (Frontier) = 可扩展的活跃节点

转换操作:
- Generate(k): 从父节点创建 k 个新想法
- Aggregate(k): 将 k 个想法合并为一个更强的想法
- Refine(1): 改进想法而不添加新内容
- Score: 评估想法质量
- KeepBestN(n): 每层保留最佳 n 个节点
```

### 2.4 Deep Research Question Generator System Prompt.md
**作用**: 用于 ChatGPT 的系统提示词，将用户原始问题转换为结构化提示词

**核心功能**:
- 问澄清问题（范围、格式、约束、背景）
- 生成结构化的深度研究提示词
- 输出 OpenAI 和 Google Gemini 两种格式

**示例结构**:
```
### TASK - 任务描述
### CONTEXT/BACKGROUND - 背景
### SPECIFIC QUESTIONS OR SUBTASKS - 具体问题/子任务
### KEYWORDS - 关键词
### CONSTRAINTS - 约束（时间、地理、来源类型）
### OUTPUT FORMAT - 输出格式
### FINAL INSTRUCTIONS - 最终指令
```

---

## 3. 研究方法论

### 3.1 Graph of Thoughts (GoT) 框架

**来源**: 基于 [SPCL, ETH Zürich](https://github.com/spcl/graph-of-thoughts) 的研究

**核心优势**:
1. **并行处理**: 多个研究路径可同时探索
2. **质量优化**: 通过评分和修剪来优化信息质量
3. **回溯能力**: 可放弃较差的研究路径
4. **动态探索**: 根据中间结果调整研究策略

**执行流程示例**:
```
用户: "Deep research CRISPR gene editing safety"

迭代 1: 初始化和探索
  - Controller 创建根节点
  - Generate(3) 部署 3 个并行智能体:
    * 当前证据和成功率
    * 安全顾虑和限制
    * 未来影响和法规
  - 结果: 3 个想法，分数 (6.8, 8.2, 7.5)

迭代 2: 深化最佳路径
  - n3 (8.2): 高分 → Generate(3) 更深探索
  - n2 (7.5): 中等 → Generate(2)
  - n4 (6.8): 低分 → Refine(1) 改进

迭代 3: 聚合强分支
  - Aggregate(3) 合并最佳想法

迭代 4: 最终打磨
  - Refine(1) 增强清晰度和完整性
  - 最终想法分数: 9.5
```

### 3.2 引用要求

**每个事实性声明必须包含**:
1. 作者/组织
2. 发布日期
3. 来源标题
4. URL/DOI
5. 页码（如适用）

**来源质量评级**:
- **A**: 同行评议的 RCT、系统评价、荟萃分析
- **B**: 队列研究、病例对照研究、临床指南
- **C**: 专家意见、病例报告、机制研究
- **D**: 初步研究、预印本、会议摘要
- **E**: 轶事、理论或推测

### 3.3 防幻觉策略

1. **Chain-of-Verification (CoVe)**:
   - 生成初始研究发现
   - 为每个声明创建验证问题
   - 搜索证据回答验证问题
   - 基于验证结果修正发现

2. **ReAct 模式** (Reason + Act):
   - Reason: 分析需要什么信息
   - Act: 执行搜索或检索操作
   - Observe: 处理结果
   - Repeat: 直到收集足够证据

3. **Human-in-the-Loop 检查点**:
   - 规划后：批准研究策略
   - 验证期间：专家审查技术声明
   - 最终确定前：利益相关者签字

---

## 4. 输出结构

### 4.1 标准文件夹结构
```
RESEARCH/
└── [topic_name]/
    ├── README.md (概述和导航)
    ├── executive_summary.md (1-2 页摘要)
    ├── full_report.md (综合发现)
    ├── data/
    │   ├── raw_data.csv
    │   ├── processed_data.json
    │   └── statistics_summary.md
    ├── visuals/
    │   ├── charts/
    │   ├── graphs/
    │   └── infographics/
    ├── sources/
    │   ├── bibliography.md
    │   ├── source_summaries.md
    │   └── screenshots/
    ├── research_notes/
    │   ├── agent_1_findings.md
    │   ├── agent_2_findings.md
    │   └── synthesis_notes.md
    └── appendices/
        ├── methodology.md
        ├── limitations.md
        └── future_research.md
```

### 4.2 示例输出分析

**主题**: AI Content Detection Field Briefing
**规模**: >50,000 词
**输出时间**: 需要多个智能体并行工作

**主要部分**:
1. Executive Summary (≤1,500 词)
2. Main Report (分为编号的部分和子部分)
3. End-User Quick-Reference Toolkit (清单、备忘单)
4. Developer Solution Blueprints (架构图、伪代码)
5. Roadmap Tables (短期/中期)
6. Appendices (详细基准、数据表、术语表)

---

## 5. 用户需求分析

### 5.1 当前架构的问题

**依赖 ChatGPT 的问题**:
1. 需要两个独立的工具/账户
2. ChatGPT 限制和成本
3. 工作流程不连贯
4. 无法充分利用 Claude Code 的原生能力

### 5.2 期望的改进

**用户目标**:
```
[用户原始问题]
       ↓
[Claude Code Agent] - 问题细化 + 深度研究
       ↓
[带引用的综合研究报告]
```

**核心需求**:
1. **利用 Claude Code Skills**: 创建可重用的研究技能
2. **利用 Claude Code Commands**: 创建便捷的斜杠命令
3. **消除 GPT 依赖**: 完全用 Claude Code 实现问题细化
4. **自动化流程**: 从原始问题到最终报告的一键执行

---

## 6. Claude Code 原生功能分析

### 6.1 Skills 系统

**定义**: Skills 是可重用的能力，可以被 Claude Code 动态加载和执行。

**在此项目中的应用场景**:
```
Skills/
├── question-refiner/        # 问题细化技能
│   ├── skill.json
│   ├── instructions.md
│   └── examples.md
├── researcher/              # 研究执行技能
│   ├── skill.json
│   ├── got-controller.md
│   ├── web-search.md
│   └── citation-formatter.md
├── synthesizer/             # 综合技能
│   ├── skill.json
│   └── instructions.md
└── validator/               # 验证技能
    ├── skill.json
    └── verification-checklist.md
```

### 6.2 Commands 系统

**定义**: Commands 是用户可以调用的快捷操作。

**在此项目中的应用场景**:
```
Commands/
├── deep-research            # /deep-research [topic]
├── refine-question          # /refine-question [raw question]
├── plan-research            # /plan-research [topic]
├── execute-research         # /execute-research [plan]
└── validate-facts           # /validate-facts [findings]
```

### 6.3 MCP (Model Context Protocol) 服务器

**可用的 MCP 功能**:
1. **mcp__web_reader__webReader**: 网页内容提取（已配置）
2. **mcp__4_5v_mcp__analyze_image**: 图像分析（已配置）
3. **潜在的其他 MCP**:
   - Puppeteer (浏览器自动化)
   - Filesystem (文件系统操作)

---

## 7. 实现方案建议

### 7.1 架构设计

```
┌─────────────────────────────────────────────────────────────┐
│                    Claude Code Agent                        │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Command: /deep-research [topic]                    │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Skill: question-refiner                           │    │
│  │  - 问澄清问题                                       │    │
│  │  - 生成结构化研究提示词                            │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Skill: research-planner (GoT Controller)          │    │
│  │  - 分解主题为子主题                                │    │
│  │  - 创建研究图                                      │    │
│  │  - 部署并行研究智能体                              │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Multi-Agent Execution                             │    │
│  │  ├─ Web Research Agents (3-5)                     │    │
│  │  ├─ Academic/Technical Agents (1-2)                │    │
│  │  └─ Cross-Reference Agent (1)                     │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Skill: synthesizer                                │    │
│  │  - 聚合发现                                        │    │
│  │  - 解决矛盾                                        │    │
│  │  - 创建连贯叙述                                    │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Skill: validator                                  │    │
│  │  - 事实核查                                        │    │
│  │  - 引用验证                                        │    │
│  │  - 质量评分                                        │    │
│  └──────────────────┬──────────────────────────────────┘    │
│                     ↓                                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Output Generation                                 │    │
│  │  - Executive Summary                               │    │
│  │  - Full Report                                     │    │
│  │  - Bibliography                                    │    │
│  │  - Appendices                                       │    │
│  └─────────────────────────────────────────────────────┘    │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

### 7.2 技术实现要点

#### A. Question Refiner Skill
**功能**: 替代 ChatGPT 的问题细化

**实现方式**:
```
输入: 用户原始问题
处理:
  1. 识别模糊点
  2. 生成澄清问题
  3. 等待用户回答
  4. 生成结构化研究提示词
输出: 结构化研究任务
```

#### B. GoT Controller Skill
**功能**: 管理研究图状态

**实现方式**:
```
使用 Task 工具创建子智能体:
- Controller Agent: 维护图状态
- Generate Agents: 探索研究路径
- Aggregate Agent: 合并发现
- Refine Agent: 改进内容
- Score Agent: 评估质量
```

#### C. Citation Manager Skill
**功能**: 确保所有声明都有引用

**实现方式**:
```
自动检查:
- 每个事实性声明是否有来源
- 引用格式是否正确
- 来源是否可靠
- 是否存在矛盾
```

### 7.3 文件结构建议

```
claude-code-deep-research/
├── .claude/
│   ├── skills/
│   │   ├── question-refiner/
│   │   │   ├── skill.json
│   │   │   ├── instructions.md
│   │   │   └── examples.md
│   │   ├── research-executor/
│   │   │   ├── skill.json
│   │   │   ├── phases.md
│   │   │   └── agent-templates.md
│   │   ├── got-controller/
│   │   │   ├── skill.json
│   │   │   ├── graph-operations.md
│   │   │   └── scoring.md
│   │   ├── synthesizer/
│   │   │   ├── skill.json
│   │   │   └── instructions.md
│   │   └── citation-validator/
│   │       ├── skill.json
│   │       └── checklist.md
│   └── commands/
│       ├── deep-research/
│       │   └── command.json
│       ├── refine-question/
│       │   └── command.json
│       └── plan-research/
│           └── command.json
├── CLAUDE.md                   # 主文档（保留）
├── CLAUDE2.md                  # GoT 版本（保留）
├── deepresearchprocess.md      # 流程文档（保留）
├── PROJECT_UNDERSTANDING.md    # 本文档
├── IMPLEMENTATION_GUIDE.md     # 待创建：实现指南
└── examples/                   # 示例输出（保留）
```

### 7.4 Skill JSON 结构示例

**question-refiner/skill.json**:
```json
{
  "name": "question-refiner",
  "description": "将原始研究问题细化为结构化的深度研究任务，通过澄清问题确保研究目标清晰",
  "instructions": "读取 instructions.md 获取详细指令",
  "examples": "读取 examples.md 查看示例"
}
```

**deep-research/command.json**:
```json
{
  "name": "deep-research",
  "description": "对给定主题执行完整的深度研究流程",
  "usage": "/deep-research [研究主题]",
  "skill": "research-executor"
}
```

---

## 8. 关键技术挑战和解决方案

### 8.1 挑战 1: Context 限制
**问题**: 深度研究可能生成超过 200K tokens 的内容

**解决方案**:
- 分模块生成（每个部分独立文件）
- 使用摘要和引用链接
- 渐进式综合（分层聚合）

### 8.2 挑战 2: 引用准确性
**问题**: 幻觉引用或格式错误

**解决方案**:
- Chain-of-Verification 验证循环
- 强制每个声明都有来源
- 使用多个来源验证关键声明

### 8.3 挑战 3: 研究质量一致性
**问题**: 不同智能体输出质量不均

**解决方案**:
- 标准化智能体提示词模板
- 评分和修剪低质量分支
- 聚合多个来源

### 8.4 挑战 4: 用户交互
**问题**: 如何处理需要用户澄清的情况

**解决方案**:
- 使用 AskUserQuestion 工具
- 分阶段执行（规划 → 用户确认 → 执行）
- 保存中间状态供用户审查

---

## 9. 实施路线图

### Phase 1: 基础 Skills (1-2 周)
- [ ] 创建 question-refiner skill
- [ ] 创建 research-executor skill
- [ ] 测试基础工作流程

### Phase 2: GoT 集成 (2-3 周)
- [ ] 创建 got-controller skill
- [ ] 实现图操作（Generate, Aggregate, Refine, Score）
- [ ] 创建智能体模板系统

### Phase 3: Commands 和 UI (1 周)
- [ ] 创建 /deep-research command
- [ ] 创建 /refine-question command
- [ ] 优化用户交互流程

### Phase 4: 质量保证 (1-2 周)
- [ ] 创建 citation-validator skill
- [ ] 实现自动化质量检查
- [ ] 添加人工审查检查点

### Phase 5: 测试和优化 (1-2 周)
- [ ] 端到端测试
- [ ] 性能优化
- [ ] 文档完善

---

## 10. 与现有代码的兼容性

### 10.1 保留的文档
- `CLAUDE.md` - 作为参考文档
- `Claude2.md` - GoT 实现参考
- `deepresearchprocess.md` - 流程参考
- `examples/` - 输出示例

### 10.2 新增的文档
- `PROJECT_UNDERSTANDING.md` - 本文档
- `IMPLEMENTATION_GUIDE.md` - 实施指南
- `.claude/skills/` - Skills 定义
- `.claude/commands/` - Commands 定义

### 10.3 迁移策略
1. **渐进式迁移**: 先实现基础功能，再添加高级特性
2. **向后兼容**: 保留原有的手动工作流程
3. **A/B 测试**: 比较新旧方法的输出质量

---

## 11. 成功指标

### 11.1 功能性指标
- [ ] 能够完全用 Claude Code 完成深度研究（无需 ChatGPT）
- [ ] 输出质量达到或超过示例标准
- [ ] 所有声明都有正确的引用
- [ ] 研究时间 < 30 分钟（对于 50,000 词报告）

### 11.2 用户体验指标
- [ ] 单命令执行: `/deep-research [topic]`
- [ ] 交互式澄清: 自动询问必要细节
- [ ] 进度可见: TodoWrite 跟踪进度
- [ ] 可中断和恢复: 保存中间状态

### 11.3 技术指标
- [ ] Context 使用效率 > 80%
- [ ] 智能体并行度 ≥ 5
- [ ] 引用准确率 > 95%
- [ ] 幻觉率 < 5%

---

## 12. 总结和下一步

### 12.1 核心价值
这个项目展示了一种使用 Claude Code 实现高质量深度研究的方法论。通过系统化的 7 阶段流程、Graph of Thoughts 框架和多智能体协作，可以生成超越传统单次查询的综合研究报告。

### 12.2 改进方向
将 ChatGPT 依赖替换为 Claude Code 原生 Skills 和 Commands，实现：
1. 更流畅的工作流程
2. 更好的集成和自动化
3. 更低的复杂度和成本
4. 更充分利用 Claude Code 的能力

### 12.3 立即行动
1. 审查本理解文档的准确性
2. 确认优先级和范围
3. 开始实施 Phase 1: 基础 Skills
4. 迭代开发和测试

---

*文档版本: 1.0*
*最后更新: 2025-12-25*
*作者: Claude (Sonnet 4.5)*
