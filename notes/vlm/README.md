# VLM Notes

## Core Architecture

典型 VLM 可以粗略理解为：

```text
image
-> vision encoder
-> projector
-> image tokens
-> LLM with text tokens
-> answer
```

## Questions To Understand

- image tokens 是什么？
- text tokens 是什么？
- Qwen-VL 如何拼接图像和文本？
- VLM 的 hidden states 包含哪些 token？
- 输出 token 的 hidden state 如何和图像信息发生关系？
- VLM hallucination 为什么发生？
