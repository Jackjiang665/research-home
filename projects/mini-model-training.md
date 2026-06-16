# Project: Mini Model Training Practice

## Goal

通过训练小模型建立对深度学习、Transformer、hidden state 和 logits 的直觉。

## Why

当前主要短板不是工程动手，而是对模型内部机制、训练流程和架构细节还不够清楚。小模型训练可以把抽象概念变成可观察的代码和结果。

## Planned Exercises

### 1. CNN Classification

- Dataset: MNIST or CIFAR-10
- Concepts:
  - Dataset / DataLoader
  - loss
  - optimizer
  - train / eval
  - accuracy

### 2. Tiny Transformer

- Task: character-level generation or text classification
- Concepts:
  - token
  - embedding
  - attention
  - hidden state
  - logits

### 3. CLIP-like Toy Model

- Task: image-text contrastive learning
- Concepts:
  - image encoder
  - text encoder
  - contrastive loss
  - multimodal alignment

### 4. Small VLM / LoRA Practice

- Task: run or lightly finetune a small multimodal model
- Concepts:
  - image token
  - text token
  - instruction tuning
  - adapter / LoRA

## Rule

每个练习只追求一个闭环：

- 跑通代码。
- 画出结构图。
- 写一页笔记。
- 记录一个之前不懂、现在懂了的概念。
