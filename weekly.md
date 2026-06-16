# Weekly Plan

## This Week

### Main Goal

把当前 VLM 不确定性实验从单样本 probe 推进到 `20` 张图的小规模批量实验。

### Must Do

- [ ] 整理 `Hidden-state-sampling-statistics` 当前 probe 结果。
- [ ] 明确批量结果字段：image_id、variant、prompt、answer、SSS、CCS、confidence、uncertainty。
- [ ] 写批量脚本：`20` 张图 × 原图/8 种扰动 × 描述任务。
- [ ] 保存 `comparison.json/csv`。
- [ ] 记录 3 个典型案例：原图稳定、扰动轻微偏移、扰动严重偏移。

### Study

- [ ] Transformer hidden state 和 attention 区别。
- [ ] VLM 基本结构：vision encoder + projector + LLM。
- [ ] 不确定性基础：entropy、calibration、OOD。
- [ ] logits、softmax、PPL 的直观含义。

### Paper

- [ ] 精读 hidden-state UQ 论文方法部分。
- [ ] 写一页论文笔记。
- [ ] 标出还没有严格复现的部分：attention-guided aggregation。

### Daily Minimum

每天只要求留下三个痕迹：

- [ ] 一个基础概念。
- [ ] 一个实验推进。
- [ ] 一段记录或笔记。

### Review

周末复盘：

- 本周实际推进了什么？
- 哪个实验结果最有价值？
- 哪个基础概念还没弄明白？
- 下周只做哪一个主任务？
