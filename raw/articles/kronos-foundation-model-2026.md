# Kronos — A Foundation Model for the Language of Financial Markets

**URL**: https://github.com/shiyu-coder/Kronos
**Paper**: https://arxiv.org/abs/2508.02739
**Captured**: 2026-04-13

## 基本信息
- 16k+ stars，2.4k forks
- 第一作者：Yu Shi（清华大学）
- 团队：Tsinghua / 清华大学
- 接收：AAAI 2026

## 核心贡献
首个开源金融市场 K 线（K-line/candlestick）Foundation Model。

核心思路：
1. **专用 Tokenizer**：将 OHLCV K 线数据量化为层级离散 token
2. **Autoregressive Transformer**：在离散 token 上预训练

训练数据：45 个全球交易所

## 技术亮点
- 把金融数据当作"语言"来处理，类比 LLM 的 tokenization
- Model Zoo：多个规模的预训练模型
- 支持微调（finetune 脚本已开源）
- WebUI 演示（BTC/USDT 24小时预测）
- 并行预测框架：8分钟完成千只股票实时分析

## 用途
- 股价预测
- 量化交易分析
- 金融市场模拟
