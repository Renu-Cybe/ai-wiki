# Wiki Schema

## Domain
LLM（大语言模型）+ AI 工具生态
- LLM：架构、训练、推理、微调、论文、 benchmark
- AI 工具：产品评测、工作流、平台、集成方案

## Conventions
- 文件名：小写、连字符、无空格（如 `transformer-architecture.md`）
- 每页以 YAML frontmatter 开头
- 使用 `[[wikilinks]]` 交叉链接，每页至少 2 个出站链接
- 更新页面时必须更新 `updated` 日期
- 新页面必须添加到 `index.md` 对应 section
- 所有操作追加到 `log.md`

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/articles/source-name.md]
---
```

## Tag Taxonomy

### LLM 域
| Tag | 用途 |
|-----|------|
| `model` | 具体模型名称（GPT-4、Claude 3、LLaMA 等） |
| `architecture` | 模型架构（Transformer、MoE、SSM 等） |
| `training` | 训练方法、数据、算力 |
| `fine-tuning` | 微调技术（LoRA、DPO、RLHF 等） |
| `inference` | 推理优化、量化、部署 |
| `benchmark` | 评测标准与结果 |
| `alignment` | 对齐、安全、RLHF |
| `paper` | 论文 |
| `dataset` | 数据集 |

### AI 工具域
| Tag | 用途 |
|-----|------|
| `product` | AI 产品、工具 |
| `workflow` | 工作流、自动化方案 |
| `评测` | 产品横评、对比 |
| `platform` | 平台、生态系统 |
| `integration` | 集成、API、插件 |

### 通用
| Tag | 用途 |
|-----|------|
| `person` | 人物 |
| `company` | 公司、机构 |
| `lab` | 实验室、研究组 |
| `timeline` | 时间线事件 |
| `controversy` | 争议、分歧 |
| `prediction` | 预测、展望 |
| `comparison` | 对比分析 |
| `summary` | 摘要/总结 |

## Page Thresholds
- **创建页面**：实体/概念在 2+ 来源中出现，或在一个来源中处于核心位置
- **追加到已有页面**：来源提及已覆盖的实体/概念
- **不创建页面**：一次性提及、细枝末节、超出领域范围
- **拆分页面**：超过 ~200 行时拆分，子主题用交叉链接
- **归档页面**：内容完全被取代时移至 `_archive/`，从 index.md 移除

## Entity Pages
每页一个实体，包含：
- 概述 / 是什么
- 关键事实与日期
- 与其他实体的关系（`[[wikilinks]]`）
- 来源引用

## Concept Pages
每页一个概念，包含：
- 定义 / 解释
- 当前认知状态
- 开放问题或争议
- 相关概念（`[[wikilinks]]`）

## Comparison Pages
包含：
- 对比对象与原因
- 对比维度（表格格式优先）
- 结论或综合判断
- 来源

## Update Policy
新信息与已有内容冲突时：
1. 看日期 — 新来源通常取代旧来源
2. 真正矛盾时，两方并存并注明日期和来源
3. frontmatter 标记：`contradictions: [page-name]`
4. 在 lint 报告中标记待用户审核

## 目录结构
```
ai-wiki/
├── SCHEMA.md
├── index.md
├── log.md
├── raw/
│   ├── articles/      # 网络文章、剪辑
│   ├── papers/        # 论文 PDF
│   ├── transcripts/   # 访谈、会议记录
│   └── assets/        # 图片、图表
├── entities/          # 实体页（人物、公司、产品、模型）
├── concepts/          # 概念页（架构、方法论、技术）
├── comparisons/       # 对比页
├── queries/           # 沉淀的问题答案
└── _archive/          # 归档页
```
