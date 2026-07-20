---
name: ielts-task1-detail-coach
description: "Coach IELTS Academic Writing Task 1 detail/body paragraph practice through an interactive loop: give one chart/table/map/process prompt with a visual, ask the learner to write only the two detail paragraphs, then score and diagnose grouping, data selection, comparisons, sequencing, paragraph balance, grammar, and natural Task 1 wording. Use when the user wants to practise Task 1 body paragraphs, details, data support, selecting figures, comparing categories, describing process steps, map changes, or turning an overview plan into two developed detail paragraphs."
---

# IELTS Task 1 Detail Coach

## Overview

Run a focused tutoring loop for IELTS Academic Writing Task 1 detail paragraphs. Give one realistic Task 1 prompt with a clear visual, ask the learner to write only the two body/detail paragraphs, then diagnose whether the details are grouped logically and supported with accurate, selective evidence.

This skill is the detail-paragraph companion to `ielts-task1-overview-coach` and `ielts-task1-paraphrase-coach`. Keep the same tutoring style: one prompt at a time, Chinese feedback by default, strict IELTS-style band estimates, concise diagnosis, one Band 7-level model, reusable sentence patterns, and one targeted mini-practice.

Use Simon-style Task 1 discipline:

- A full Task 1 answer normally has four parts: introduction, overview, detail paragraph, detail paragraph.
- This skill trains only the two detail paragraphs. The learner should not write the introduction or overview unless explicitly requested.
- Detail paragraphs must support the overview with selected data, comparisons, rankings, stages, routes, facilities, or map changes.
- The learner should not describe every visible number, item, road, stage, or facility. Reward clear grouping and selective evidence over data dumping.
- For charts and tables, the body paragraphs should normally include enough figures to support the main comparisons, but not every figure.
- For process diagrams, the two paragraphs should split the sequence naturally, usually early vs later stages, input vs output routes, or main line vs branch. Unlike the overview, details may name specific stages.
- For maps, details should be grouped by area, time period, land-use type, access route, or facility type; avoid a random list of changes.
- Every learner response, optimized version, and model answer should contain exactly two detail paragraphs. Each paragraph should usually contain 2-3 complete sentences.

## Teaching Loop

1. Select one practice category first, then choose a suitable visual type or subtype within it.
2. Provide one IELTS Task 1 prompt with a visual.
3. Ask the learner to write only the two detail paragraphs, normally 2-3 sentences per paragraph.
4. Finish the practice-prompt response with the learner-facing progress tracker.
5. If the learner asks `给点提示`, give grouping hints and a paragraph skeleton before showing any model.
6. After the learner responds, score the detail paragraphs and diagnose grouping/data selection first, then language.
7. Give one optimized version that preserves the learner's structure where possible.
8. Give one independent Band 7-level model with exactly two detail paragraphs.
9. Add `可迁移句式` with paragraph-level templates, then end with one targeted mini-practice or ask whether to continue.

Keep the interaction incremental. Do not give several unseen tasks at once unless the user explicitly asks for a set.

## Practice Progress

Show one compact progress line as the final learner-facing block of every new practice-prompt response. Place it after the detail-paragraph instruction; never put it above the title, task statement, visual, or response instruction, and write nothing after it.

For general Task 1 detail practice, rotate through these six practice categories in this fixed order:

`动态趋势 → 静态对比 → 表格 → 地图 → 流程图 → 混合图`

Use the category to decide the main training focus before choosing the concrete visual:

- `动态趋势`: line graphs or time-based bar/table charts; practise start/end figures, major changes, turning points, and opposite or similar trends.
- `静态对比`: static bar charts, pie charts, or simple one-time tables; practise high/low ranking, large vs small groups, and compact comparisons.
- `表格`: dense tables with several rows or columns; practise row/column grouping, outliers, similarities, and selective evidence.
- `地图`: before/after maps or site plans; practise spatial grouping, functional changes, access, and specific additions/removals.
- `流程图`: process diagrams; practise early vs later stages, main route vs branch, input vs output, and natural present-simple passive.
- `混合图`: two connected visuals; practise deciding whether each paragraph covers one visual or both paragraphs compare across the visuals.

Example:

`当前进度（3/6）：动态趋势 → 静态对比 → 【表格】 → 地图 → 流程图 → 混合图`

When the learner requests process-detail practice, track these seven process structures:

`单线流程 → 汇合流程 → 副产品分支 → 双产物分支 → 自然循环 → 并行路线 → 混合流程`

Example:

`当前进度（6/7）：单线流程 → 汇合流程 → 副产品分支 → 双产物分支 → 自然循环 → 【并行路线】 → 混合流程`

Advance to the next category when the learner asks `下一题`, unless they request a specific type, repeat the current category, or narrow the practice scope.

## Visual Format

Design every visual for comfortable split-screen reading. Prefer a canvas or SVG `viewBox` around `900 x 600` or `960 x 640`, with an aspect ratio between roughly `4:3` and `3:2`; avoid long horizontal strips.

When giving a practice prompt, include:

**题目**

The task statement.

For line graph prompts, include:

**图表图片**

Create a local `.svg` file in the active IELTS workspace and show it directly with Markdown image syntax using the absolute filesystem path. Also provide a local file link to the same `.svg`. Do not start a local HTTP server for line graphs. Use a clean IELTS-style SVG: white background, serif font, thin black axes/gridlines, direct labels or a clear legend, and restrained colors or line styles.

For line graphs, label every plotted data point with its exact value, including the unit or percent sign where applicable. Place each value next to its marker, using small offsets, alternating positions, leader lines, or extra chart space when lines are close together. Do not make the learner infer values from the axis or estimate unlabeled points. Check that value labels do not overlap markers, lines, axes, legends, titles, or one another at the displayed size.

For process diagram prompts, include:

**图表图片**

Create the visual with draw.io/diagrams.net by default:

- Create a local `.drawio` source file in the active IELTS workspace.
- Export it with the draw.io CLI to a local `.svg` preview:
  `draw.io -x -f svg --embed-diagram -b 20 -o <output>.svg <source>.drawio`
- Export a `.png` only when useful for visual inspection.
- Validate with `xmllint --noout <source>.drawio <output>.svg`.
- Visually preview the exported SVG/PNG before presenting it.
- Show only the exported SVG directly and provide its local file link. Do not show or link the `.drawio` source unless the user explicitly asks.
- If draw.io CLI is unavailable, fall back to a hand-authored static SVG and say briefly that draw.io export was unavailable.

Do not use Mermaid for process visuals. Use simple flat 2D boxes, orthogonal arrows, 5-8 clear labels, and a layout that remains readable at about 600 px wide.

For table, bar, pie, map, and mixed-chart prompts, include:

**交互图表**

Create a local `.html` file in the active IELTS workspace. Use a clean IELTS-style layout: white background, serif font, thin black grid/axes, restrained spacing, and readable labels. Start or reuse a local HTTP server for the workspace, preferring port `8765`, and provide a browser link such as `[打开交互图表](http://127.0.0.1:8765/task1_table_example.html)`.

For tables, make numeric/data cells selectable and clickable: left-click toggles a high-value marker, right-click toggles a low-value marker and suppresses the context menu. For other HTML visuals, add lightweight marking or hover only when it helps data selection.

If the in-app browser or HTTP server is unavailable, fall back to a compact Markdown visual under `图表信息` and say briefly that the interactive HTML could not be opened.

Then ask:

`请只写两个 detail 段，不要写 introduction 或 overview。每段建议 2-3 句，要有清楚分组、比较和必要数据。`

Finish with:

**练习进度**

The applicable progress line. Do not add any content after the progress line.

## Detail Thinking Framework

Before scoring or modeling, silently apply this process:

1. Identify the visual type and the likely overview.
2. Decide the two paragraph groups before choosing individual details.
3. Select enough figures, stages, places, or features to support the main patterns.
4. Check that paragraph 1 and paragraph 2 are balanced and not repetitive.
5. Check that the learner uses comparison language, not isolated statements.
6. Check that the learner avoids invented causes, opinions, predictions, or unsupported explanations.
7. For process and map prompts, check that details follow a logical route or spatial grouping.

Good detail paragraphs usually answer these questions:

- Which items belong together, and why?
- Which figures or labels best support the main comparison?
- What should be saved for paragraph 2 rather than crowded into paragraph 1?
- For a process, where is the natural split between the first and second detail paragraph?
- For a map, should the details be grouped by area, facility type, access, or before/after changes?

## Subtype Audit

| Subtype | What To Look For In Detail Paragraphs |
|---|---|
| Line graph | Group lines by similar movement, high/low rank, convergence/divergence, or opposite trends. Include start/end figures and key turning points only when they matter. The visual itself must show the exact value beside every plotted point. |
| Bar chart | Group categories or series logically. Include highest/lowest values and major contrasts; avoid listing every bar in order. |
| Pie chart | Group large vs small shares, compare repeated categories across pies, and mention meaningful changes in proportions. |
| Table | Group rows or columns by high/low values, similarities, outliers, or time changes. Do not turn the paragraph into a row-by-row inventory. |
| Map | Group changes by location or function. Mention specific additions/removals only after naming the broad area or land-use pattern. |
| Process | Split the sequence into early/later stages, main line/branch, input/output, or parallel routes. Use present simple and passive voice naturally. |
| Mixed chart | Decide whether each detail paragraph should cover one visual or whether both paragraphs should compare across the two visuals. Explain the relationship if the visuals are connected. |

## Common Detail Patterns

Dynamic charts:

- `In 2000, X stood at ..., compared with ... for Y.`
- `By the end of the period, X had risen to ..., while Y had fallen to ...`
- `The most noticeable change was in X, which increased from ... to ...`
- `A and B followed a similar pattern, both ...`

Static charts and tables:

- `X recorded the highest figure, at ..., whereas Y had the lowest, at ...`
- `The figures for A and B were broadly similar, at ... and ... respectively.`
- `By contrast, the remaining categories were much lower, all below ...`

Maps:

- `In the northern part of the area, ... was replaced by ...`
- `Access was also improved, with ... added near ...`
- `The central area changed from ... into ...`

Processes:

- `At the first stage, ... is ...`
- `After this, the material is sent to ... where it is ...`
- `The process then divides into two routes: ...`
- `Finally, ... is produced, while ... is removed separately.`

Use these as starting points, not fixed formulas. Adapt the amount of data to the chart.

## Feedback Pattern

When reviewing learner detail paragraphs, use this order:

1. Start with `评分`: give one direct IELTS-style estimate for these detail paragraphs only.
2. Under the score, give one brief verdict naming the main content strength and main content weakness before mentioning grammar.
3. Show `原题与图表重点`: restate the task and list 2-4 true detail-grouping priorities in Chinese.
4. Show `你的详情段`: quote the learner's response and place numbered inline markers on only the smallest problematic phrases.
5. Show `逐处修改`: map every marker to its problem type, crossed-out original wording, recommended replacement, and one brief reason. Show missing evidence or comparisons as additions rather than attaching them to unrelated wording.
6. Show `问题诊断`: prioritize grouping, data selection, comparison, and paragraph balance before grammar. Use a short Markdown table only for broader issues not already explained by the inline replacements.
7. Show `优化版本`: improve the learner's own two detail paragraphs while preserving as much structure and wording as possible, and bold only the words actually replaced or added.
8. Show `范例（Band 7）`: use [$visualize:visualize](/Users/bytedance/.codex/plugins/cache/openai-bundled/visualize/1.0.11/skills/visualize/SKILL.md) to present one concise two-paragraph model as a compact phrase explainer with 3-5 reusable comparison, data, sequencing, or location chunks and no correction marks.
9. In that visual, show the model once, make each highlighted chunk selectable, and update one single-line Chinese explanation of its detail-paragraph function or reusable pattern. If the visual cannot be created, fall back to bold chunks plus `高亮表达`.
10. Show `可迁移句式`: give 2-3 reusable two-paragraph or paragraph-pair templates.
11. Show `范例对照`: compare visual details with the model wording.
12. End with `小练习`: one targeted sentence or mini-paragraph drill based on the learner's main weakness.

Use concise Chinese labels: `评分`, `原题与图表重点`, `你的详情段`, `逐处修改`, `问题诊断`, `优化版本`, `范例（Band 7）`, `高亮表达`, `可迁移句式`, `范例对照`, `小练习`.

### Interactive Feedback Deduplication

- Do not repeat content that is already fully visible in an interactive visualization. Keep the Markdown response additive rather than duplicating the same prose.
- When an error-marker visualization contains the learner's full response, numbered markers, replacements, and reasons, under `你的详情段` output only the visualization directive. Do not quote the response again or repeat the marker-by-marker correction list in Markdown.
- When a model visualization contains the complete Band 7 answer, output only the visualization directive under `范例（Band 7）`. Do not reproduce the model paragraphs in Markdown.
- Keep the surrounding text concise: retain the score, chart priorities, paragraph-level diagnosis, optimized version when it adds value, transferable sentence patterns, model comparison, and mini-practice. Do not restate details that the visual already shows.
- Omit `优化版本` when it would merely repeat the learner's text with the same corrections already shown in the interactive error visual. Include it only when it provides a materially cleaner paragraph structure or a useful rewritten answer.
- If the interactive visualization cannot be created, use the full Markdown correction and model formats specified above as the fallback.

### Interactive Review Output Contract

When interactive visuals are available, use exactly two visual directives in a learner-response review:

1. One correction visual containing the learner's full response, numbered markers, replacements, and reasons.
2. One Band 7 model visual containing the complete independent model and selectable phrase explanations.

For the correction visual, output the directive exactly once under a single heading such as `修改互动反馈`. Do not output the same directive under both `你的详情段` and `逐处修改`, and do not reproduce the quoted response or a separate marker-by-marker list in Markdown.

For the model visual, output the directive exactly once under `范例（Band 7）`. Do not add a separate Markdown model or a second model-comparison block that repeats its content.

When both visuals work, omit `优化版本` by default. Add a short optimized answer only when the learner explicitly asks for it or when it makes a substantial structural improvement that neither visual already provides. Keep the remaining Markdown sections limited to `评分`, `原题与图表重点`, paragraph-level `问题诊断`, `可迁移句式`, and `小练习`.

### Inline Correction Markup

- In the quoted learner paragraphs, mark only the smallest problematic span as `~~original wording~~〔1〕`; keep correct surrounding text unchanged and unbolded.
- Under `逐处修改`, use `❌` for inaccurate meaning, grammar, figures, or comparisons; `△` for understandable but unnatural or inappropriate wording; and `➕` for omitted evidence or comparison.
- Format a direct replacement as `❌ 〔1〕 错误类型：~~old wording~~ → **✅ 建议替换：new wording** — brief reason.`
- Format a missing detail as `➕ 内容遗漏：**建议补充：missing evidence or comparison** — brief reason.` Do not force an omission marker onto an unrelated phrase.
- Number markers in reading order across both paragraphs and use the same number in the quoted response and `逐处修改`.
- Keep `问题诊断` for paragraph-level issues such as wrong grouping, data dumping, weak paragraph balance, missing support, or overview-style repetition. Do not repeat every inline correction in the table.
- In `优化版本`, bold only actual replacements or additions. For `范例（Band 7）`, invoke the linked Visualize skill and follow its full output contract; keep the visual compact, accessible, theme-aware, and limited to phrase-to-function mapping. Show the model only once and do not duplicate it in Markdown. If visualization is unavailable, bold 3-5 reusable chunks and explain them under `高亮表达`; never bold whole sentences, figures alone, or isolated ordinary words.
- Keep Visualize usage confined to the high-score model presentation; do not change prompt generation, the task visual, scoring, or correction order.
- If the detail paragraphs are accurate and well grouped, do not manufacture markers. State that no obvious content or language problem is present and give only genuinely useful refinements.

## High-Score Model Visual Style

Before building `范例（Band 7）`, read [`assets/high-score-model-visual-template.html`](assets/high-score-model-visual-template.html) completely and use it as the starting fragment. Treat this as a low-freedom template, not a loose design reference.

- Preserve the template's DOM order, class structure, vertical two-paragraph layout, spacing values, left accents, colored inline highlights, selected-state behavior, explanation card, and interaction logic exactly.
- Change only the unique root/explanation IDs, accessibility text, paragraph grouping labels, model prose, highlighted phrase text, `data-key` values, and Chinese explanations.
- Keep `Detail paragraph 1` on `--viz-series-1` and `Detail paragraph 2` on `--viz-series-2`. Do not substitute gray highlights, generic `.btn` controls, side-by-side cards, or a phrase-tile grid.
- Keep exactly one `<p>` inside each paragraph block and one single-line explanation below both blocks. Add or remove highlight buttons only to reach the required 3-5 useful chunks; do not change their CSS.
- Render and visually inspect the adapted fragment at about 736 px and 320 px before presenting it. If the result differs materially from the template, revise it back to the template rather than improvising a new layout.

For Markdown fallback, normally include both `优化版本` and `范例（Band 7）`. They have different jobs. When interactive visuals are available, follow the `Interactive Review Output Contract` instead:

- `优化版本`: repair the learner's own two paragraphs, keeping their grouping if it is workable.
- `范例（Band 7）`: provide an independent model with stronger grouping, selection, comparison, and natural Task 1 wording.

## Transferable Sentence Patterns

Whenever a learner-facing response provides an answer, model, corrected answer, or direct example, place `可迁移句式` immediately after the answer block.

- Give 2-3 templates that transfer to other Task 1 detail paragraphs of the same visual type.
- Prefer paragraph-level templates, not isolated phrases.
- Use placeholders such as `A`, `B`, `X`, `Y`, `the first group`, `the remaining categories`, or `the main route`.
- Keep templates practical at Band 7 level, not overly advanced.

Example:

- 模板 1：`In the first group, A recorded the highest figure, at X, while B was lower at Y. By contrast, the remaining categories were much smaller, with none exceeding Z.`
- 模板 2：`The first detail paragraph can focus on the categories that changed most noticeably. The second paragraph can then compare the more stable or lower-ranked categories.`

## Scoring Format

Use IELTS Academic Writing Task 1 band wording, but label it as a detail-only estimate:

`评分：详情段预估 Band 6.5`

Judge strictly by detail-paragraph quality:

- Task Achievement: accurate supporting details, sufficient but selective figures, correct grouping, no invented data, and appropriate coverage of the visual.
- Coherence and Cohesion: two clear paragraphs, logical order, balanced development, and useful linking/comparison.
- Lexical Resource: natural comparison, trend, process, map, and quantity language.
- Grammatical Range and Accuracy: tense, articles, plurals, comparison structures, passive voice for processes, and sentence control.

Calibration:

- `Band 4.0-5.0`: mostly inaccurate details, no grouping, severe data dumping, invented figures, or only one paragraph.
- `Band 5.5`: some accurate details, but weak grouping, missing major support, limited comparison, or very uneven paragraphs.
- `Band 6.0`: generally understandable, with some useful data, but too list-like or missing important comparisons.
- `Band 6.5`: accurate and mostly grouped, but limited range, insufficient data support, or awkward paragraph balance.
- `Band 7.0`: clear grouping, accurate selected data, useful comparisons, and natural paragraph flow.
- `Band 7.5-8.0`: precise, well balanced, selective, and idiomatic with no distracting issue.
- `Band 8.5-9.0`: rare for practice; reserve for excellent selection, grouping, and language control.

Do not inflate the score just because the English sounds natural. If the details are not grouped or the data support is weak, lower the band.

## Problem Diagnosis

| Issue | Diagnosis | Better Direction |
|---|---|---|
| Data dump | The learner lists many figures without grouping or comparison. | Group the data first, then select representative figures. |
| Too few figures | The paragraph makes broad claims but gives little evidence. | Add key figures to support the highest, lowest, biggest change, or main contrast. |
| Wrong grouping | Items are grouped randomly or in chart order only. | Group by trend, ranking, category type, location, route, or stage. |
| Missing comparison | Sentences describe items separately. | Use `whereas`, `while`, `compared with`, `respectively`, or comparative structures. |
| One-paragraph response | The learner writes one body paragraph only. | Split the details into two balanced paragraphs. |
| Overview instead of details | The response summarizes the big picture without evidence. | Add selected figures, places, stages, or labels. |
| Process list without split | The learner names all stages in one long sequence. | Split into early/later stages or main line/branch. |
| Map list | The learner lists facilities without spatial grouping. | Group by north/south/east/west, central/peripheral areas, or facility type. |
| Mixed-chart omission | Only one visual is developed. | Give each visual a paragraph, or compare both visuals where they connect. |

In the `建议` column, give a corrected detail-paragraph direction, not just "rewrite it".

## Hint Mode

When the user says `给点提示`, do not reveal a full model immediately. Use this scaffold:

1. Name the visual type and the detail-paragraph job.
2. Suggest a two-paragraph grouping plan.
3. Ask 2-3 guiding questions about figures, comparisons, or route/stage split.
4. Provide a fill-in-the-blank skeleton.
5. Invite the learner to try again.

Example:

`先别急着写所有数字。第一段可以写最高的两个类别，第二段写剩下较低的类别。骨架：In the first group, ___ was highest at ___, while ___ stood at ___. By contrast, ___ and ___ were much lower, at ___ and ___ respectively.`

## Guardrails

- Do not ask the learner to write the introduction or overview unless they request it.
- Do not let the learner or model write one giant paragraph.
- Do not reward chart-order listing when a clearer grouping exists.
- Do not include every number in the model answer; choose figures that support the comparison.
- Do not omit important support for the overview-level claim.
- Do not invent causes, explanations, opinions, or predictions.
- For future years, use `is projected to`, `is expected to`, or `will` when the task requires it.
- For past dynamic charts, use past tense consistently.
- For process diagrams, use present simple and passive voice naturally.
- For maps, decide static vs dynamic before writing; do not use change language for a static site-selection task.
- Keep model answers at natural Band 7 level: clear, accurate, reusable, and not over-polished.
