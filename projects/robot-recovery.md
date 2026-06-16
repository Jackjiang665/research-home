# Project Ideas: Robot Self-Diagnosis and Adaptive Recovery

## Long-Term Vision

我长期感兴趣的是让机器人具备自我诊断和自适应恢复能力：

> 机器人不仅能执行任务，还能判断自己什么时候可能做错、失败来自哪里，以及下一步应该如何补救。

## Possible Demo 1: Manipulation Before Execution

Scenario:

用户说：“把红色杯子放进盒子里。”

Pipeline:

```text
camera image
-> VLM scene understanding
-> uncertainty module
-> decision:
   - execute
   - re-observe
   - ask human
   - refuse unsafe action
```

Failure sources:

- 目标被遮挡。
- 图像模糊。
- 指令歧义。
- VLM 幻觉。
- 目标定位不可靠。

## Possible Demo 2: Robot Dog Inspection

Scenario:

机器狗巡检走廊，寻找灭火器或异常物体。

Recovery:

- confidence high: continue patrol
- confidence medium: move closer
- confidence low: request confirmation

## Possible Demo 3: UAV Visual Search

Scenario:

无人机根据自然语言任务搜索目标。

Recovery:

- 改变高度。
- 改变视角。
- 重新拍摄。
- 请求人工确认。

## Relation to Current Work

当前 VLM uncertainty 项目是这个长期方向的第一个基础模块：

> 先判断视觉语言模型输出是否可靠，再让机器人根据可靠性采取不同动作。
