---
name: idea-to-architecture
description: Turn an early-stage digital product, AI tool, automation, app, service, or Agent idea into one clear Mermaid system architecture diagram through lightweight requirements analysis. Use when a user says they have an idea, concept, or want to build something—including “我有一个想法/点子” or “我想做一个…”—and the conversation plausibly concerns a product or system. Do not use for ordinary life plans, pure business brainstorming, or requests that only ask for copy or code without system architecture.
---

# Idea to Architecture

把用户尚未成形的产品或系统想法，通过轻量对话收敛为一张可讨论、可修改的系统架构图。主要交付物是**一张 Mermaid 架构图**，不是代码、项目脚手架或实施方案。

## 工作边界

- 保持平台和模型供应商中立；除非用户已经指定，否则不要默认 OpenAI、Anthropic、云厂商或技术框架。
- 先判断想法是否真的需要 AI、Agent 或复杂编排。确定性功能应建模为普通系统组件，不要为了“智能感”把每个模块都画成 Agent。
- 不把缺失信息补成事实。区分已确认信息、合理假设和待确认项。
- 不要求用户填写完整 PRD，也不把一次灵感讨论变成冗长问卷。
- 交付架构图后停止在设计层；只有用户另行提出新请求时，才讨论代码、部署或项目创建。

## 分析想法

先用一句话复述：谁通过什么核心闭环获得什么结果。然后从对话中提取会影响架构的事实：

- 用户、入口与交互方式
- 主要输入、核心处理和最终输出
- 必需的外部系统、数据源或人工参与者
- 需要保存的数据与领域知识
- 时效、规模、隐私、权限和失败边界

只追问会改变一级模块、系统边界、数据归属、关键集成、安全策略或运行形态的问题。每轮最多问 3 个，优先问当前信息增益最高的问题。如果用户希望先看图，采用保守且可逆的假设，并在图中标注 `[待确认]`。

当用户说“我有一个想法”但尚未说明内容时，先邀请其用一两句话描述想做什么。若内容显然不是数字产品或系统，正常回应用户，不要强行产出架构图。

## 选择架构

信息足以确定主要边界后，读取 [references/architecture-patterns.md](references/architecture-patterns.md)，选择最小适用的分层和组件。不要为了填满模板添加无必要的层或组件。

重点检查：

1. 哪些能力是确定性系统组件，哪些才需要智能模块。
2. 数据从哪里进入、由谁处理、保存在哪里、如何形成结果。
3. 哪些外部调用会产生副作用，是否需要审批、审计或人工兜底。
4. 哪些需求确实需要记忆、任务、异步、调度、并行或目标判断。

## 绘制一张图

使用 Mermaid `flowchart`，根据阅读方向选择 `TB` 或 `LR`：

- 只交付一张主架构图，不拆成多张局部图。
- 用子图表达真实存在的层或系统边界，通常不超过 7 个。
- 节点名称使用用户能理解的业务语言；必要时在第二行补充技术角色。
- 明确外部参与者、产品边界、核心能力、外部服务、数据与运行支撑。
- 用带文字的箭头标出主输入、关键调用、数据写入和最终输出。
- 未确认但必须画出的节点或连接标注 `[待确认]`。
- 安全与可观测性是横切能力；只有确有需要时才画出，并连接到实际受影响的组件。
- 保持 Mermaid 语法可渲染，避免在节点中堆放段落或大量实现细节。

## 交付格式

使用用户的语言，按以下顺序输出：

1. **我理解的想法**：一句话。
2. **架构假设**：仅列出影响图形的假设，最多 5 条；没有则省略。
3. **架构图**：恰好一个 Mermaid 代码块。
4. **关键流转**：用 3–6 个短步骤解释主链路。
5. **待确认**：只列出可能导致架构重画的问题；没有则省略。

图应当是当前讨论的可修改版本，而不是伪装成已验证的最终设计。用户补充或纠正信息后，更新同一张主图。
