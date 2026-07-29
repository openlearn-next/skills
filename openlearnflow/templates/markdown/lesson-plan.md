# {{ title }}

> {{ subtitle }}

---

## 一、教学设计概览

| 项目 | 内容 |
|------|------|
| **学科** | {{ subject }} |
| **年级** | {{ grade }} |
| **学期** | {{ semester }} |
| **章节** | {{ chapter }} |
| **课题** | {{ topic }} |
| **课型** | {{ lessonType }} |
| **课时** | {{ classHours }} 课时 |
| **教学模式** | {{ teachingMode }} |

## 二、课程标准分析

### 2.1 课标定位

{{ curriculum.coursePosition }}

### 2.2 内容要求

{% for req in curriculum.contentRequirements %}
- {{ req }}
{% endfor %}

### 2.3 核心素养

| 素养维度 | 在本课中的体现 |
|---------|--------------|
{% for literacy in curriculum.coreCompetencies %}
| {{ literacy.name }} | {{ literacy.manifestation }} |
{% endfor %}

### 2.4 学业质量

**目标水平:** 水平 {{ curriculum.academicQuality.level }}

{{ curriculum.academicQuality.description }}

## 三、教材分析

### 3.1 章节地位

{{ textbook.chapterPosition }}

### 3.2 知识结构

{{ textbook.knowledgeStructure }}

### 3.3 教学重难点

**重点:**
{% for point in textbook.keyPoints %}
- {{ point }}
{% endfor %}

**难点:**
{% for point in textbook.difficultPoints %}
- {{ point }}
{% endfor %}

## 四、知识图谱

### 4.1 知识网络

{{ knowledge.knowledgeNetwork }}

### 4.2 核心概念

{% for concept in knowledge.coreConcepts %}
- **{{ concept.name }}** — {{ concept.connections | join(' / ') }}
{% endfor %}

### 4.3 工程案例

{% for case in knowledge.engineeringCases %}
- {{ case }}
{% endfor %}

## 五、学情分析

### 5.1 已有基础

{{ student.existingExperience }}

### 5.2 学习困难

{% for difficulty in student.learningDifficulties %}
- {{ difficulty }}
{% endfor %}

### 5.3 分层策略

{{ student.tieredStrategy }}

## 六、教学目标

### 6.1 知识目标
{% for obj in goal.knowledgeObjectives %}
- {{ obj }}
{% endfor %}

### 6.2 技能目标
{% for obj in goal.skillObjectives %}
- {{ obj }}
{% endfor %}

### 6.3 工程实践目标
{% for obj in goal.engineeringObjectives %}
- {{ obj }}
{% endfor %}

### 6.4 创新目标
{% for obj in goal.innovationObjectives %}
- {{ obj }}
{% endfor %}

## 七、教学策略

**教学模式:** {{ strategy.teachingModel }}

**教学方法:**
{% for method in strategy.teachingMethods %}
- {{ method }}
{% endfor %}

**选择依据:** {{ strategy.selectionRationale }}

## 八、教学过程

{% for stage in activity.learningTasks %}
### {{ stage.name }}

| 项目 | 内容 |
|------|------|
| **EDP 阶段** | {{ stage.edpPhase }} |
| **目标** | {{ stage.objective }} |
| **真实情境** | {{ stage.realWorldContext }} |
| **驱动问题** | {{ stage.problem }} |
| **时长** | {{ stage.durationMinutes }} 分钟 |

**教师活动:**
{% for act in stage.teacherSupport %}
- {{ act }}
{% endfor %}

**学生活动:**
{% for act in stage.studentActivities %}
- {{ act }}
{% endfor %}

{% endfor %}

## 九、评价方案

### 9.1 评价框架

{{ assessment.assessmentFramework }}

### 9.2 评价方式

{% for method in assessment.assessmentMethods %}
- {{ method }}
{% endfor %}

### 9.3 评价量规 (Rubric)

{% for rubric in assessment.rubrics %}
#### {{ rubric.name }}

| 维度 | 权重 | 优秀(4) | 良好(3) | 合格(2) | 待改进(1) |
|------|------|---------|---------|---------|----------|
{% for criteria in rubric.criteria %}
| {{ criteria.name }} | {{ criteria.weight }}% | {{ criteria.levels[0].description }} | {{ criteria.levels[1].description }} | {{ criteria.levels[2].description }} | {{ criteria.levels[3].description }} |
{% endfor %}

{% endfor %}

## 十、教学资源

### 10.1 教学资源清单
{% for res in resource.teachingResources %}
- {{ res }}
{% endfor %}

### 10.2 板书设计

{{ resource.boardDesign }}

### 10.3 PPT 大纲

{{ resource.pptOutline }}

## 十一、教学反思

### 11.1 反思框架

{{ reflection.reflectionFramework }}

### 11.2 预设反思问题

{% for q in reflection.presetQuestions %}
- {{ q }}
{% endfor %}

### 11.3 改进建议

{% for s in reflection.improvementSuggestions %}
- {{ s }}
{% endfor %}

## 十二、质量审核

**综合评分:** {{ review.overallScore }} / 100

**亮点:**
{% for s in review.strengths %}
- {{ s }}
{% endfor %}

**待改进:**
{% for w in review.weaknesses %}
- {{ w }}
{% endfor %}

**发布状态:** {% if review.readyToPublish %}可发布{% else %}需要修改{% endif %}

---

> 本文档由 OpenLearn Teaching Design Studio 自动生成
> 生成时间: {{ generatedTime }}
> 工作流: {{ workflow }}
> 版本: {{ version }}
