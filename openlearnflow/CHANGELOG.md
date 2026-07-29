# Changelog

## v1.3.1 (2026-07-29)

### 文档优化

- README 执行流水线增加中文 Expert 名称和职责说明
- 每个 Phase 补齐降级策略描述

## v1.3.0 (2026-07-29)

### 成果物质量 + 文档落盘

**外部 skill 降级策略：**
- 首次对话自动检测外部 skill 可用性（skillhub list）
- 缺失 skill 时自动降级，不阻塞教学设计主流程
- PPT 降级：手写 16:9 HTML 幻灯片 / 网页降级：手写 Canvas 页面
- 视觉方向降级：默认"教育科技"方案 / UI 审查降级：自检清单替代
- 向用户透明报告当前可用/降级状态

**PPT 模板系统：**
- 新增 `templates/pptx/layouts/`：11 种专业 PPT 布局模板
- 新增 `templates/pptx/layout-catalog.json`：布局 ID → HTML 文件 → 插槽定义 → 路由规则

**互动网页四步协作链：**
- `design-taste-frontend` → 3 个视觉方向供用户选择
- `web-design-engineer` → 严格工作流（System → v0 → Build → Critique）
- `web-design-guidelines` → UI 合规审查
- Review Expert → WC01–WC04 教学合规审查

**教学设计文档落盘：**
- Review 通过后自动保存 `workspace/{项目}/{课题}-教学设计.md`
- 对话输出摘要，完整内容以文件为准
- 文档末尾附成果物索引表

**Expert 更新：**
- Chief Expert：可用性检测 + 降级策略 + 文档保存规则
- Activity Expert：交互模拟规格输出段
- Resource Expert：素材来源标注（builtin / generated / external）
- Teaching Review Expert：PPT 审核（PC01–PC04）+ 网页审核（WC01–WC04）

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
