# Changelog

## v1.2.3 (2026-07-29)

### ikea-teacher-training v1.0.0 — 基于宜家效应的教师培训课程计划设计器

- 三阶段交互流程：问卷生成 → 数据分析 → 课程计划生成
- 阶段一：通过访谈收集培训上下文，自动生成 6-8 题调查问卷（背景层 + 痛点层），输出可导入 Google Form / 问卷星的文本及结构化映射文件
- 阶段二：Node.js 脚本读取 CSV 回收数据，自动匹配列名映射，生成 ECharts 交互式 HTML 分析报告（饼图、横向柱状图、交叉分析图）
- 阶段三：基于分析结果和宜家效应，匹配三类活动模板（教学工具共创 / 课程片段重构 / 学生反馈系统搭建），生成完整课程计划文档
- 阶段间产物持久化到 `.training-plan/` 目录，支持断点续传和独立重跑
- 宜家效应核心机制：每个活动都要求教师亲手构建可带回课堂使用的教学产出物

## v1.2.2 (2026-07-29)

### assessment-creator v1.0.0 — 试题生成器首次发布

- 面向中学信息科技教师的练习试题自动生成技能
- 支持六种纸笔测试题型：单选、多选、判断、填空、简答、连线
- 三个 Expert 协作流水线：出题 Expert → 审题 Expert → 排版 Expert
- 13 条质量审查规则（正确性/清晰度/有效性/规范性/伦理）
- 数据与编码模块知识点库（12 个知识点），含参数化出题模板和常见错误
- 双入口交互模式：单轮快捷指令 + 多轮引导
- 分批出题（每批5道）+ 变体策略（参数采样 + 模板轮换）
- 教学解析级别输出（步骤推理 + 核心原理 + 教学提示）
- 外部 Skill 软依赖降级（IMA 不可用时不影响出题）
- Markdown 试卷模板 + 答案卷模板
- `exercise-generation` 分类状态更新为 active

## v1.2.1 (2026-07-29)

### openlearnflow v1.3.1 — 文档优化

- README 执行流水线增加中文 Expert 名称和职责说明

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
