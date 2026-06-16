# Project: VLM Uncertainty and Visual Perturbation Attribution

## Goal

验证 hidden-state dynamics 方法是否能用于 VLM 输出不确定性检测，并进一步观察视觉扰动是否会导致输出可靠性下降。

## Research Question

当 VLM 面对原图和视觉扰动图时：

- 输出内容是否发生语义偏移？
- hidden-state confidence 是否下降？
- 不确定性是否可以归因到视觉输入退化？

## Current Method

- Model: Qwen3-VL-2B-Instruct
- Input: image + prompt
- Tasks:
  - short QA
  - one-sentence image description
- Perturbations:
  - gaussian blur
  - brightness dark
  - brightness bright
  - cutout
  - gaussian noise
  - pixelate
  - salt pepper
  - solarize
- Metrics:
  - LSR
  - tau
  - SSS
  - CCS
  - confidence
  - uncertainty

## Current Findings

- 简单单词 QA 对视觉扰动不敏感。
- 描述任务更容易暴露扰动导致的语义偏移。
- 原图 confidence 高于若干强扰动图。
- 当前多 token 聚合仍是 uniform average，尚未严格使用 attention aggregation。

## Next Steps

- [ ] 扩展到 20 张图。
- [ ] 加入传统 UQ 指标：entropy、PPL、MSP。
- [ ] 加入 API 裁判或人工评分。
- [ ] 计算正确/错误回答的 AUROC。
- [ ] 保存 attentions，实现论文中的 attention-guided aggregation。
- [ ] 输出一份小实验报告。

## Link

Local project:

`/home/robot/大模型不确定性评估/02_projects/Hidden-state-sampling-statistics`
