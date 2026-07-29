# Lesson Plan Workflow

## Goal
生成一份完整的中国普通高中《技术与工程》课时教学设计方案。

## Expert Collaboration Rules

本 Workflow 调度 11 位 Expert 按顺序协同工作：

```
curriculum → textbook → knowledge → student → objective
    → strategy → activity → assessment → resource → reflection → review
```

### 协作原则

1. **单职责原则** — 每位 Expert 只完成自己的分析/设计任务
2. **前置依赖** — 后置 Expert 只能使用前置 Expert 的输出
3. **不可修改** — 任何 Expert 不得修改已有 Context
4. **Chief 协调** — 最终由 Chief Expert 检查一致性并汇总

### 数据流转

```
TeacherInput → TeachingContext
    ↓
Curriculum Expert → CurriculumContext
Textbook Expert → TextbookContext
Knowledge Expert → KnowledgeContext
Student Expert → StudentContext
    ↓
Goal Expert → GoalContext
Strategy Expert → StrategyContext
Activity Expert → LearningActivityContext
Assessment Expert → AssessmentContext
Resource Expert → ResourceContext
Reflection Expert → ReflectionContext
    ↓
Review Expert → TeachingReviewContext
Chief Expert → FinalTeachingDesign
```

## Output Requirements

| 格式 | 用途 |
|------|------|
| Markdown | 教师阅读的教学设计文档 |
| JSON | 系统消费的结构化数据 |
| DOCX | Word 文档（教研用途） |
| PPTX | 课件/说课展示 |

## Quality Checklist

- [ ] 课程标准符合度 ≥ 70%
- [ ] 核心素养体现度 ≥ 65%
- [ ] 工程实践完整性 ≥ 65%
- [ ] 教学闭环 ≥ 70%
- [ ] 资源完整性 ≥ 55%
- [ ] 课时合理性 ≥ 70%
