# Developer Guide

## 扩展 Skill

### 新增 Expert

1. 创建 `experts/my-expert.json`
2. 创建 `prompts/experts/my-expert.md`
3. 在 `skill.manifest.json` 中注册
4. 在 `config/model.config.json` 中添加模型映射

### 新增 Workflow

1. 创建 `workflows/my-workflow.workflow.json`
2. 定义步骤序列和依赖关系
3. 在 `skill.manifest.json` 的 workflows 中注册
4. 在 `config/workflow.config.json` 中添加执行参数

### 新增知识源

1. 添加知识文件到 `knowledge/{domain}/`
2. 在 `config/knowledge.config.json` 中注册源
3. 在 `knowledge/retrieval/index-config.json` 中添加检索策略
4. 在对应 Expert 的 enhanced 版本中添加 knowledgeSources

## 测试

```bash
pnpm test -- src/__tests__/skill/
pnpm test -- src/__tests__/release/
```

## 调试

```json
{
  "environment": "development",
  "debug": true,
  "verbose": true,
  "logging": "debug"
}
```
