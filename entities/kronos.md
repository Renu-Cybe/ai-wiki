---
title: Kronos
created: 2026-04-13
updated: 2026-04-13
type: entity
tags: [model, architecture, financial, paper, open-source]
sources: [raw/articles/kronos-foundation-model-2026.md]
---

# Kronos

## Overview

金融市场 Foundation Model，将 K 线数据（K-line/candlestick）类比为"金融语言"。首个开源的金融 K 线预训练模型，被 AAAI 2026 接收。

## Key Facts

| | |
|--|--|
| GitHub | [shiyu-coder/Kronos](https://github.com/shiyu-coder/Kronos) |
| Paper | arXiv:2508.02739 |
| Stars | 16k+ |
| AAAI 2026 | ✅ 接收 |
| 训练数据 | 45 个全球交易所 |
| 架构 | Decoder-only Transformer + 专用 K 线 tokenizer |

## 核心技术

### 两阶段框架

1. **专用 Tokenizer**：将连续多维 OHLCV K 线数据量化成层级离散 token
2. **Autoregressive Transformer**：在离散 token 上做预训练

### 关键洞察

把金融市场的 K 线序列当作"语言"来处理——和 LLM 的 tokenization 思路一脉相承。

### 应用场景

- 股价预测
- 并行预测：8分钟完成千只股票实时分析
- 量化因子构建
- 金融市场模拟

## Model Zoo

提供多个规模的预训练模型，适合不同算力和应用场景。

## 与其他金融 AI 的关系

同类工作（[[financial-ai]]）：
- MarS (Jun Jie Li, 2024) — Large Market Model (LMM)，订单级生成模型

## See Also

[[foundation-model]] | [[transformer-architecture]] | [[financial-ai]]
