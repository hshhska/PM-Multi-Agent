# Owen — PM Multi-Agent Orchestrator

> A single-file AI skill that turns Claude Code into a **14-agent product team**, coordinated by Owen the orchestrator.

## What is Owen?

Owen is a prompt-based multi-agent framework for **product managers**. You give it a requirement, and Owen:

1. **Plans** — scans which agents are needed, drafts an execution plan with acceptance criteria
2. **Executes** — dispatches work to specialized agents (PRD writer, researcher, data analyst, etc.) with parallel collaboration
3. **Tests** — runs your acceptance criteria against the output, loops until all tests pass
4. **Delivers** — hands you a reviewed, multi-perspective deliverable for final sign-off

No code. No API keys. Just one `.md` file.

## The Team (14 Agents)

| Agent | Role | What they do |
|-------|------|-------------|
| **Owen** | Orchestrator | Plans, dispatches, tracks status, never produces content |
| **Nora** | Requirements Intake | Organizes messy input, identifies info gaps |
| **Parker** | PRD Writer | Writes structured PRDs with clear boundaries |
| **Sage** | Spec Agent | Bridges product → engineering, produces dev-ready specs |
| **Miles** | Planning | Work breakdown, RACI, milestone scheduling |
| **Vera** | Validation | Tests assumptions, walks through pipelines pre-launch |
| **Robin** | Research | Competitive analysis, market research with actionable conclusions |
| **Rachel** | Reporting | Executive-ready presentations and summaries |
| **Dale** | Data | SQL queries, metric analysis, data processing |
| **Dev** | Demo/Prototype | Quick HTML demos, API validation scripts |
| **Cleo** | Operations | Copy review, campaign strategy assessment |
| **Rex** | Quality Gate | Runs acceptance tests, enforces the Goal-Driven loop |
| **Tim** | Tech Perspective | Flags technical risks during production |
| **Uma** | User Perspective | Catches missing user scenarios |
| **Beth** | Business Perspective | Validates ROI and business alignment |

## Core Design: Goal-Driven Loop

Inspired by the Wiener-Shannon-Boyd dual agent system:

```
① PM defines goal + acceptance criteria (tests)
        ↓
② Agents execute collaboratively
        ↓
③ Rex runs criteria tests against output
        ↓
   ┌─ All ✅ → PM does final review
   └─ Any ❌ → Specific errors returned to agents → back to ②
```

**"Done" = passed all tests, not "finished doing stuff".**

Not every task needs this — Owen auto-detects when to use the full loop vs. direct execution.

## Install

### Claude Code CLI
```bash
# Global (works in all projects)
cp owen.md ~/.claude/commands/owen.md

# Project-level (works only in this project)
cp owen.md .claude/commands/owen.md
```

Then type `/owen` to activate.

## Usage

```
Owen, I need a PRD for a new notification system
Owen, status?
Owen, review the research report Robin produced
Owen, what's blocked?
```

## License

MIT — use it however you want.

---

# Owen — PM 多 Agent 协调员（中文说明）

> 一个单文件 AI Skill，让 Claude Code 变成一个 **14 人的 AI 产品团队**，由 Owen 统一调度。

## Owen 是什么？

Owen 是一个基于 Prompt 的多 Agent 协作框架，专为**产品经理**设计。你说一个需求，Owen 会：

1. **制定计划** — 扫描需要哪些角色参与，生成执行计划和验收标准
2. **并行执行** — 调度专业 Agent（PRD 写手、调研员、数据分析师等）同步协作
3. **验收测试** — 对产出物逐项跑验收标准，未通过自动返还修改，直到全部通过
4. **交付审查** — 把多视角审核过的交付物提交给你做最终确认

不需要写代码，不需要 API Key，只需要一个 `.md` 文件。

## 14 个 Agent 角色

| Agent | 职责 | 做什么 |
|-------|------|--------|
| **Owen** | 协调员 | 制定计划、分配任务、追踪状态，不直接产出内容 |
| **Nora** | 需求收口 | 整理零散输入，识别信息缺口 |
| **Parker** | PRD 写手 | 写结构清晰、边界明确的产品需求文档 |
| **Sage** | Spec 产研桥梁 | 把 PRD 转成研发可直接开工的 Spec 文档 |
| **Miles** | 规划 | 工作项拆解、RACI、里程碑排期 |
| **Vera** | 验证 | 走查链路、验证假设、识别技术风险 |
| **Robin** | 调研 | 竞品分析、市场调研，每个发现都映射到自身业务 |
| **Rachel** | 汇报 | 面向管理层的结论先行、数据支撑的汇报材料 |
| **Dale** | 数据 | SQL 取数、指标分析、数据处理 |
| **Dev** | 原型/Demo | 快速做 HTML Demo 或接口验证脚本 |
| **Cleo** | 运营 | 文案评审、活动策略评估 |
| **Rex** | 质量关卡 | 跑验收测试，驱动 Goal-Driven 循环 |
| **Tim** | 技术视角 | 同步标注技术风险 |
| **Uma** | 用户视角 | 补充用户场景、发现遗漏 |
| **Beth** | 商业视角 | 验证 ROI 和业务对齐 |

## 核心设计：Goal-Driven 循环

灵感来自 Wiener-Shannon-Boyd 双 Agent 系统：

```
① PM 定义目标（goal）+ 验收标准（criteria tests）
        ↓
② Agent 团队并行执行
        ↓
③ Rex 逐项跑验收测试
        ↓
   ┌─ 全部 ✅ → PM 做最终确认
   └─ 有 ❌  → 具体错误返还 Agent 修改 → 回到 ②
```

**"完成"= 通过了所有测试，不是"做完了就行"。**

不是所有任务都需要走完整循环 — Owen 会自动判断什么时候走 Goal-Driven 循环、什么时候直接执行。

## 安装

```bash
# 全局安装（所有项目生效）
cp owen.md ~/.claude/commands/owen.md

# 项目级安装（仅当前项目生效）
cp owen.md .claude/commands/owen.md
```

然后输入 `/owen` 激活。

## 使用示例

```
Owen，帮我写一个通知系统的 PRD
Owen，现在什么状态？
Owen，Robin 的调研报告帮我看一下
Owen，有什么阻塞？
```
