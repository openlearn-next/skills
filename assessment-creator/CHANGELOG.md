# Changelog

## [1.0.1] - 2026-08-31

### Fixed

- 修复 `SKILL.md` 中 13 条质量审查规则分级与处理动作的表述差异
- 统一 `config/knowledge.config.json` 中前置依赖字段名称为 `prerequisites`
- 修复 `config/quality-rules.json` 中 R03 的审查处理动作为 `auto_fix_if_minor`
- 对齐 `evaluation/review-checklist.json` 中 PRE-03 的单批题量上限检查描述

## [1.0.0] - 2026-07-29

### Added

- 首次发布 assessment-creator 试题生成器技能
- 支持六种纸笔测试题型：单选、多选、判断、填空、简答、连线
- 三个 Expert 角色协作流水线：出题 Expert、审题 Expert、排版 Expert
- 13 条质量审查规则（R01-R13），覆盖正确性、清晰度、有效性、规范性、伦理
- 数据与编码模块知识点库（12 个知识点），每个含参数化出题模板和常见错误
- 双入口交互模式：单轮快捷指令 + 多轮引导
- 分批出题机制（每批 5 道），支持中途调整
- 教学解析级别输出（步骤推理 + 核心原理 + 教学提示）
- 变体生成策略（参数采样 + 模板轮换）
- 外部 Skill 软依赖降级机制
- Markdown 试卷模板和答案卷模板
- 8 组测试用例
