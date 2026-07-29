# Changelog

## v1.0.0 (2026-07-29)

### Edu Skills Collection 初始化

**合集结构：**
- 创建合集根目录 `edu-skills/`，作为多 skill 的统一仓库
- 添加根级 `manifest.json`，定义合集清单与分类体系
- 添加 `.gitignore`，排除 workspace 和 node_modules

**已收录 Skill：**
- `openlearnflow` v1.1.0 — 高中技术与工程 AI 教学设计
  - 11 个领域 Expert 协作流水线（课标分析→教材分析→知识体系→学情→目标→策略→活动→评价→资源→反思→审核）
  - 12 个 Expert Prompt 模板（11 Expert + 1 Chief Expert）
  - 4 个 Workflow 定义（lesson-plan / curriculum-analysis / assessment-design / reflection）
  - 支持外部 skill 调用：`pptx`（PPT 课件生成）、`web-design-engineer`（互动网页生成）
  - 从 `teaching-design` 重命名为 `openlearnflow`
  - 完整知识库：课标、教学法、学科图谱、工程案例、评估体系、优化策略
  - 13 个 Context Schema 定义
  - 4 种输出格式（Markdown / JSON / DOCX / PPTX）

**规划能力：**
- 练习生成 (exercise-generation)
- 知识图谱 (knowledge-graph)
- 学情评估 (student-assessment)
- 资源整合 (resource-curation)
