# OpenLearn Flow v1.1.0

> 中国普通高中《技术与工程》AI 协同教学设计技能

## 概述

OpenLearn Flow 将高中技术与工程教学设计专业知识封装为可复用的 AI Skill 包。它定义了从课程标准分析到质量审核的完整教学设计流水线，通过 **Chief Expert + 11 领域 Expert** 的协作模式生成结构化教学设计，并可委托外部专业 skill 生成 PPT 课件和互动教学网页。

## 目录结构

```
openlearnflow/
├── manifest.json         # Skill 清单（能力、工作流、Expert 定义）
├── SKILL.md              # AI Agent 入口指令
├── prompts/              # Expert Prompt 模板
│   ├── experts/          #   12 个领域 Expert 系统指令
│   ├── system/           #   Chief Expert 调度指令
│   └── workflows/        #   工作流 Prompt
├── workflows/            # Workflow 定义（JSON）
├── experts/              # Expert 元数据定义（JSON）
├── contexts/             # Context Schema 定义
├── knowledge/            # 领域知识库
├── evaluation/           # 教学质量评估标准
├── optimization/         # 教学设计优化策略
├── templates/            # 输出模板（md/json/docx/pptx）
├── examples/             # 使用示例
├── config/               # 运行时配置
└── docs/                 # 详细文档
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
| knowledge-expert | 分析 | 知识体系构建 |
| student-expert | 分析 | 学情分析 |
| goal-expert | 设计 | 五维教学目标设计 |
| strategy-expert | 设计 | 教学方法与策略选择 |
| activity-expert | 设计 | 学习活动设计 |
| assessment-expert | 设计 | 评价方案与 Rubric |
| resource-expert | 整合 | 教学资源整合（含 PPT 大纲） |
| reflection-expert | 反思 | 教学反思框架设计 |
| review-expert | 审核 | 9 项标准质量审核 |

## 成果物

| 类型 | 格式 | 生成方式 |
|------|------|----------|
| 教学设计文档 | Markdown | 本 skill 全流程产出 |
| PPT 课件 | .pptx | Resource Expert 大纲 → `pptx` skill 渲染 |
| 互动教学网页 | HTML/CSS/JS | Activity Expert 设计 → `web-design-engineer` skill 生成 |

## 外部 Skill 依赖

| Skill | 用途 | 必需 |
|-------|------|------|
| `pptx` | PPT 课件渲染 | 否 |
| `web-design-engineer` | 互动教学网页生成 | 否 |

## 输入 Context

```json
{
  "subject": "技术与工程",
  "grade": "高一",
  "chapter": "第三章 系统与设计",
  "topic": "系统的结构",
  "classHours": 3,
  "studentProfile": "学生对技术课程兴趣较高...",
  "teachingMode": "项目式学习",
  "deliverables": ["document", "ppt", "web"]
}
```

## 许可证

MIT License — 详见 LICENSE 文件
