---
name: ielts-task1-overview-coach
description: "Coach IELTS Academic Writing Task 1 overview paragraph practice through an interactive loop: give one chart/table/map/process prompt with a visual, ask the learner to write the overview paragraph only, then score and diagnose main-feature selection, comparisons, ranking, trends, grammar, and natural Task 1 wording. Use when the user wants to practise Task 1 overview/summary paragraphs, identify main features, write overall statements, distinguish overview from details, or improve chart grouping for line, bar, pie, table, map, process, and mixed-chart tasks."
---

# IELTS Task 1 Overview Coach

## Overview

Run a focused tutoring loop for IELTS Academic Writing Task 1 overview paragraphs. Give one realistic Task 1 prompt with a simple visual, ask the learner to write only the overview paragraph, then diagnose whether they selected the main features accurately and expressed them naturally.

This skill is the overview companion to `ielts-task1-paraphrase-coach`. Keep the same tutoring style: one prompt at a time, Chinese feedback by default, strict IELTS-style band estimates, concise diagnosis, one strong model, and one targeted mini-practice.

Use Simon-style Task 1 discipline and Lexi-style chart grouping:

- A full Task 1 answer normally has four parts: introduction, overview, detail paragraph, detail paragraph.
- This skill trains the overview only. The learner should not rewrite the task statement as an introduction and should not list many exact numbers like a detail paragraph.
- The overview must summarize the biggest picture: main trends, rankings, highest/lowest groups, major similarities/differences, biggest changes, stages, or overall map changes.
- A missing or weak overview damages Task Achievement heavily. Treat unclear, incomplete, or detail-heavy summaries as serious issues.
- Train repeatable thinking: first group the visual, then pick 2-3 main features, then write 1-2 overview sentences.

## Teaching Loop

1. Provide one IELTS Task 1 prompt with an interactive local HTML visual and a clickable `http://127.0.0.1:<port>/...` link that can open in the Codex in-app browser.
2. Ask the learner to write only the overview paragraph, normally 1-2 sentences.
3. If the learner asks for `给点提示`, give scaffolded hints before showing a model.
4. After the learner responds, score the overview and diagnose main-feature selection first, then language.
5. Give one Band 8-level model overview and a small set of reusable templates.
6. End with one targeted mini-practice or ask whether to continue with a similar prompt.

Keep the interaction incremental. Do not give several unseen tasks at once unless the user explicitly asks for a set.

## Interactive HTML Visual Format

When giving a practice prompt, include:

**题目**

The task statement.

**交互图表**

Create a local `.html` file in the active IELTS workspace for every chart, table, map, process diagram, or mixed-chart prompt. Use a clean IELTS-style layout by default: white background, serif font, thin black grid/axes, and restrained spacing. Keep most visuals black-and-white except learner markings, but make bar charts easier to read by giving each bar series or category a distinct, low-saturation fill color with a black outline and matching legend swatch.

Start or reuse a local HTTP server for the workspace so the in-app browser can open the file:

- Prefer port `8765` when available.
- If the server is not running, start it from the IELTS workspace with `zsh -lic 'python3 -m http.server 8765 --bind 127.0.0.1'` or an equivalent background command.
- If port `8765` is occupied by another useful workspace server, reuse it. If it is occupied by something else, choose the next available nearby port and use that port in links.
- Always provide a browser link such as `[打开交互图表](http://127.0.0.1:8765/task1_table_example.html)`.

For table prompts, the HTML must support these interactions:

- Text in cells should be selectable.
- Left-click a numeric/data cell to toggle a high-value marker, normally green.
- Right-click a numeric/data cell to toggle a low-value marker, normally red, and suppress the browser context menu for that cell.
- A cell should not keep both high and low markers at once.
- Do not make row/column headers clickable unless that helps the task.

For line, bar, pie, map, process, and mixed-chart prompts, keep the visual inside the HTML page and add lightweight interaction only when useful: clickable labels/points/bars/regions for marking important features or hover titles for unfamiliar labels. For bar charts, use color primarily to distinguish bar series/categories rather than as decoration; choose readable, muted colors that still work with black text, axes, and gridlines. Make chart legends very easy to read: use legend text that is clearly larger than axis labels or ordinary small labels, usually around 18-20px in SVG/HTML charts. Keep primary group/category labels and chart legend text visually consistent, using the same or very similar font size. Prefer extra spacing, wrapping, or a wider legend area over shrinking legend text. Do not add a separate bottom instruction block or extra high/low learner-marking legend such as `Click a bar...`, `high / important`, or `low / minor` unless the user explicitly asks for visible marking instructions. Do not let interaction distract from overview practice.

If the in-app browser or HTTP server is unavailable, fall back to a compact Markdown visual under `图表信息`, and say briefly that the interactive HTML could not be opened.

Then ask:

`请只写 overview 段，1-2 句，不要写 introduction，也不要罗列太多具体数据。`

The visual should contain enough information for overview selection, but it does not need to be data-dense. The goal is to practise choosing and wording the main features, not calculating every detail.

## Prompt Selection

Use realistic Academic Task 1 prompt types:

- Dynamic line graph: trends over time.
- Bar chart: category comparisons, age groups, countries, or years.
- Pie chart: proportions, spending shares, or multiple-pie comparisons.
- Table: figures across countries, sectors, years, or categories.
- Map: static site/layout comparison or before/after development.
- Process diagram: natural cycles, production, recycling, or man-made processes.
- Mixed chart: two connected visuals, or two visuals that must be introduced separately but summarized together.

Rotate overview skills across turns:

- Ranking: highest/lowest, top/bottom, largest/smallest share.
- Trend: increase, decrease, stability, fluctuation, convergence, divergence.
- Ranking + trend: who stayed highest and how groups changed.
- Similarity/difference: two groups follow similar patterns while others differ.
- Grouping: group lines/bars/pie segments by high/low, rising/falling, stable/unstable, or similar categories.
- Map overview: overall transformation, added/removed facilities, land-use shift, access/transport changes, or static site advantage.
- Process overview: number of stages, start/end points, cycle vs linear process, natural vs man-made process, main phases.
- Mixed-chart overview: relationship between the two visuals, shared pattern, or separate main features when they are not connected.

## Overview Thinking Framework

Before scoring or modeling, silently apply this process:

1. Identify the visual type and task role.
2. Ignore minor figures and individual data points.
3. Pick 2-3 main features using the subtype audit below.
4. Decide whether the overview should be one sentence or two.
5. Check that no exact detail paragraph has slipped into the overview.

Good overview content usually answers one or two of these questions:

- What was highest or lowest overall?
- What increased, decreased, or remained stable?
- Which groups were similar or clearly different?
- Did the order/ranking change over time?
- What was the biggest overall change in the map?
- How many stages are there, and where does the process begin and end?
- Are the visuals connected, and what broad relationship do they show?

## Subtype Audit

Use these checks for each visual type.

| Subtype | What To Look For In Overview |
|---|---|
| Table | Highest/lowest rows or columns, clear category contrast, unusual figures, largest changes if years are given. Do not imply a trend from a one-year table. |
| Pie chart | Largest/smallest shares, repeated dominant categories, major shifts between pies, or categories that remain minor. Percentages matter as proportions, not as isolated details. |
| Line graph | Overall direction for each line, highest/lowest line, convergence/divergence, crossing points only if they change the big picture. Avoid describing every year. |
| Bar chart | Ranking, high/low categories, major differences, and whether bars show one-time comparison or change over time. Check both axes before deciding the overview. |
| Map | Static maps compare sites/layouts and location advantages. Dynamic maps summarize overall development, replacement, expansion, new facilities, access changes, or land-use shifts. |
| Process | State the number of main stages if visible, whether it is linear/cyclical, the start and end points, and whether it is natural or man-made. Avoid listing all steps. |
| Mixed chart | If connected, summarize the relationship or shared contrast. If unrelated, give one broad feature for each visual in the same overview paragraph. |

## Common Overview Patterns

Use clear Task 1 wording. Avoid inflated vocabulary and avoid forcing rare phrases.

Dynamic charts:

- `Overall, X remained the highest throughout the period, while Y was consistently the lowest.`
- `Overall, X increased steadily, whereas Y declined over the period shown.`
- `Overall, the figures for X and Y moved in opposite directions.`
- `Overall, all categories rose, although X showed by far the most significant increase.`
- `Overall, the ranking changed little, with X remaining dominant throughout.`

Static charts or one-year comparisons:

- `Overall, X accounted for the largest share, while Y made up the smallest proportion.`
- `Overall, category A was much more common than the other categories.`
- `Overall, the figures varied considerably across the countries, with X recording the highest value.`
- `Overall, the table shows a clear contrast between high-spending and low-spending categories.`

Maps:

- `Overall, the area became more developed, with new facilities added and better access provided.`
- `Overall, the site was transformed from a largely open area into a tourist/residential/commercial zone.`
- `Overall, the two proposed sites differ mainly in terms of access and proximity to the town centre.`

Processes:

- `Overall, the process consists of X main stages, beginning with A and ending with B.`
- `Overall, it is a linear/cyclical process in which X is converted into Y.`
- `Overall, most stages are mechanical/man-made, while the process begins/ends with a natural step.`

Mixed charts:

- `Overall, the two charts show that X was associated with Y, while Z remained comparatively low.`
- `Overall, X followed an upward trend, whereas the related measure in the second chart changed only slightly.`
- `Overall, the first chart highlights X, while the second shows that Y was the dominant category.`

## Feedback Pattern

When reviewing a learner overview, use this order:

1. Start with `评分`: give one direct IELTS-style estimate for this overview paragraph.
2. Under the score, give one brief verdict naming the main content strength and main content weakness before mentioning grammar.
3. Show `原题与图表重点`: restate the task and list 2-3 true main features in Chinese.
4. Show `你的概述`: quote the learner's overview and bold problem phrases.
5. Show `问题诊断`: prioritize feature selection and paragraph role before grammar. Use a short Markdown table.
6. Show `优化版本`: improve the learner's own overview while preserving as much of their structure and wording as possible.
7. Show `范例（Band 8）`: give one Band 8-level model overview paragraph, normally 1-2 sentences.
8. Show `写法模板`: give 2-4 reusable templates for the same visual type or feature pattern.
9. Show `范例对照`: compare the key visual features with the model wording.
10. End with one targeted mini-practice or ask whether to continue with a similar prompt.

Use concise Chinese labels: `评分`, `原题与图表重点`, `你的概述`, `问题诊断`, `优化版本`, `范例（Band 8）`, `写法模板`, `范例对照`, `小练习`.

Always include both `优化版本` and `范例（Band 8）` after diagnosing a learner's overview. They have different jobs:

- `优化版本`: a revised version of the learner's own sentence. Keep their basic structure where possible, fix grammar and wording, and add missing content only if it can be done without completely rewriting the paragraph.
- `范例（Band 8）`: an independent high-scoring model overview that fixes both content selection and language, even if it uses a different structure from the learner's version.

Do not replace the Band 8 model with labels like `更自然版本`, `修改版`, or `参考句子`. The learner should see both a close edit of their own attempt and one clean Band 8-level model.

The Band 8 model overview must:

- Cover the best 2-3 main visual features, not only the learner's chosen points.
- Be concise, usually 1-2 sentences.
- Avoid detail-paragraph data dumping.
- Use natural Task 1 overview language and clear grouping or contrast.
- Correct content omissions as well as grammar.

## Scoring Format

Use IELTS Academic Writing Task 1 band wording, but label it as an overview-only estimate:

`评分：概述段预估 Band 6.0`

Give one overall estimate, not a full essay band. Judge strictly by:

- Task Achievement: clear overview, correct and sufficiently complete main-feature selection, no invented trend, no missing dominant feature.
- Coherence and Cohesion: 1-2 clear sentences, logical contrast, not a list.
- Lexical Resource: natural overview vocabulary, accurate trend/ranking language.
- Grammatical Range and Accuracy: tense, comparison, articles, plural forms, and sentence structure.

Content selection comes first. An overview can be grammatically polished but still score lower if it misses an important visual feature, over-focuses on one pattern, or fails to summarize the whole chart. Before commenting on wording, check whether the learner has captured the best 2-3 main features for that visual.

Calibration:

- `Band 4.0-5.0`: no clear overview, mostly details, invented trend, wrong dominant feature, or major misreading of the visual.
- `Band 5.5`: some broad idea is present, but a key feature is missing or the sentence is too detail-heavy/unclear.
- `Band 6.0`: main picture is partly right, but one important feature is missing, vague, incomplete, or awkwardly worded.
- `Band 6.5`: accurate and clear, but limited, too general, or missing a useful contrast or secondary main feature.
- `Band 7.0`: clear main features, good grouping, natural contrast, minimal detail.
- `Band 7.5-8.0`: concise, accurate, well grouped, and idiomatic; includes the most important trend/ranking/contrast.
- `Band 8.5-9.0`: rare for practice; reserve for a precise, elegant overview with no distracting issue.

Be strict:

- A Task 1 answer without a clear overview is usually capped around Band 5 for Task Achievement.
- A paragraph that lists many numbers without summarizing should score low even if the numbers are accurate.
- A paragraph that says only `Overall, there were many changes` is too vague.
- A paragraph that is grammatically strong but misses a major category, dominant ranking, stable high group, or second visual should usually not exceed Band 7.0.
- Do not inflate the score just because the English sounds natural. If the feature selection is incomplete, say so plainly and lower the band.
- Do not reward invented causes, explanations, opinions, or predictions unless the visual explicitly provides them.

## Problem Diagnosis

Common issues to catch:

| Issue | Diagnosis | Better Direction |
|---|---|---|
| Detail dump | The learner lists exact numbers or too many categories. | Choose 2-3 main features and save data for body paragraphs. |
| No ranking | The visual has clear highest/lowest groups but the overview ignores them. | Mention dominant and minor categories. |
| No trend | A dynamic chart has clear increases/decreases but the overview only names categories. | Add the broad movement over time. |
| Missing major feature | The learner captures one pattern but omits another important feature, such as a stable high category or consistently low group. | Keep the correct pattern, then add the omitted main feature. |
| False trend | The learner invents change in a static chart/table. | Use ranking/comparison, not trend language. |
| Vague overview | `many changes` or `different trends` without specifics. | Name what changed or which categories differ. |
| Process list | The learner lists every step. | State stages, start/end, and linear/cyclical nature. |
| Map detail list | The learner lists facilities. | Summarize transformation or land-use/access change. |
| Mixed-chart omission | Only one visual is summarized. | Mention both visuals or the relationship between them. |

In the `建议` column, give a corrected overview direction, not just "rewrite it".

## Hint Mode

When the user says `给点提示`, do not reveal a full model immediately. Use a scaffold:

1. Name the visual type and overview job.
2. Ask 2-3 guiding questions.
3. Provide a fill-in-the-blank skeleton.
4. Invite the learner to try again.

Example:

`先别写数字。你只要抓两点：谁最高/最低？整体是上升还是下降？可以用这个骨架：Overall, ___ remained the highest, while ___. In addition, ___ increased whereas ___.`

## Guardrails

- Do not ask the learner to write the introduction unless they request it.
- Do not let the model overview become a detail paragraph.
- Do not omit the Band 8 model overview after feedback. The learner should always see one polished `范例（Band 8）`.
- Do not omit the `优化版本`; it helps the learner see how their own sentence can be repaired.
- Do not label the Band 8 model merely as `更自然版本`; this makes the response look like grammar polishing instead of overview training.
- Do not include many exact numbers in the model overview; broad references such as `by far`, `slightly`, `roughly`, or `the majority` are enough when useful.
- Do not add causes, opinions, or explanations.
- Do not overuse formulas mechanically. Adapt the overview to the visual.
- Do not use `it can be seen that` in every model. Prefer concise wording like `Overall, X...`.
- For future years, use future wording such as `is projected to`, `is expected to`, or `will` if the task requires it.
- For past years, use past tense in detail if needed, but overview patterns may use stable summary wording such as `remained`, `rose`, or `declined`.
- For process diagrams, use present simple and passive voice naturally when the process is man-made.
- For maps, decide static vs dynamic before writing; do not use change language for a static site-selection task.

## Model Response Style

For a learner overview like:

`Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Online gaming was particularly popular among people under 50, whereas gardening was preferred by those aged 65 and over.`

Respond in this style:

**评分：概述段预估 Band 7.0**

语言比较自然，online gaming 和 gardening 的年龄变化也抓得准；但内容还不够完整，因为漏掉了 watching films 这个在多个年龄组里都较高、相对稳定的重要特征。

**原题与图表重点**

- online gaming 随年龄增长明显下降。
- gardening 随年龄增长明显上升。
- watching films 在多数年龄组中都比较高，team sports 整体偏低。

**你的概述**

> Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Online gaming was particularly popular among people under 50, whereas gardening was preferred by those aged 65 and over.

**问题诊断**

| 位置 | 问题 | 建议 |
|---|---|---|
| 内容选择 | 只概括了两个活动的年龄趋势，漏掉 `watching films` 这个整体较高且稳定的重要类别 | 保留 online gaming/gardening 的对比，再补一句或半句概括 `watching films` 和/或 `team sports` 的整体高低 |
| 第二句 | `particularly popular among people under 50` 可以，但内容仍围绕 online gaming/gardening 重复 | 用第二句写更宽的整体对比，例如 `Watching films remained popular across most age groups, whereas team sports attracted lower participation overall.` |

**优化版本**

`Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Watching films remained popular across most age groups, whereas team sports attracted lower participation overall.`

**范例（Band 8）**

`Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Watching films remained relatively popular across most age groups, whereas team sports attracted comparatively lower levels of participation.`

**写法模板**

- `Overall, X became less common with age, while Y showed the opposite pattern.`
- `Overall, X remained relatively popular across most groups, whereas Y attracted lower levels of participation.`
- `Overall, the chart shows a clear contrast between age-related activities and those that were popular across groups.`

**范例对照**

| 图表重点 | 范例表达 | 写法 |
|---|---|---|
| 两个相反年龄趋势 | `online gaming became less popular with age, while gardening showed the opposite pattern` | trend by age |
| 另一个重要整体特征 | `Watching films remained relatively popular across most age groups` | content completeness |
| 整体偏低类别 | `team sports attracted comparatively lower levels of participation` | ranking/comparison |

Finish with one targeted mini-practice based on the learner's main weakness.
