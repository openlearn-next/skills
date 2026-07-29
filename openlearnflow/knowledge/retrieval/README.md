# RAG Retrieval Integration

## 概述

检索配置定义了知识源到 Expert 的映射关系和检索策略。Expert 在执行时根据对应的 Policy 从知识库检索相关知识，注入 Prompt Context。

## 检索流程

```
Expert.execute()
    │
    ├─ 1. 读取 Policy（按 expertId）
    ├─ 2. 获取 sources（知识源列表）
    ├─ 3. Query Expansion（同义词 + 概念层级扩展）
    ├─ 4. 检索匹配（exact/keyword/semantic/hybrid）
    ├─ 5. 排序去重（relevance ranking）
    └─ 6. 注入 Context（contextKey → Prompt）
```

## Expert → Policy 映射

| Expert | Policy | 策略 | 最大结果 | 知识源 |
|--------|--------|------|---------|--------|
| curriculum-expert | curriculum-policy | keyword | 5 | 课标 + 核心素养 + 映射 |
| strategy-expert | (inline) | keyword | 5 | 教学理论 + 工程教育 |
| goal-expert | (inline) | exact | 3 | 核心素养 + 映射 |
| activity-expert | activity-policy | hybrid | 8 | 工程教育 + 案例 + 知识图谱 |
| assessment-expert | assessment-policy | keyword | 5 | 评价方法 + 映射 |
| reflection-expert | (inline) | keyword | 3 | 教学理论 + 案例 |

## 检索策略

| 策略 | 说明 | 适用 |
|------|------|------|
| `exact` | 精确字段匹配 | 标准条目查询 |
| `keyword` | 关键词 + 同义词扩展 | 概念搜索 |
| `semantic` | 语义向量相似 | 案例匹配（预留） |
| `hybrid` | 关键词 + 语义混合 | 综合检索 |

## Query Expansion

支持两种扩展策略：
- **synonym**: 同义词映射（系统→system/子系统/整体）
- **concept-hierarchy**: 概念层级展开（控制→传感器/Arduino/反馈）

## Context Injection

检索结果注入到 Expert Prompt Context 中的 `retrieved*` key，由 PromptRenderer 的模板变量（`{{ retrievedCurriculum }}` 等）在渲染时替换。
