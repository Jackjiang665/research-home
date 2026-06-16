# Roadmap

## Timeline

当前时间：2026 年 6 月。

关键节点：

- 2026.06-2026.08：研究生入学前准备期。
- 2026.09：进入北京邮电大学开始研究生阶段学习。
- 研一上：对齐导师方向、实验室平台和自己的长期主线。
- 研一下-研二：形成可发表或可展示的稳定课题。

## 2026.06-2026.08 入学前目标

核心目标：

> 以 VLM 不确定性溯源为研究切入，同时系统补深度学习、多模态模型和机器人学习基础，为进入具身多模态可靠性方向做准备。

### 研究目标

- 跑通 VLM 输出不确定性最小实验闭环。
- 完成 `20-50` 张图的原图/扰动图实验。
- 比较 hidden-state UQ 与 entropy/PPL 等传统指标。
- 初步分析视觉扰动下回答内容、正确性和置信度变化。
- 输出一份 5 页左右的实验报告。

### 学习目标

- 深度学习基础：反向传播、优化、CNN、Transformer。
- VLM 基础：CLIP、LLaVA/Qwen-VL、image token、text token。
- UQ 基础：entropy、calibration、OOD、epistemic/aleatoric uncertainty。
- 具身基础：机器人任务执行、imitation learning、active perception。

### 工程目标

- 训练一个小 CNN 分类模型。
- 训练一个小 Transformer 或字符级语言模型。
- 完成一个小型 CLIP-like 图文对齐练习。
- 维护当前 `research-home` 作为个人研究主页和工作台。

## 研一上目标

核心目标：

> 找到自己在实验室中的稳定位置：具身系统、多模态可靠性、机器人自我诊断三者之间的交叉点。

任务：

- 了解实验室真实项目和平台，包括机械臂、无人机、机器狗等。
- 选择一个最适合接入的具身平台或仿真任务。
- 把 VLM 不确定性模块接入一个简单机器人感知/决策流程。
- 明确自己偏具身组、多模态组，还是二者之间的可靠性方向。

## 候选长期主线

### 主线 B：具身智能系统与机器人任务执行

研究重点：让机器人在真实环境中完成任务。

可能题目：

- 多模态大模型驱动的机器人任务执行系统。
- 面向桌面操作的 VLM/VLA + 技能库系统。
- 机器狗/无人机巡检中的多模态场景理解与任务规划。

### 主线 C：机器人自我诊断与自适应恢复

研究重点：机器人失败或不确定时，如何判断原因并恢复。

可能题目：

- 面向机器人任务的失败检测与来源归因。
- 基于不确定性估计的主动感知与恢复策略。
- 多模态具身智能体的自我诊断机制。

### 当前切入 A：VLM 输出不确定性溯源

当前定位：B/C 的基础模块。

作用：

- 判断 VLM 输出是否可靠。
- 判断不确定性是否来自视觉输入退化。
- 为机器人执行前风险评估提供信号。
- 未来触发重拍、换视角、请求确认等恢复动作。

## 30-Day Focus

未来 30 天只抓一个主线：

> 把 VLM 输出不确定性实验做成完整小闭环。

交付物：

- 批量实验脚本。
- 20-50 张图实验结果。
- 原图/扰动图对比表。
- hidden-state UQ 与传统 UQ 对比。
- 一份结构清楚的实验报告。

## 4-Week Plan

### Week 1: VLM UQ 小闭环

目标：把当前 probe 变成可复用的小批量实验。

学习：
- hidden state、attention、logits、entropy、PPL。
- Qwen-VL / LLaVA 这类 VLM 的基本结构。

实验：
- 跑 `20` 张图 × 原图/8 种扰动 × 描述任务。
- 保存回答、hidden-state confidence、uncertainty、扰动类型。
- 记录典型案例：正常、轻微偏移、严重偏移。

产出：
- 一个批量实验脚本。
- 一个 `comparison.csv/json`。
- 一页实验观察。

### Week 2: 传统 UQ 与正确性判断

目标：把 hidden-state UQ 和传统指标放在一起比较。

学习：
- predictive entropy。
- maximum softmax probability。
- perplexity。
- calibration 基本概念。

实验：
- 给批量实验补充 entropy / PPL / MSP。
- 使用 API 裁判或人工抽样判断描述质量。
- 比较正确/偏移/错误回答的分数分布。

产出：
- 指标对比表。
- 3-5 个典型案例分析。
- 一页 “hidden-state UQ 是否有用” 的阶段结论。

### Week 3: 小模型训练建立直觉

目标：不要只会调用大模型，开始理解模型训练过程。

学习：
- PyTorch Dataset / DataLoader。
- loss、optimizer、train/eval。
- CNN 基础。

练习：
- 训练一个 MNIST 或 CIFAR-10 CNN。
- 记录训练曲线、准确率、错误样本。
- 写一页笔记：训练流程到底发生了什么。

产出：
- 一个可跑的小模型训练项目。
- 一页 “从输入到 logits” 的解释。

### Week 4: Transformer 与具身连接

目标：把模型内部理解和机器人长期方向接起来。

学习：
- token、embedding、self-attention、hidden state。
- 具身任务执行 pipeline：感知、规划、技能、控制。
- active perception 基本想法。

练习：
- 跑一个 tiny Transformer 或字符级语言模型。
- 画出当前 VLM UQ 模块如何接入机器人执行前检查。

产出：
- tiny Transformer 笔记。
- 一个 “VLM reliability -> robot recovery” 的系统草图。
- 下个月计划。
