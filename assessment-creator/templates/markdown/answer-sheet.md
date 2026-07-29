# {{MODULE_NAME}} · {{SECTION_TITLE}} — 参考答案

---

## 一、单选题

| 题号 | 答案 | 分值 |
|------|------|------|
{{#each single_choice_questions}}
| {{@index_plus_1}} | {{correct_option}}. {{#if option_text}}{{option_text}}{{/if}} | {{score}}分 |
{{/each}}

{{#each single_choice_questions}}
### 第{{@index_plus_1}}题解析

**答案**：{{correct_option}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}

## 二、多选题

| 题号 | 答案 | 分值 |
|------|------|------|
{{#each multiple_choice_questions}}
| {{@index_plus_1}} | {{correct_options}} | {{score}}分 |
{{/each}}

{{#each multiple_choice_questions}}
### 第{{@index_plus_1}}题解析

**答案**：{{correct_options}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}

## 三、判断题

| 题号 | 答案 | 分值 |
|------|------|------|
{{#each true_false_questions}}
| {{@index_plus_1}} | {{answer}} | {{score}}分 |
{{/each}}

{{#each true_false_questions}}
### 第{{@index_plus_1}}题解析

**答案**：{{answer}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}

## 四、填空题

| 题号 | 答案 | 分值 |
|------|------|------|
{{#each fill_in_blank_questions}}
| {{@index_plus_1}} | {{answer}} | {{score}}分 |
{{/each}}

{{#each fill_in_blank_questions}}
### 第{{@index_plus_1}}题解析

**答案**：{{answer}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}

## 五、简答题

{{#each short_answer_questions}}
### 第{{@index_plus_1}}题

**参考答案**：
{{answer}}

**评分要点**：
{{#each scoring_points}}
{{@index_plus_1}}. {{point}}（{{score}}分）
{{/each}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}

{{#if matching_questions.length}}
## 六、连线题

{{#each matching_questions}}
### 第{{@index_plus_1}}题

| 题号 | 正确答案 |
|------|----------|
{{#each pairs}}
| {{@index_plus_1}} | {{right_label}} |
{{/each}}

**解析**：{{analysis.steps}}

**原理**：{{analysis.principle}}

**教学提示**：{{analysis.teaching_tip}}

---

{{/each}}
{{/if}}

---

## 📊 总分统计

| 题型 | 题数 | 每题分值 | 小计 |
|------|------|----------|------|
| 单选题 | {{SINGLE_COUNT}} | {{SINGLE_SCORE}}分/题 | {{SINGLE_TOTAL}}分 |
{{#if MULTI_COUNT}}| 多选题 | {{MULTI_COUNT}} | {{MULTI_SCORE}}分/题 | {{MULTI_TOTAL}}分 |{{/if}}
{{#if TF_COUNT}}| 判断题 | {{TF_COUNT}} | {{TF_SCORE}}分/题 | {{TF_TOTAL}}分 |{{/if}}
{{#if BLANK_COUNT}}| 填空题 | {{BLANK_COUNT}} | {{BLANK_SCORE}}分/空 | {{BLANK_TOTAL}}分 |{{/if}}
{{#if SHORT_COUNT}}| 简答题 | {{SHORT_COUNT}} | {{SHORT_SCORE}}分/题 | {{SHORT_TOTAL}}分 |{{/if}}
{{#if MATCH_COUNT}}| 连线题 | {{MATCH_COUNT}} | {{MATCH_SCORE}}分/题 | {{MATCH_TOTAL}}分 |{{/if}}
| **合计** | **{{TOTAL_COUNT}}** | | **{{TOTAL_SCORE}}分** |
