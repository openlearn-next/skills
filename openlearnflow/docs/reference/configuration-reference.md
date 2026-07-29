# Configuration Reference

## 主配置 (skill.config.json)

| 键 | 默认值 | 说明 |
|----|--------|------|
| `runtime.maxWorkflowConcurrency` | 3 | 最大并发工作流 |
| `runtime.workflowTimeoutMs` | 1800000 | 工作流超时(30min) |
| `expert.temperature` | 0.4 | LLM 温度 |
| `expert.maxTokens` | 4096 | 单次最大 Token |
| `output.defaultFormat` | markdown | 默认输出格式 |
| `quality.passThreshold` | 70 | 质量合格线 |

## 模型配置 (model.config.json)

```json
{
  "defaultProvider": "openai",
  "providers": {
    "openai": { "model": "gpt-4o" },
    "ollama": { "model": "qwen2.5:7b" },
    "mock": { "enabled": true }
  }
}
```

## 功能开关 (feature-flags.json)

| 功能 | 默认 | 说明 |
|------|------|------|
| `ai` | true | AI 功能总开关 |
| `knowledge-base` | true | 知识库检索 |
| `quality-optimization` | true | 质量自动优化 |
| `adaptive-learning` | false | 自适应学习(开发中) |

## 环境配置

| 参数 | Development | Production |
|------|------------|------------|
| provider | mock | openai |
| debug | true | false |
| auto-optimize | false | true |
