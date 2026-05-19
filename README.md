---
base_model: Qwen/Qwen2.5-1.5B-Instruct
library_name: peft
pipeline_tag: text-generation
tags:
  - leyoai
  - qwen2.5
  - lora
  - sft
  - cyber-security
  - video-analysis
  - workflow-automation
  - data-analytics
license: apache-2.0
language:
  - zh
  - en
datasets:
  - leyoai-custom-dataset
---

# leyoai-flow-mini

## 中文介绍

LeyoAI Flow Model (Mini) 是一个基于 Qwen2.5-1.5B-Instruct 微调的流程自动化助手，适用于轻量级工作流设计和优化。

### 使用方法

```python
from modelscope import AutoModelForCausalLM, AutoTokenizer

# Load model
model = AutoModelForCausalLM.from_pretrained(
    "FFZwai/leyoai-flow-mini",
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained("FFZwai/leyoai-flow-mini")

# Inference
prompt = "设计一个用户注册流程"
inputs = tokenizer(prompt, return_tensors="pt").to(model.device)
outputs = model.generate(**inputs, max_length=100)
response = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(response)
```

### 训练详情

- **基座模型**: Qwen2.5-1.5B-Instruct
- **微调方式**: LoRA (Low-Rank Adaptation)
- **LoRA Rank**: 16
- **LoRA Alpha**: 32
- **训练设备**: Mac Studio MPS (fp32)
- **部署平台**: HuggingFace Spaces / ModelScope

### 性能指标

- **Eval Loss**: 0.288
- **Accuracy**: 90.5%

### 许可证

Apache License 2.0

---

## English Introduction

LeyoAI Flow Model (Mini) is a workflow automation assistant fine-tuned from Qwen2.5-1.5B-Instruct, suitable for lightweight workflow design and optimization.

### Usage

```python
from modelscope import AutoModelForCausalLM, AutoTokenizer

# Load model
model = AutoModelForCausalLM.from_pretrained(
    "FFZwai/leyoai-flow-mini",
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained("FFZwai/leyoai-flow-mini")

# Inference
prompt = "Design a user registration workflow"
inputs = tokenizer(prompt, return_tensors="pt").to(model.device)
outputs = model.generate(**inputs, max_length=100)
response = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(response)
```

### Training Details

- **Base Model**: Qwen2.5-1.5B-Instruct
- **Fine-tuning Method**: LoRA (Low-Rank Adaptation)
- **LoRA Rank**: 16
- **LoRA Alpha**: 32
- **Training Device**: Mac Studio MPS (fp32)
- **Deployment**: HuggingFace Spaces / ModelScope

### Performance Metrics

- **Eval Loss**: 0.288
- **Accuracy**: 90.5%

### License

Apache License 2.0

---

## 关于 LeyoAI (About LeyoAI)

**LeyoAI** 是杭州市上城区乐友信息服务工作室旗下的垂直领域 AI MaaS 平台，提供四大 AI 助手：

- **Cyber Model**: AI 安全助手
- **Video Model**: 视频安全助手
- **Flow Model**: 流程自动化助手
- **Analytics Model**: 数据分析助手

**LeyoAI** is a vertical AI MaaS platform by Hangzhou Shangcheng Leyou Information Service Studio, providing four AI assistants:

- **Cyber Model**: AI Security Assistant
- **Video Model**: Video Safety Assistant
- **Flow Model**: Workflow Automation Assistant
- **Analytics Model**: Data Analytics Assistant

### 链接 (Links)

- 官网 (Website): https://leyoai.vercel.app
- GitHub: https://github.com/richard3153/leyoai-landing
- HuggingFace: https://huggingface.co/FFZwai

---

## Framework Versions

- PEFT 0.18.1
- Transformers 4.51.3
- PyTorch 2.7.0
- Datasets 3.6.0
