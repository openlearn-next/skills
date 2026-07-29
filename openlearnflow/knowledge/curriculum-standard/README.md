# Curriculum Standard Knowledge Model

## 概述

课程标准知识模型将以《普通高中技术课程标准（2017年版2020年修订）》为核心的结构化知识提供给 Expert 使用。

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
  ├── 核心素养 (5 个)
  │   └── 水平维度 (4 级)
  ├── 内容域 (3 个)
  │   └── 主题 → 内容标准
  └── 学习要求 (知识/技能/素养/工程)
```

## Expert 使用方式

| Expert | 使用字段 | 说明 |
|--------|---------|------|
| Curriculum Expert | `coreCompetencies` + `contentDomains` | 提取课标要求 |
| Objective Expert | `mappings/*.objectives` | 素养→目标映射 |
| Assessment Expert | `mappings/*.assessmentIndicators` | 评价指标 |
| Strategy Expert | `teachingSuggestions` | 教学方法建议 |
