---
title: Hermes Agent
created: 2026-04-13
updated: 2026-04-13
type: entity
tags: [product, open-source, agent, nous-research]
sources: [raw/articles/nousresearch-hermes-agent-2026.md]
---

# Hermes Agent

## Overview

开源 autonomous AI agent 框架，由 [Nous Research](https://nousresearch.com) 开发。版本 v0.8.0（2026年4月8日）。

**特点：唯一内置自学习循环的 agent** — 从经验中自动生成 skill、持久化记忆、跨 session 搜索、用户建模。

## Key Facts

| | |
|--|--|
| 当前版本 | v0.8.0 |
| 发布日期 | 2026-04-08 |
| GitHub | [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) |
| Stars | 72k+ |
| License | MIT |
| 语言 | Python |
| 安装量 | 8.5k+ forks |

## Core Features

### 自学习循环（Self-Improving）
- 从复杂任务中**自动生成 skill**
- 使用过程中**自我改进**
- Agent curated memory + 定期提醒持久化
- FTS5 session 搜索 + LLM 摘要压缩
- 用户建模 via Honcho dialectic

### 多平台消息
一个进程支持：Telegram、Discord、Slack、WhatsApp、Signal、Email。

### 定时任务
内置 cron，支持投递到任意平台。

### 六大执行后端
Local、Docker、SSH、Daytona（serverless 休眠）、Singularity（HPC）、Modal（serverless GPU）。

### 技能系统
Procedural memory + [AgentSkills.io](https://agentskills.io) 开放标准。技能可从经验中自动生成和进化。

## LLM Provider 支持

`hermes model [provider:model]` 切换，无需改代码：

- Nous Portal（推荐）
- OpenRouter（200+ 模型）
- z.ai/GLM
- Kimi/Moonshot
- **MiniMax**
- OpenAI
- Anthropic
- 自定义端点

## 与先生 Hermes 的关系

服务器运行的 Hermes（athena/erduo 那套框架）基于 hermes-agent 构建。先生的版本：
- 定制了 SOUL.md（雅典娜人格）
- 集成飞书平台
- 迁移自 OpenClaw
- 使用 MiniMax-M2.7 作为默认模型

## 框架架构

```
hermes-agent/
├── run_agent.py          # AIAgent 核心对话循环
├── model_tools.py        # 工具编排、函数调用处理
├── hermes_state.py       # SQLite + FTS5 session 存储
├── agent/                # Agent 内部模块
│   ├── prompt_builder.py
│   ├── context_compressor.py
│   └── models_dev.py
├── hermes_cli/           # CLI 子命令
├── gateway/              # 消息平台网关
│   └── platforms/        # Telegram/Discord/Slack...
├── tools/                # 工具实现
│   ├── registry.py
│   ├── terminal_tool.py
│   ├── web_tools.py
│   └── delegate_tool.py
└── cron/                  # 定时任务调度
```

## 技术亮点

- **FTS5 搜索**：跨 session 语义检索
- **Context 压缩**：自动上下文缩减
- **Prompt Caching**：Anthropic 提示缓存
- **轨迹保存**：可导出对话轨迹用于训练

## 文档

- 官网：hermes-agent.nousresearch.com/docs
- Skills Hub：agentskills.io

## See Also

[[Nous Research]] | [[autonomous-agent]] | [[skill-system]]
