# Architecture

## 整体架构

```
Teacher Input → Workflow Engine → Expert Pipeline → Prompt → LLM → Output
                     │
              Knowledge Base (RAG)
                     │
              Quality Optimization
```

## 数据流

```
TeacherInput
  → Curriculum Expert (课标分析)
    → Knowledge Expert (知识图谱)
      → Student Expert (学情分析)
        → Objective Expert (目标设计)
          → Strategy Expert (策略选择)
            → Activity Expert (活动设计)
              → Assessment Expert (评价设计)
                → Resource Expert (资源整合)
                  → Reflection Expert (教学反思)
                    → Quality Reviewer (质量审核)
                      → FinalTeachingDesign
```

## 组件依赖

```
Config ──> Runtime ──> Workflow Engine ──> Expert Executor
  │              │              │
  │              ├── EventBus ──┤
  │              ├── CacheMgr ──┤
  │              └── HookMgr ───┤
  │                             │
  └── Knowledge Base ──── RAG ──┤
                                │
                    Output Generator ──> Exporter
```

## 层架构

| 层 | 组件 | 职责 |
|----|------|------|
| Configuration | skill.config.json, environments/ | 运行时参数 |
| Knowledge | pedagogy/, curriculum/, assessment/ | 领域知识 |
| Execution | Workflow Engine, Expert Executor | 流程调度 |
| Generation | Prompt Renderer, Pipeline | 内容生成 |
| Quality | Evaluator, Optimizer | 质量保证 |
| Output | Output Generator, Exporters | 多格式输出 |
