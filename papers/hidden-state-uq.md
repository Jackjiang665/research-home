# Sampling-Free UQ via Hidden State Dynamics

## Basic Info

- Title: Sampling-Free Uncertainty Quantification via Hidden State Dynamics in Language Models
- Topic: uncertainty quantification, hidden states, LLM reliability
- Local project: `Hidden-state-sampling-statistics`

## Core Idea

模型生成 token 时，各层 hidden state 会逐步向最终语义表示收敛。确定性高的 token 往往更早稳定、更快收敛；不确定 token 则在早期波动更大、后期收敛更慢或不稳定。

## Metrics

### LSR

Layer-wise Semantic Relevance Score:

每一层 hidden state 与最终层 hidden state 的余弦相似度。

### SSS

Semantic Stability Score:

拐点之前 LSR 轨迹的稳定性，通常写作 `1 - variance`。越高表示早期语义越稳定。

### CCS

Convergence Confidence Score:

拐点之后 LSR 轨迹的平均收敛斜率。越高表示后期越明确地向最终表示收敛。

### Sequence Score

论文使用 attention-guided aggregation 聚合多个 token 的分数。

当前实现阶段：

- 单 token QA：sequence score 等于 token score。
- 多 token 描述：暂时使用 uniform average。
- 后续严格复现需要保存 final-layer attentions。

## Connection to My Research

当前我将这个方法迁移到 VLM 场景中，观察视觉扰动是否会影响 VLM 输出的 hidden-state confidence。

目标不是只算一个分数，而是把它发展为机器人任务执行前的感知可靠性判断模块。

## Current Observation

在 `img_001.jpg` 上：

- 单 token QA `dog` 对扰动不敏感。
- 短描述任务更能体现视觉扰动影响。
- 原图 confidence 最高，solarize、gaussian blur、pixelate 等扰动更低。

## Next Questions

- 这个指标能否区分正确/错误回答？
- 和 entropy、PPL 相比是否更有效？
- 对不同扰动类型是否有可分性？
- 如何引入 attention aggregation？
- 如何将分数转化为机器人行为策略？
