# Curriculum Standard Knowledge Model

## 概述

课程标准知识模型将以《普通高中技术与工程课程标准（2017年版2025年修订）》（原文封面写作“日常修订版”）为核心的结构化知识提供给 Expert 使用。原“通用技术”课程于 2025 年更名为“技术与工程”。

## 目录结构

```
curriculum-standard/
├── schema.json                              # 知识模型 Schema
├── standards/
│   └── technology-engineering.json          # 技术与工程课程标准
├── mappings/
│   └── competency-objective-map.json        # 素养→目标→评价映射
└── README.md
```

## 知识模型设计

```
课程标准
  ├── 课程性质与课程理念 (5 条)
  ├── 核心素养 (5 个：技术意识 / 工程思维 / 创新设计 / 图样表达 / 物化能力)
  │   └── 水平维度 (3 级，对应学业质量水平 1~3)
  ├── 课程结构 (必修 2 模块 / 选择性必修 3 系列 8 模块 / 选修 6 模块)
  ├── 内容域 (5 个)
  │   └── 主题 → 内容标准
  ├── 学业质量 (3 个水平)
  └── 学习要求 (知识/技能/素养/工程)
```

> **2025 版关键变化**：必修模块更名为《技术与工程设计 1》《技术与工程设计 2》；选择性必修由旧版模块体系调整为 3 个系列 8 个模块；学业质量由 4 个水平调整为 **3 个水平**（水平 2 = 必修/合格考参照，水平 3 = 必修+选择性必修/等级考依据）。

## Expert 使用方式

| Expert | 使用字段 | 说明 |
|--------|---------|------|
| Curriculum Expert | `coreCompetencies` + `contentDomains` | 提取课标要求 |
| Objective Expert | `mappings/*.objectives` | 素养→目标映射 |
| Assessment Expert | `mappings/*.assessmentIndicators` | 评价指标 |
| Strategy Expert | `teachingSuggestions` | 教学方法建议 |
