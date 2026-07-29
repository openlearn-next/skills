# Changelog

## v1.2.0 (2026-07-29)

### openlearnflow v1.3.0 — 外部 skill 降级 + 模板系统

- 外部 skill 可用性自动检测（skillhub list），缺失时降级不阻塞主流程
- PPT 降级：手写 16:9 HTML 幻灯片 / 网页降级：手写 Canvas / 视觉降级：默认方案
- PPT 模板系统：11 种专业布局 + layout-catalog.json 路由规则
- 网页四步协作链：design-taste-frontend → web-design-engineer → web-design-guidelines → Review Expert

## v1.1.0 (2026-07-29)

### openlearnflow v1.2.0 — 成品物质量优化

- PPT 生成：Chief Expert 全 Context 汇总 → 结构化规格 JSON → pptx skill → Review 审核（最多 2 次重试）
- 互动网页：Activity Expert 交互模拟规格 → Chief Expert 技术翻译 → web-design-engineer → Review 审核（最多 2 次重试）
- 素材策略：builtin（知识库预存）/ generated（运行时绘制）/ external（外部 URL）
- 4 Expert Prompt 更新：Chief / Activity / Resource / Teaching Review

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
