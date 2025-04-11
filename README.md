---
license: Apache License 2.0

text:
  #二级只能属于一个task_categories
  text-generation:
    #三级可以多选
    languages:
      - zh

configs: # 配置数据集的子数据集和划分
- config_name: default
  data_files:
  - split: train
    path: "Petro_Distall_R1.json"

---

# 中文石油工程领域DeepSeek-R1蒸馏数据集（Chinese-PetroEngineering-Data-Distill-From-R1）

<p align="center">
🤗 <a href="https://huggingface.co/datasets/YOUR_USERNAME/Chinese-PetroEngineering-DeepSeek-R1-Distill">Hugging Face</a>&nbsp&nbsp | &nbsp&nbsp🤖 <a href="https://modelscope.cn/datasets/YOUR_USERNAME/Chinese-PetroEngineering-DeepSeek-R1-Distill">ModelScope</a> &nbsp&nbsp | &nbsp&nbsp🚀 <a href="https://github.com/YOUR_USERNAME/Chinese-PetroEngineering-Data-Distill-From-R1">Github</a>
</p>

本数据集为中文石油工程领域基于DeepSeek-R1全量版蒸馏的专业数据集，涵盖井工程、完井工程、岩石力学等油气井工程领域的核心知识，总数据量为13,083条。

## 数据集特点

本数据集具有以下特点：

1. **专业领域覆盖**：
   - 井工程技术
   - 完井工程
   - 岩石力学
   - 其他油气井工程相关领域

2. **数据格式**：采用COT（Chain-of-Thought，思维链）格式，包含：
   - 输入问题（input）
   - 思维过程（thought_process）
   - 最终答案（answer）

3. **数据示例**：
```json
{
  "id": 1,
  "question": "什么是地层失稳",
  "thought_process": "嗯，用户问的是地层失稳，作为石油工程专家，我需要准确回答这个问题。首先，地层失稳在钻井过程中确实是个大问题，可能导致井壁坍塌、卡钻甚至井喷。我应该先定义清楚什么是地层失稳，然后解释它的成因...",
  "answer": "地层失稳（Formation Instability）是石油工程钻井过程中井眼周围岩石因力学或化学作用失去原有平衡状态，导致井壁坍塌、缩径或发生塑性变形等破坏的现象..."
}
```

## 数据集蒸馏细节

在蒸馏过程中，我们采用了以下策略：

1. **问题生成**：
   - 基于石油工程专业知识体系大纲
   - 利用多个大模型（DeepSeek-R1、ChatGPT、夸克等）协同生成专业问题
   - 确保问题覆盖井工程、完井、岩石力学等核心领域

2. **答案生成**：
   - 使用火山引擎API调用DeepSeek-R1全量版模型
   - 在思维过程和回答中融合网络搜索结果，确保专业性和准确性
   - 保持专业术语的规范使用

3. **提示词设置**：
   - 使用专业领域提示词："作为石油工程领域的专家，请你专业、准确回答问题:"
   - 不添加额外的系统提示词

4. **数据质量控制**：
   - 保持专业术语的准确性
   - 确保回答的完整性和逻辑性
   - 保留思维过程，便于理解推理链路
   - 结合网络搜索结果进行内容验证和补充

## 局限性

本数据集仍存在一些局限性：

1. 数据未经过进一步的筛选和验证
2. 可能存在一些专业术语或概念的表述不够准确
3. 答案的完整性和准确性需要专业人士进一步验证
4. 不同专业领域的数据分布可能不够均衡

## 使用建议

1. 建议在使用此数据集时，结合实际工程经验进行验证
2. 可用于模型预训练或微调，但建议在实际应用前进行专业审核
3. 适合用于辅助学习和研究，不建议直接用于工程决策

## 引用

```text
@misc{Chinese-PetroEngineering-Data-Distill-From-R1,
  author = {Xueqiang Ma, Saina Yue},
  title = {The Chinese Petroleum Engineering Dataset Distilled from DeepSeek-R1},
  year = {2025},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/YOUR_USERNAME/Chinese-PetroEngineering-Data-Distill-From-R1}},
}
```

## 联系作者

请替换以下联系方式为您的实际联系方式：

- GitHub: [YOUR_USERNAME](https://github.com/YOUR_USERNAME)
- Email: your.email@example.com

## 致谢

感谢火山引擎提供的API支持，使得本数据集的生成成为可能。同时感谢所有为本项目提供建议和帮助的同行。

## 许可证

本项目采用 Apache License 2.0 许可证。详见 LICENSE 文件。
