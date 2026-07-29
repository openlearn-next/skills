# OpenLearn Flow v1.3.0

> 中国普通高中《技术与工程》AI 协同教学设计技能

## 概述

OpenLearn Flow 通过 **Chief Expert + 11 领域 Expert** 协作生成结构化教学设计，并可委托外部 skill 生成 PPT 课件和互动教学网页。外部 skill 缺失时自动降级，不阻塞主流程。

## 工作流程

```
用户输入（课题/年级/课时/教学模式）
  │
  ├─ Phase 1: 教学设计流水线（11 Expert 顺序执行）
  │   │
  │   ├─ 1. Curriculum Expert（课程标准专家）      → 课标解读，回答"为什么教"
  │   ├─ 2. Textbook Expert（教材分析专家）        → 章节定位、重难点分析
  │   ├─ 3. Knowledge Expert（知识体系专家）       → 核心概念图谱 + 工程案例 + 跨学科连接
  │   ├─ 4. Student Expert（学情分析专家）         → 已有基础、认知困难、分层策略
  │   ├─ 5. Goal Expert（教学目标专家）            → 五维目标（知识/技能/工程思维/创新/态度）
  │   ├─ 6. Strategy Expert（教学策略专家）        → 教学模式、课堂组织、技术工具
  │   ├─ 7. Activity Expert（活动设计专家）        → 按课时设计学习活动 + 交互模拟规格
  │   ├─ 8. Assessment Expert（评价设计专家）      → 形成性/表现性/终结性评价 + Rubric
  │   ├─ 9. Resource Expert（资源整合专家）        → 教学材料 + 素材来源标注
  │   ├─ 10. Reflection Expert（教学反思专家）     → 反思框架 + 预设问题 + 改进方向
  │   └─ 11. Review Expert（质量审核专家）         → 9 项标准审核 + PPT/网页审核
  │
  ├─ Phase 2: 教学文档输出（必须，自动落盘）
  │   └─ 保存为 workspace/{项目}/{课题}-教学设计.md
  │       对话中仅输出摘要，完整内容见文件
  │
  ├─ Phase 3: PPT 课件生成（可选）
  │   ├─ 自动检测 pptx skill 是否可用
  │   ├─ 可用 → layout-catalog 11 种布局模板 → 渲染 .pptx
  │   └─ 不可用 → 降级为手写 16:9 HTML 幻灯片（浏览器全屏演示）
  │
  └─ Phase 4: 互动网页生成（可选，四步协作链）
      ├─ Step 1: design-taste-frontend → 确定视觉方向（3 选 1）
      ├─ Step 2: web-design-engineer → System → v0 → Build → Critique
      ├─ Step 3: web-design-guidelines → UI 合规审查（对比度/触控/响应式/无障碍）
      └─ Step 4: Review Expert → WC01–WC04 教学合规审查
          所有外部 skill 不可用时 → 降级为手写 Canvas + CSS + JS 页面
```

## 目录结构

```
openlearnflow/
├── SKILL.md              # AI Agent 入口指令（含降级策略）
├── manifest.json         # Skill 清单
├── prompts/              # 12 Expert + 1 Chief Prompt 模板
├── workflows/            # 4 个 Workflow 定义
├── experts/              # 11 个 Expert 元数据
├── knowledge/            # 领域知识库（课标/教学法/图谱/案例）
├── templates/pptx/       # PPT 布局模板系统
│   ├── layout-catalog.json  # 11 种布局 + 路由规则
│   └── layouts/             # HTML 模板文件
├── contexts/             # Context Schema
├── evaluation/           # 教学质量评估标准
├── optimization/         # 优化策略
└── docs/                 # 参考文档
```

## 工作流

| 工作流 | 步骤数 | 说明 |
|--------|--------|------|
| `lesson-plan` | 11 | 标准课时教学设计 |
| `curriculum-analysis` | 2 | 独立课程标准分析 |
| `assessment-design` | 5 | 评价方案设计 |
| `reflection` | 7 | 教学反思与改进 |

## Expert 角色

| Expert | 类型 | 说明 |
|--------|------|------|
| curriculum-expert | 分析 | 课程标准解读 |
| textbook-expert | 分析 | 教材章节分析 |
| knowledge-expert | 分析 | 知识体系 + 工程案例 + 跨学科联系 |
| student-expert | 分析 | 学情分析 + 分层策略 |
| goal-expert | 设计 | 五维教学目标 |
| strategy-expert | 设计 | 教学策略 + 模式选择 |
| activity-expert | 设计 | 学习活动设计 + 交互模拟规格 |
| assessment-expert | 设计 | 评价方案 + Rubric |
| resource-expert | 整合 | 教学资源 + 素材来源标注 |
| reflection-expert | 反思 | 教学反思框架 |
| review-expert | 审核 | 9 项教学审核 + PPT 审核 + 网页审核 |

## 成果物

| 类型 | 格式 | 生成方式 |
|------|------|----------|
| 教学设计文档 | Markdown 文件 | 11 Expert 流水线 → 自动保存到 workspace/ |
| PPT 课件 | .pptx / HTML | layout-catalog 模板系统 → pptx skill（不可用时手写 HTML） |
| 互动教学网页 | HTML | 三 skill 协作链（不可用时手写 Canvas） |

## 外部 Skill 依赖

| Skill | 用途 | 必需 | 不可用时 |
|-------|------|------|---------|
| `pptx` | PPT 课件渲染 | 否 | 手写 16:9 HTML 幻灯片 |
| `design-taste-frontend` | 网页视觉方向 | 否 | 默认"教育科技"方案 |
| `web-design-engineer` | 互动网页生成 | 否 | 手写 Canvas 页面 |
| `web-design-guidelines` | UI 合规审查 | 否 | 自检清单替代 |

## 使用示例

```
用户: 我需要设计一个研究都江堰的项目式学习教学设计，在这个项目中让学生学习技术与工程教材中有关的部分

OpenLearn Flow:
  1. 检测外部 skill 可用性
  2. 11 Expert 流水线生成教学设计
  3. 保存 教学设计.md 到 workspace/
  4. 生成 PPT 课件（12 页，layout-catalog 模板）
  5. 生成弯道环流互动模拟网页
  6. Review Expert 审核通过
```

## 许可证

MIT License
