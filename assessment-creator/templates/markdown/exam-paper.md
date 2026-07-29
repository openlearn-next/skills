# {{MODULE_NAME}} · {{SECTION_TITLE}}

> **适用年级**：{{GRADE_LEVEL}}  
> **预计用时**：{{DURATION}} 分钟  
> **满分**：{{TOTAL_SCORE}} 分  
> **命题范围**：{{KNOWLEDGE_POINTS}}

---

## 一、单选题（每题 {{SINGLE_SCORE}} 分，共 {{SINGLE_TOTAL}} 分）

{{#each single_choice_questions}}
**{{@index_plus_1}}.** {{question_text}}
    A. {{option_a}}  B. {{option_b}}  C. {{option_c}}  D. {{option_d}}

{{/each}}

---

## 二、多选题（每题 {{MULTI_SCORE}} 分，共 {{MULTI_TOTAL}} 分）

> **说明**：每题有两个或两个以上正确答案，全部选对得满分，选对但不全得一半分，有错选不得分。

{{#each multiple_choice_questions}}
**{{@index_plus_1}}.** {{question_text}}（多选）
    A. {{option_a}}  B. {{option_b}}  C. {{option_c}}  D. {{option_d}}{{#if option_e}}  E. {{option_e}}{{/if}}

{{/each}}

---

## 三、判断题（每题 {{TF_SCORE}} 分，共 {{TF_TOTAL}} 分）

> **说明**：正确打"√"，错误打"×"。

{{#each true_false_questions}}
**{{@index_plus_1}}.** {{question_text}}（   ）

{{/each}}

---

## 四、填空题（每空 {{BLANK_SCORE}} 分，共 {{BLANK_TOTAL}} 分）

{{#each fill_in_blank_questions}}
**{{@index_plus_1}}.** {{question_text}}

{{/each}}

---

## 五、简答题（每题 {{SHORT_SCORE}} 分，共 {{SHORT_TOTAL}} 分）

{{#each short_answer_questions}}
**{{@index_plus_1}}.** {{question_text}}

{{/each}}

---

{{#if matching_questions.length}}
## 六、连线题（每题 {{MATCH_SCORE}} 分，共 {{MATCH_TOTAL}} 分）

{{#each matching_questions}}
**{{@index_plus_1}}.** 将左右两组内容正确连线：

| 左列 | 右列 |
|------|------|
{{#each pairs}}
| {{@index_plus_1}}. {{left}} | {{right_label}}. {{right}} |
{{/each}}

{{/each}}
{{/if}}
