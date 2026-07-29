# Quick Start

## 5 分钟快速上手

### 1. 加载 Skill

```typescript
import { loadTeachingDesignSkill } from './skill/SkillLoader';

const skill = await loadTeachingDesignSkill({
  promptRenderer,
  outputGenerator,
  workflowEngine,
  pluginManager,
});
```

### 2. 执行教学设计

```typescript
const result = await workflowEngine.execute('lesson-plan', {
  subject: '技术与工程',
  grade: '高一',
  chapter: '第三章 系统与设计',
  topic: '系统的结构',
  classHours: 3,
  teachingMode: '项目式学习',
});
```

### 3. 导出结果

```typescript
const markdown = await outputGenerator.generate(result, { format: 'markdown' });
console.log(markdown.content);
```

## 输入参数

| 参数 | 必填 | 说明 |
|------|------|------|
| `subject` | ✓ | 学科（固定：技术与工程） |
| `grade` | ✓ | 年级（高一/高二/高三） |
| `chapter` | ✓ | 章节 |
| `topic` | ✓ | 课题 |
| `classHours` | ✓ | 课时数 |
| `teachingMode` | — | 教学模式（项目式学习/探究式学习/合作学习） |

## 输出格式

| 格式 | 用途 |
|------|------|
| Markdown | 教师阅读文档 |
| JSON | 程序消费 |
| DOCX | Word 文档 |
| PPTX | 演示文稿 |
