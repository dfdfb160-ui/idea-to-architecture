# Idea to Architecture｜想法架构图

把一个尚未成形的数字产品或系统想法，通过轻量需求分析收敛为一张清晰、可讨论、可继续修改的 Mermaid 系统架构图。

## 这个 Skill 做什么

- 识别用户、入口、核心闭环、数据、外部系统和运行边界。
- 只追问会实际改变架构的问题，避免把讨论变成完整 PRD 问卷。
- 区分普通确定性功能、AI 能力和真正需要自主决策的 Agent。
- 选择满足当前需求的最小架构，不为了完整感堆叠无必要组件。
- 最终交付一张 Mermaid 主架构图，并解释关键流转和待确认事项。

这个 Skill 聚焦“从想法到架构图”。它不会自动进入代码实现、项目搭建或部署阶段。

## 自动触发范围

当用户表达自己有一个数字产品、App、AI 工具、自动化、服务或 Agent 想法，并希望进一步分析时，可以自动调用本 Skill。

普通生活安排、纯商业创意讨论，以及只要求文案或代码而不需要系统架构的请求，不属于它的处理范围。

## 文件结构

```text
idea-to-architecture/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── architecture-patterns.md
```

## 安装

将整个 `idea-to-architecture` 文件夹放入个人 Codex Skills 目录，并重新加载 Codex。安装后既可以自动触发，也可以通过 `$idea-to-architecture` 显式调用。

## 版权说明

本仓库公开供查看，但未授予开源许可证。除 `THIRD_PARTY_NOTICES.md` 中单独说明的第三方材料外，本仓库原创内容保留所有权利。未经仓库所有者明确许可，不得复制、修改、分发或用于再发布。

第三方材料及其许可声明见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
