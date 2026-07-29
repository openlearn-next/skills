# Changelog

## v1.1.0 (2026-07-29)

### Skill Rename

- Skill ID 从 `teaching-design` 重命名为 `openlearnflow`
- Skill 名称更新为 "OpenLearn Flow — 技术与工程教学设计"

### New Capabilities

- `ppt-generation`: 基于 Resource Expert PPT 大纲，委托 `pptx` skill 渲染 .pptx 课件
- `web-interactive`: 基于 Activity Expert 活动设计，委托 `web-design-engineer` skill 生成互动教学网页

### External Skill Dependencies

- `pptx` (可选): PPT 演示文稿创建与编辑
- `web-design-engineer` (可选): HTML/CSS/JS 交互页面生成

## v1.0.0 (2026-07-28)

### Initial Release

**Features:**
- 11 项教学设计 Capability（课标分析/教材分析/知识图谱/学情分析/目标设计/策略设计/活动设计/评价设计/资源整合/教学反思/质量审核）
- 4 个 Workflow 定义（lesson-plan/curriculum-analysis/assessment-design/reflection）
- 11 个 Expert 定义（含 6 个 base JSON + 5 个 enhanced JSON）
- 12 个 Prompt 模板（11 Expert + 1 Chief Expert）
- 4 种输出格式（Markdown/JSON/DOCX/PPTX）
- Context Schema 定义（13 个 Context 类型）
- 5 维 21 项评估指标体系
- 3 个评估测试用例
- 完整的 Skill Package 结构

**Workflows:**
- `lesson-plan` (11 steps): 完整教学设计流水线
- `curriculum-analysis` (2 steps): 独立课标分析
- `assessment-design` (5 steps): 评价方案（含并行）
- `reflection` (7 steps): 反思改进（含并行）

**Experts:**
- `curriculum-expert`: 课程标准分析（analysis）
- `textbook-expert`: 教材分析（analysis）
- `knowledge-expert`: 知识体系分析（analysis）
- `student-expert`: 学情分析（analysis）
- `goal-expert`: 教学目标设计（design）
- `strategy-expert`: 教学策略设计（design）
- `activity-expert`: 学习活动设计（design，含 EDP 约束）
- `assessment-expert`: 评价方案设计（design，含 Rubric）
- `resource-expert`: 资源整合（curation）
- `reflection-expert`: 教学反思设计（analysis）
- `review-expert`: 教学质量审核（review）

**Templates:**
- `markdown/lesson-plan.md`: 12 节完成模板
- `json/teaching-design.schema.json`: 输出结构 Schema
- `docx/lesson-plan.template.docx`: 14 节文档结构
- `ppt/lesson-plan.template.pptx`: 13 张幻灯片结构

**Evaluation:**
- 5 维 21 项评分指标（满分 100，及格 70）
- 4 级评估（A/B/C/D）
- 3 个跨学科测试用例
