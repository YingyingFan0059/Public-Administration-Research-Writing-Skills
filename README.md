# Public Administration Research Writing Skills
# 公共管理研究写作技能包

Word-first academic writing skills for public administration, emergency management, and computational social science.

面向公共管理、应急管理与计算社会科学的 Word 优先学术写作技能包。

This repository provides a reusable local skill and a prompt library for drafting, revising, and diagnosing journal manuscripts. It is designed for section-aware writing in venues such as `Public Administration Review`, `American Political Science Review`, `Journal of Computational Social Science`, and related public policy, governance, and crisis-management journals.

本仓库提供一套可复用的本地 skill 与提示词库，用于论文草拟、润色、诊断与投稿前检查。整体设计强调“按章节写作”和“按研究设计守边界”，适用于 `Public Administration Review`、`American Political Science Review`、`Journal of Computational Social Science` 以及相关公共政策、治理与危机管理期刊。

## Overview / 项目简介

Generic AI writing prompts often miss the constraints that social-science manuscripts actually need:

- Word-first output instead of LaTeX-first conference formatting
- tighter control over causal language and research design meaning
- clearer boundaries for policy implications
- section-specific revision goals instead of one generic "polish" mode

通用写作 prompt 往往忽视社会科学论文真正需要的约束条件：

- 输出应适合直接粘贴到 Word，而不是默认面向 LaTeX 会议排版
- 必须更严格地控制因果语言、研究设计含义和变量关系
- 必须限制政策含义的过度外推
- 不同章节应该有不同的修改目标，而不是统一用一个“润色”模式

This repository addresses those needs with a local skill that routes by both `Task Mode` and `Section`.

本仓库用“`Task Mode + Section`”双轴路由来解决这些问题。

## What Is Included / 仓库内容

- `public-management-word-writing/SKILL.md`
  - Main skill entry point
  - Skill 主入口
- `public-management-word-writing/references/core-rules.md`
  - Shared guardrails for meaning, methods, and claim strength
  - 共享底层规则，约束原意、方法含义与结论强度
- `public-management-word-writing/references/task-modes.md`
  - Mode-specific behavior such as `polish`, `humanize`, `lit-review`, `design-check`, and `reviewer-diagnosis`
  - 按任务模式定义行为，如 `polish`、`humanize`、`lit-review`、`design-check`、`reviewer-diagnosis`
- `public-management-word-writing/references/section-guidance.md`
  - Section-specific priorities for `Introduction`, `Literature Review`, `Research Design`, `Results`, `Discussion`, and `Conclusion`
  - 针对 `Introduction`、`Literature Review`、`Research Design`、`Results`、`Discussion`、`Conclusion` 的章节规则
- `public-management-word-writing/references/prompt-library.md`
  - Copy-paste prompts for general LLM chat interfaces
  - 可直接复制到通用大模型界面的提示词模板
- `public-management-word-writing/agents/openai.yaml`
  - Metadata for skill discovery
  - skill 发现和调用所需的元数据

## Supported Sections / 支持章节

- `Introduction`
- `Literature Review`
- `Research Design`
- `Results`
- `Discussion`
- `Conclusion`

Each section has different revision priorities:

- `Introduction`: sharpen the puzzle, gap, and contribution
- `Literature Review`: organize by debate, mechanism, and positioning
- `Research Design`: protect variables, identification logic, assumptions, and sample definitions
- `Results`: separate reported findings from interpretation
- `Discussion`: interpret patterns and limits without overstating evidence
- `Conclusion`: restate contribution and implications with restraint

每个章节的修改重点不同：

- `Introduction`：突出研究问题、理论缺口与贡献
- `Literature Review`：按争论、机制和定位组织文献，而不是文献流水账
- `Research Design`：保护变量、识别策略、假设条件与样本定义
- `Results`：区分“结果报告”和“结果解释”
- `Discussion`：解释意义与边界，但不过度推断
- `Conclusion`：总结贡献和启示，但保持克制

## Supported Task Modes / 支持任务模式

- `polish`
- `humanize`
- `zh-to-en`
- `en-to-zh`
- `zh-to-zh`
- `lit-review`
- `design-check`
- `results-discussion`
- `reviewer-diagnosis`

Recommended defaults / 推荐默认搭配：

| Section | Recommended task mode |
| --- | --- |
| Introduction | `polish` |
| Literature Review | `lit-review` |
| Research Design | `polish` or `design-check` |
| Results | `results-discussion` |
| Discussion | `results-discussion` |
| Conclusion | `polish` |

## Install / 安装方式

### Option 1: Use Directly From This Repository
### 方式一：直接在本仓库中使用

Open `public-management-word-writing/SKILL.md` in a skill-aware agent workflow and point the agent to this repository path.

如果你的 agent 环境支持本地 skill，直接读取 `public-management-word-writing/SKILL.md` 并将本仓库路径提供给 agent 即可。

### Option 2: Install Globally For Codex
### 方式二：安装到 Codex 全局 skills 目录

Copy the `public-management-word-writing` folder into your local Codex skills directory:

将 `public-management-word-writing` 文件夹复制到本地 Codex skills 目录：

- macOS / Linux: `${CODEX_HOME:-$HOME/.codex}/skills/`
- Windows: `%USERPROFILE%\.codex\skills\` when `CODEX_HOME` is not set

After installation, invoke it as:

安装后可直接这样调用：

```text
Use $public-management-word-writing to revise this section for a public management journal.
```

## Quick Start / 快速开始

Use the skill with both `Task Mode` and `Section`.

建议同时提供 `Task Mode` 和 `Section`。

```text
Use $public-management-word-writing to revise this section for a public management journal.

Target Journal: Public Administration Review
Section: Results
Task Mode: results-discussion
Method / Design: two-way fixed effects DID
Must-Preserve Terms: administrative burden; response capacity; county-level panel
Text:
[paste the draft]
```

```text
Use $public-management-word-writing to review this section for research design weaknesses.

Target Journal: Public Administration Review
Section: Research Design
Task Mode: design-check
Method / Design: instrumental variables
Must-Preserve Terms: IV; treatment intensity; county fixed effects
Text:
[paste the draft]
```

```text
Use $public-management-word-writing to revise this section.

Target Journal: Journal of Computational Social Science
Section: Literature Review
Task Mode: lit-review
Method / Design: text-as-data + classifier
Must-Preserve Terms: crisis informatics; emergency governance
Text:
[paste the draft]
```

## Prompt Library / 提示词库

If you are working in a general chat interface rather than a local skill environment, use:

如果你使用的是普通聊天界面而不是本地 skill 环境，可以直接使用：

- `public-management-word-writing/references/prompt-library.md`

It includes / 其中包含：

- general English polishing / 通用英文润色
- de-AI rewriting / 去 AI 味改写
- Chinese-to-English drafting / 中文草稿转英文正文
- English-to-Chinese reading translation / 英文转中文精读翻译
- literature review restructuring / 文献综述重组
- research design diagnosis / 研究设计诊断
- results and discussion rewriting / 结果与讨论改写
- reviewer-style diagnosis / 审稿人视角诊断
- section-specific prompts / 各章节专用 prompt

## Design Principles / 设计原则

1. Preserve evidence boundaries. Do not turn association into causation.  
   保持证据边界，不把相关关系写成因果关系。
2. Preserve research design meaning. Keep variables, models, assumptions, and sample definitions stable.  
   保持研究设计含义，不随意改动变量、模型、假设与样本定义。
3. Preserve section function. A section should be revised according to its job in the paper.  
   保持章节功能，不同章节按各自任务修改。
4. Prefer simple academic prose. Use clear journal English rather than inflated AI-style language.  
   优先使用清晰、克制的学术语言，而不是夸张、机械的 AI 文风。
5. Stay Word-friendly. Output should paste cleanly into Word.  
   保持 Word 友好，输出应能直接粘贴使用。

## Scope / 适用范围

This repository is especially useful for:

本仓库尤其适合：

- journal article drafting / 期刊论文写作
- revise-and-resubmit cycles / 返修阶段修改
- section-by-section revision / 分章节精修
- pre-submission reviewer-style diagnosis / 投稿前审稿人视角检查
- public management and computational social science manuscripts that need strong control over inference language / 对推断语言控制要求较高的公共管理与计算社会科学论文

It is less suitable for:

本仓库不太适合：

- heavy LaTeX formatting workflows / 强 LaTeX 排版工作流
- bibliography management / 文献管理
- automated citation retrieval / 自动引文抓取
- quantitative verification that requires the original data and code / 需要原始数据与代码的定量核验

## Repository Structure / 仓库结构

```text
public-management-word-writing/
├─ SKILL.md
├─ agents/
│  └─ openai.yaml
└─ references/
   ├─ core-rules.md
   ├─ prompt-library.md
   ├─ section-guidance.md
   └─ task-modes.md
```

## License / 许可证

This project is released under the [MIT License](./LICENSE).

本项目采用 [MIT License](./LICENSE) 开源。
