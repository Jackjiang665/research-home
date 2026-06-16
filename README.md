# Jiang Hanchen Research Home

这是我的个人研究主页、工作台和成长记录。它不属于某一个具体项目，而是用于长期沉淀我的研究方向、学习路线、论文笔记、实验记录和阶段复盘。

## About Me

我本科就读于中国地质大学（北京）信息工程学院，专业为电气工程及其自动化，将于 2026 年 9 月进入北京邮电大学开始研究生阶段学习。

本科期间，我长期参与机器人竞赛与工程实践，主要经历包括智能搬运小车、轮式机器人、农业植保机器人、微型无人机等项目，并担任机器人队队长。这些经历让我对真实机器人系统中的感知、决策、控制、调试和工程落地有了直接认识。

我当前的长期兴趣是：

> 面向真实机器人任务的多模态感知、决策可靠性与自适应恢复。

更具体地说，我希望研究机器人在开放环境中如何看懂任务、判断自身输出是否可靠、定位失败来源，并在不确定时采取重拍、换视角、请求确认或调整策略等恢复动作。

## Current Focus

当前阶段，我以 VLM 输出不确定性研究作为切入点，训练自己理解多模态模型、hidden state、uncertainty quantification 和实验闭环。

当前小课题：

> 基于隐状态动态的 VLM 输出不确定性检测与视觉扰动溯源。

核心问题：

- VLM 在原图和视觉扰动图上的输出可靠性是否会发生变化？
- hidden state 动态指标，如 LSR、SSS、CCS，能否反映这种变化？
- 当 VLM 输出不可靠时，是否可以进一步判断不确定性主要来自视觉输入退化？
- 这些指标未来能否作为机器人执行前的感知可靠性监控模块？

## Long-Term Directions

我目前保留几条长期候选方向，后续会根据研究生阶段导师项目、实验平台和自身积累逐步收敛。

### 1. Embodied Robot Task Systems

让机器人真正完成任务，而不是只在离线数据上评估模型。

可能方向：

- 机械臂桌面操作系统
- 机器狗巡检任务
- 无人机视觉搜索任务
- VLM/VLA + 技能库 + 控制器的系统集成
- 语言指令到机器人动作的任务执行

### 2. Robot Self-Diagnosis and Adaptive Recovery

让机器人知道自己什么时候可能做错、为什么做错，以及下一步应该如何补救。

可能方向：

- failure detection
- failure attribution
- active perception
- uncertainty-aware robot behavior
- 失败后重拍、换视角、请求确认、重新规划

### 3. Multimodal Reliability for Embodied AI

研究多模态模型在具身系统中的可靠性，而不是只看模型 benchmark 分数。

可能方向：

- VLM 输出不确定性
- VLM 幻觉检测
- 视觉扰动和问题歧义溯源
- 具身任务执行前风险评估
- 模型输出可信度与机器人行为策略联动

### 4. Deployment and Model Compression Reliability

研究 VLM/VLA 在边缘设备、量化部署和机器人平台上的可靠性变化。

可能方向：

- FP16/INT8/INT4 对 VLM 输出可靠性的影响
- 量化后 hidden-state UQ 是否仍有效
- 端侧部署中的性能、速度、可靠性权衡

## Active Projects

- [VLM Uncertainty and Visual Perturbation Attribution](projects/vlm-uncertainty.md)
- [Mini Model Training Practice](projects/mini-model-training.md)
- [Embodied Robot Recovery Ideas](projects/robot-recovery.md)

## Study System

我当前采用三条线并行，但每天执行时保持收敛：

- 基础线：深度学习、Transformer、VLM、机器人学习。
- 论文线：每周精读 1 篇和主线相关的论文。
- 实验线：持续推进一个最小实验闭环。

每日最低产出：

- 学清楚一个基础概念。
- 推进一个具体实验动作。
- 沉淀一段笔记、表格或代码说明。

## Repository Structure

```text
research-home/
├── README.md
├── roadmap.md
├── weekly.md
├── backlog.md
├── logs/
├── notes/
│   ├── deep-learning/
│   ├── vlm/
│   ├── uncertainty/
│   └── embodied-ai/
├── papers/
├── projects/
└── templates/
```

## Principles

- 方向可以开放，执行必须收敛。
- 当前项目先做闭环，再谈扩展。
- 不把长期愿景压成今日焦虑。
- 先提升自己，再反哺团队和公司。
- 研究要服务于真实机器人系统，而不是停留在离线指标。
