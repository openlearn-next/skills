# Edu Skills Collection

> 面向中国 K-12 教育的 AI 协同教学 Skills 合集

## 已收录 Skill

| Skill | 学科 | 年级 | 版本 | 说明 |
|-------|------|------|------|------|
| [openlearnflow](openlearnflow/) | 技术与工程 | 高一~高三 | v1.1.0 | 教学设计 + PPT 课件 + 互动网页 |

## 目录结构

```
edu-skills/
├── manifest.json       # 合集清单（skill 索引 + 共享资源 + 分类规划）
├── openlearnflow/      # 技术与工程教学设计 skill
│   ├── SKILL.md        #   AI agent 入口指令
│   ├── manifest.json   #   子 skill 清单
│   ├── prompts/        #   Expert Prompt 模板
│   ├── workflows/      #   工作流定义
│   ├── knowledge/      #   领域知识库
│   └── ...
└── workspace/          # 临时工作区（gitignore）
```

## 新增 Skill

在 `edu-skills/` 下创建新目录，沿用 `openlearnflow/` 的结构模板：

```
edu-skills/
├── openlearnflow/        # 已有
├── math-exercises/       # 示例：数学练习生成
│   ├── SKILL.md
│   ├── manifest.json
│   ├── prompts/
│   └── ...
└── chemistry-lab/        # 示例：化学实验设计
    ├── SKILL.md
    ├── manifest.json
    └── ...
```

新 skill 完成后，在根 `manifest.json` 的 `skills` 数组中注册即可被合集发现。

## 规划中的 Skill

| 方向 | 说明 |
|------|------|
| 练习生成 | 各学科自动出题、组卷、答案解析 |
| 知识图谱 | 学科知识体系的结构化建模 |
| 学情评估 | 认知诊断与个性化学习路径推荐 |
| 资源整合 | 跨平台教学资源的发现与适配 |
