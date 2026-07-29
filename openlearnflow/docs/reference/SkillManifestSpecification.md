# Skill Manifest Specification

## 概述

Skill Manifest 是 Skill 的唯一元数据文件，包含 Skill 的身份、能力、工作流和依赖信息。

## Manifest 结构

```yaml
# skill.yaml
id: teaching-design
name: Teaching Design Studio
displayName: 教学设计专家
version: 1.0.0
description: 中国普通高中《技术与工程》AI 协同教学设计系统

runtime:
  minVersion: 1.0.0
  maxVersion: 2.0.0

capabilities:
  - id: curriculum-analysis
    name: 课程标准分析
    type: analysis
    file: capabilities/curriculum-analysis.yaml
    
  - id: lesson-design
    name: 教学设计
    type: generation
    file: capabilities/lesson-design.yaml
    
  - id: objective-design
    name: 目标设计
    type: design
    file: capabilities/objective-design.yaml
    
  - id: activity-design
    name: 活动设计
    type: design
    file: capabilities/activity-design.yaml
    
  - id: assessment-design
    name: 评价设计
    type: design
    file: capabilities/assessment-design.yaml
    
  - id: resource-curation
    name: 资源整合
    type: curation
    file: capabilities/resource-curation.yaml
    
  - id: reflection
    name: 教学反思
    type: analysis
    file: capabilities/reflection.yaml

workflows:
  - id: lesson-plan
    name: 课时教学方案
    description: 标准课时教学设计
    file: workflows/lesson-plan.yaml
    
  - id: project-design
    name: 项目式学习方案
    description: PBL 项目教学设计
    file: workflows/project-design.yaml
    
  - id: engineering-design
    name: 工程实践方案
    description: EDP 工程设计教学
    file: workflows/engineering-design.yaml

dependencies:
  skills: []
  runtimes: ["context-engine", "workflow-engine", "prompt-engine", "output-engine"]

permissions:
  - runtime.read
  - runtime.write
  - file.read
  - file.write

metadata:
  author: OpenLearn AI Team
  license: MIT
  language: zh-CN
  locale: zh_CN
  keywords:
    - 技术与工程
    - 教学设计
    - AI 教育
  categories:
    - education
    - teaching-design
    - k12
```

## 字段说明

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `id` | string | ✓ | 全局唯一标识 |
| `name` | string | ✓ | 英文名称 |
| `displayName` | string | ✓ | 显示名称 |
| `version` | semver | ✓ | 语义化版本 |
| `description` | string | ✓ | 功能描述 |
| `runtime.minVersion` | semver | ✓ | 最低 Runtime 版本 |
| `capabilities` | array | ✓ | 能力列表 |
| `workflows` | array | ✓ | 工作流列表 |
| `dependencies` | object | — | 依赖声明 |
| `permissions` | array | ✓ | 权限申请 |
| `metadata` | object | — | 扩展元数据 |
