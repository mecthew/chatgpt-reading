# 个人chatgpt阅读小记
1. 根据[chatgpt分析](https://yaofu.notion.site/How-does-GPT-Obtain-its-Ability-Tracing-Emergent-Abilities-of-Language-Models-to-their-Sources-b9a57ac0fcf74f30a1ab9e3e36fa1dc1)，目前可以得出以下结论：
  + 语言生成能力 & 通用世界知识 & 上下文学习（in-context learning）来源于与训练 （GPT3-initial，`davinci`）
  + 模型的超大知识储备来源于其参数规模（175B）
  + 能够遵循指示并将其推广到新任务的能力来自于scaling instruction tuning (`davinci-instruct-beta`)
  + 执行复杂推理的能力很可能来自于对代码的训练（***why?***，`code-davinci-002`）
  + 生成中立、客观、安全和信息丰富的答案的能力来自于与人类的一致性。具体而言：
    - 如果进行SFT，则生成的模型为`text-davinci-002` 。
    - 如果进行RLHF，则生成的模型为`text-davinci-003`。
    - 无论是监督还是RLHF，这些模型都无法在许多任务上超越`code-davinci-002`，这被称为一致性损失。
  + 对话能力也来自于RLHF（`ChatGPT`），具体而言它在上下文学习中进行权衡：
    - 建模对话历史记录
    - 增加信息量
    - 拒绝超出模型知识范围的问题(***why?***)。
