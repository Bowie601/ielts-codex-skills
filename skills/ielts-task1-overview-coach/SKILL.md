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
- The overview must sound like an overview, not a compressed body paragraph. For process diagrams, prioritize the overall structure, route, transformation, start/end points, broad phases, branches, cycles, or convergence; avoid naming a chain of individual steps unless they are grouped into a higher-level feature.
- Preserve enough concrete content for the two detail paragraphs. Especially for a simple process diagram, do not name every input, machine or treatment stage, output, and final use in the overview. If the overview would exhaust nearly all visible labels, generalize the middle as `a main treatment stage` or `the main processing line`, and describe outputs by broad roles such as `energy`, `fertiliser`, `a main product`, or `a by-product`.
- A missing or weak overview damages Task Achievement heavily. Treat unclear, incomplete, or detail-heavy summaries as serious issues.
- Train repeatable thinking: first group the visual, then pick 2-3 main features, then write exactly two overview sentences.
- Require every learner overview, optimized version, and model answer to contain exactly two complete sentences. Use the first sentence for the overall structure or dominant pattern and the second for a complementary feature such as the start/end points, main contrast, ranking, branch, or second visual.

## Teaching Loop

1. Select one visual type or subtype.
2. Provide one IELTS Task 1 prompt with a visual. For line graphs, create a local `.svg`, show it inline, and provide a local file link so it can be opened from the side panel. For process diagrams, always use draw.io/diagrams.net; do not use Mermaid. For other visual types, use an interactive local HTML visual and a clickable `http://127.0.0.1:<port>/...` link.
3. Ask the learner to write only the overview paragraph in exactly two sentences.
4. Finish the practice-prompt response with the learner-facing progress tracker defined below.
5. If the learner asks for `给点提示`, give scaffolded hints before showing a model.
6. After the learner responds, score the overview and diagnose main-feature selection first, then language.
7. Give one Band 7-level model overview built from concise, reusable sentence patterns, followed by a `可迁移句式` summary.
8. End with one targeted mini-practice or ask whether to continue with a similar prompt.

Keep the interaction incremental. Do not give several unseen tasks at once unless the user explicitly asks for a set.

## Practice Progress

Show one compact progress line as the final learner-facing block of every new practice-prompt response, including the first prompt in a session. Place it after the overview-writing instruction; never put it above the title, task statement, visual, or response instruction, and write nothing after it. Use `当前进度（n/N）：`, connect the full ordered set with `→`, and wrap the current item in full-width brackets `【】`. The tracker shows the current type's position in the rotation; it must not reveal the chart's main features or the expected overview.

For general Task 1 rotation, use these seven visual types in this fixed order:

`折线图 → 柱状图 → 饼图 → 表格 → 地图 → 流程图 → 混合图`

Example:

`当前进度（6/7）：折线图 → 柱状图 → 饼图 → 表格 → 地图 → 【流程图】 → 混合图`

When the learner requests process-diagram practice, track the seven process structures instead of the top-level visual types:

`单线流程 → 汇合流程 → 副产品分支 → 双产物分支 → 自然循环 → 并行路线 → 混合流程`

Example:

`当前进度（4/7）：单线流程 → 汇合流程 → 副产品分支 → 【双产物分支】 → 自然循环 → 并行路线 → 混合流程`

Keep the order stable across a one-by-one practice session. Advance to the next item when the learner asks for `下一题`, unless they request a specific type, ask to repeat the current type, or narrow the practice scope. If a session starts with a user-selected type, highlight that type directly; do not imply that earlier items have already been completed.

## Visual Format

Design every visual for comfortable split-screen reading. Prefer a canvas or SVG `viewBox` around `900 × 600` or `960 × 640`, with an aspect ratio between roughly `4:3` and `3:2`; do not exceed about `1.6:1` unless the content makes it unavoidable. Avoid long horizontal strips that become too small when fitted into a narrow panel.

- Keep all labels readable when the visual is displayed at about 600 px wide.
- For processes with 5-8 stages, use two rows, a compact vertical arrangement, or a clear serpentine route when a single row would make the image too wide. Keep arrows orthogonal and the reading order obvious.
- For two-panel maps or mixed visuals, stack panels vertically when side-by-side placement would make labels too small.
- For HTML visuals, use a responsive chart container with a practical maximum width around 900 px, sufficient height, and no horizontal scrolling.
- Preview the visual at split-screen size before presenting it; do not validate readability only at full resolution.

When giving a practice prompt, include:

**题目**

The task statement.

For line graph prompts, include:

**图表图片**

Create a local `.svg` file in the active IELTS workspace and show it directly with Markdown image syntax, using the absolute filesystem path. Also provide a local file link to the same `.svg`, so the learner can open the saved SVG from the side panel. Do not start a local HTTP server or create an HTML wrapper for line graphs. Use a clean IELTS-style SVG: white background, serif font, thin black axes/gridlines, direct labels or a clear legend, and distinct but restrained line styles or muted colors. Make the graph readable enough for overview selection without requiring hover or click interactions.

Example:

`![折线图](/Users/.../Documents/ielts/task1_line_example.svg)`

`[在侧边打开 SVG](/Users/.../Documents/ielts/task1_line_example.svg)`

For process diagram prompts, include:

**图表图片**

Create the process visual with draw.io/diagrams.net by default:

- Create a local `.drawio` source file in the active IELTS workspace.
- Export it with the draw.io CLI to a local `.svg` preview. Export a `.png` only when useful for visual inspection:
  - `draw.io -x -f svg --embed-diagram -b 20 -o <output>.svg <source>.drawio`
  - `draw.io -x -f png -b 20 -o <output>.png <source>.drawio`
- Show only the exported SVG directly with Markdown image syntax and provide its local file link for side-panel preview. Do not show or link the `.drawio` source in the learner-facing response unless the user explicitly asks for it.
- Validate with `xmllint --noout <source>.drawio <output>.svg` and visually preview the exported SVG/PNG before presenting it. On macOS, `qlmanage -t -s 1200 -o /tmp <output>.svg` plus `view_image` is a suitable preview check.
- If draw.io CLI is unavailable, fall back to a hand-authored static SVG and say briefly that draw.io export was unavailable.

Do not use Mermaid for process visuals. Draw.io/diagrams.net is the required process-diagram generator because it gives more reliable control over IELTS-style spacing, orthogonal arrows, cycles, branches, and parallel streams.

Use an authentic IELTS Task 1 visual style rather than a technical engineering schematic. Prefer simple flat 2D boxes, orthogonal arrows, and 5-8 clearly labelled stages. Avoid complex cross-sections, thick pipe networks, perspective drawings, multiple arrow styles, crowded routes, decorative icons that touch text, or explanatory sentences that effectively give the overview. Use phase labels only when they look like normal chart labels, not answer hints. If a real process is technically complex, simplify it into an exam-style schematic that makes the main route, cycle, branch, or convergence easy to see at a glance.

Example:

`![流程图](/Users/.../Documents/ielts/task1_process_example.svg)`

`[在侧边打开 SVG](/Users/.../Documents/ielts/task1_process_example.svg)`

For table, bar, pie, map, and mixed-chart prompts, include:

**交互图表**

Create a local `.html` file in the active IELTS workspace. Use a clean IELTS-style layout by default: white background, serif font, thin black grid/axes, and restrained spacing. Keep most visuals black-and-white except learner markings, but make bar charts easier to read by giving each bar series or category a distinct, low-saturation fill color with a black outline and matching legend swatch.

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

For bar, pie, map, and mixed-chart prompts, keep the visual inside the HTML page and add lightweight interaction only when useful: clickable labels/bars/regions for marking important features or hover titles for unfamiliar labels. For bar charts, use color primarily to distinguish bar series/categories rather than as decoration; choose readable, muted colors that still work with black text, axes, and gridlines. Make chart legends very easy to read: use legend text that is clearly larger than axis labels or ordinary small labels, usually around 18-20px in SVG/HTML charts. Keep primary group/category labels and chart legend text visually consistent, using the same or very similar font size. Prefer extra spacing, wrapping, or a wider legend area over shrinking legend text. Do not add a separate bottom instruction block or extra high/low learner-marking legend such as `Click a bar...`, `high / important`, or `low / minor` unless the user explicitly asks for visible marking instructions. Do not let interaction distract from overview practice.

For non-line-graph HTML prompts, if the in-app browser or HTTP server is unavailable, fall back to a compact Markdown visual under `图表信息`, and say briefly that the interactive HTML could not be opened.

Then ask:

`请只写 overview 段，共 2 句，不要写 introduction，也不要罗列太多具体数据。`

Finish the learner-facing prompt with:

**练习进度**

The applicable progress line from `Practice Progress`. Do not add any content after the progress line.

The visual should contain enough information for overview selection, but it does not need to be data-dense. The goal is to practise choosing and wording the main features, not calculating every detail.

For map visuals, prioritize readability over visual density. Use SVG when the user requests SVG output or when a static visual is clearer than an interactive page. Keep labels outside crowded shapes whenever possible, and use short callouts or legends instead of placing text directly on roads, arrows, circles, process connectors, or patterned areas. Leave clear spacing between labels, arrows, facilities, roundabouts, and panel borders; if a label would overlap, shorten it, move it into nearby whitespace, or replace multiple item labels with one accurate umbrella label such as `bus facilities`, `visitor facilities`, `public space`, or `access roads`. Avoid rotated text except for large empty areas, and never let caption text collide with the compass, arrows, or panel frames. Before presenting the visual, mentally check both panels at conversation screenshot size: all labels should be readable, no text should cross a road or building outline, and the overview-relevant features should be visible without zooming.

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
4. Divide the selected main features across exactly two sentences: an overall structure or dominant pattern first, followed by one complementary main feature.
5. Check that no exact detail paragraph has slipped into the overview.
6. For process diagrams, check that the wording stays at structure level: type of process, start/end, major phases, branch or merge pattern, repeated cycle, and main output. Do not turn the overview into a shortened list of step labels.
7. Run a detail-reserve check: after reading the overview, confirm that both body paragraphs still have meaningful stages, equipment, materials, figures, or uses left to describe. If not, replace specific labels with accurate umbrella wording.

Good overview content usually answers one or two of these questions:

- What was highest or lowest overall?
- What increased, decreased, or remained stable?
- Which groups were similar or clearly different?
- Did the order/ranking change over time?
- What was the biggest overall change in the map?
- How many stages are there, and where does the process begin and end?
- For a process, what is the structure: linear, cyclical, branching, converging, parallel, or mixed?
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
| Process | State the structure of the process, such as linear, cyclical, branching, converging, parallel, or mixed; give the start and end points, broad phases, and main output. Keep it at overview level: do not compress the body paragraph by naming a sequence of individual operations such as washing, mixing, cleaning, pressing, and packing unless they are grouped into a broader phase or structural relationship. |
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
- `Overall, the process has two input streams that merge before the material is converted into the final product.`
- `Overall, the main treatment line produces X, while one or more by-products are removed separately.`
- `Overall, the process is mainly linear, although it includes a side branch for waste or by-products.`

Process structure templates:

- Single-line process: `Overall, it is a linear, man-made process in which A is processed into B. The process begins with X and ends with Y.`
- Converging process: `Overall, this is a mainly linear, man-made process in which A and B are combined to produce C. Once the materials have merged, the mixture passes through several stages before being turned into the final product.`
- Branching process with a by-product: `Overall, this is a mainly linear process with a separate branch for X as a by-product. The main material passes through several stages before being turned into Y, while X is sent to Z.`
- Branching process with parallel final products: `Overall, this is a man-made process with two branches leading to different final products. It begins with A and then divides into two routes, producing B and C respectively.`
- Natural cycle: `Overall, this is a cyclical natural process in which A develops through several stages, from B to C. Once C is formed, the cycle starts again.`
- Parallel routes: `Overall, this is a man-made process consisting of two parallel routes, one for A and the other for B. Both routes begin with X and continue through separate stages before producing Y and Z respectively.`
- Mixed process: `Overall, this is a mixed process in which two inputs are combined before passing through a main treatment stage. It then produces two outputs, one used for X and the other for Y.`

When choosing a process template, classify the diagram first: single-line, converging, branching by-product, branching parallel products, cycle, parallel routes, or mixed. Use the template only as a base; adapt it to the visual and avoid squeezing every step into the overview.

Mixed charts:

- `Overall, the two charts show that X was associated with Y, while Z remained comparatively low.`
- `Overall, X followed an upward trend, whereas the related measure in the second chart changed only slightly.`
- `Overall, the first chart highlights X, while the second shows that Y was the dominant category.`

## Feedback Pattern

When reviewing a learner overview, use this order:

1. Start with `评分`: give one direct IELTS-style estimate for this overview paragraph.
2. Under the score, give one brief verdict naming the main content strength and main content weakness before mentioning grammar.
3. Show `原题与图表重点`: restate the task and list 2-3 true main features in Chinese.
4. Show `你的概述`: quote the learner's overview and place numbered inline markers on only the smallest problematic phrases.
5. Show `逐处修改`: map every marker to its problem type, crossed-out original wording, recommended replacement, and one brief reason. Show missing main features as additions rather than forcing them onto an unrelated phrase.
6. Show `问题诊断`: prioritize feature selection and paragraph role before grammar. Use a short Markdown table only for broader issues not already explained by the inline replacements.
7. Show `优化版本`: improve the learner's own overview while preserving as much of their structure and wording as possible, make it exactly two complete sentences, and bold only the words actually replaced or added.
8. Show `范例（Band 7）`: use [$visualize:visualize](/Users/bytedance/.codex/plugins/cache/openai-bundled/visualize/1.0.11/skills/visualize/SKILL.md) to present one concise two-sentence model as a compact phrase explainer with 2-4 reusable chunks and no correction marks.
9. In that visual, show the model once, make each highlighted chunk selectable, and update one single-line Chinese explanation of its overview function or reusable pattern. If the visual cannot be created, fall back to bold chunks plus `高亮表达`.
10. Show `可迁移句式`: abstract 2-3 reusable whole-overview templates from the answer, with exactly two connected sentences in each template.
11. Show `范例对照`: compare the key visual features with the model wording.
12. End with one targeted mini-practice or ask whether to continue with a similar prompt.

Use concise Chinese labels: `评分`, `原题与图表重点`, `你的概述`, `逐处修改`, `问题诊断`, `优化版本`, `范例（Band 7）`, `高亮表达`, `可迁移句式`, `范例对照`, `小练习`.

### Inline Correction Markup

- In the quoted learner overview, mark only the smallest problematic span as `~~original wording~~〔1〕`; keep correct surrounding text unchanged and unbolded.
- Under `逐处修改`, use `❌` for inaccurate meaning or grammar, `△` for understandable but unnatural or inappropriate wording, and `➕` for omitted overview content.
- Format a direct replacement as `❌ 〔1〕 错误类型：~~old wording~~ → **✅ 建议替换：new wording** — brief reason.`
- Format a missing feature as `➕ 内容遗漏：**建议补充：missing main feature** — brief reason.` Do not attach it to an unrelated phrase in the learner's sentence.
- Number markers in reading order and use the same number in the quoted overview and `逐处修改`.
- Keep `问题诊断` for non-local issues such as wrong feature selection, detail dumping, weak two-sentence division, or failure to cover the whole visual. Do not repeat every inline correction in the table.
- In `优化版本`, bold only actual replacements or additions. For `范例（Band 7）`, invoke the linked Visualize skill and follow its full output contract; keep the visual compact, accessible, theme-aware, and limited to phrase-to-function mapping. Show the model only once and do not duplicate it in Markdown. If visualization is unavailable, bold 2-4 reusable chunks and explain them under `高亮表达`; never bold the whole sentence or isolated ordinary words.
- Keep Visualize usage confined to the high-score model presentation; do not change prompt generation, the task visual, scoring, or correction order.
- If the overview is accurate, do not manufacture markers. State that no obvious content or language problem is present and give only genuinely useful refinements.

## High-Score Model Visual Style

Before building `范例（Band 7）`, read [`assets/high-score-model-visual-template.html`](assets/high-score-model-visual-template.html) completely and use it as the starting fragment. Preserve its exact layout, CSS values, colored inline highlight behavior, explanation card, and interaction logic.

- Change only the unique IDs, accessibility text, grouping cue, two-sentence model prose, highlighted phrase text, `data-key` values, and Chinese explanations.
- Keep the single `Overview` prose block on `--viz-series-1`; do not introduce gray highlights, generic `.btn` controls, phrase tiles, columns, or multiple cards.
- Keep exactly one `<p>` and one single-line explanation. Add or remove highlight buttons only to reach 2-4 useful chunks; do not change their CSS.
- Render and visually inspect the adapted fragment at about 736 px and 320 px. If it differs materially from the template, revise it back to the template.

Always include both `优化版本` and `范例（Band 7）` after diagnosing a learner's overview. They have different jobs:

- `优化版本`: a revised version of the learner's own wording. Keep their basic structure where possible, fix grammar and wording, add missing content only if it can be done without completely rewriting the paragraph, and return exactly two complete sentences.
- `范例（Band 7）`: an independent, exam-ready model that fixes both content selection and language while remaining easy to understand, remember, and adapt.

Do not replace the Band 7 model with labels like `更自然版本`, `修改版`, or `参考句子`. The learner should see both a close edit of their own attempt and one clean Band 7-level model.

The Band 7 model overview must:

- Cover the best 2-3 main visual features, not only the learner's chosen points.
- Be concise and contain exactly two complete sentences.
- Prefer common Task 1 vocabulary and short, reusable structures that a learner can reproduce reliably under exam conditions.
- Use one clear overall sentence followed by one simple contrast, ranking, trend, branch, or start/end sentence.
- Avoid rare vocabulary, heavily nested clauses, unnecessary synonyms, and language that is more sophisticated than the task requires.
- Avoid detail-paragraph data dumping.
- Prefer accurate umbrella terms over lists of individual items when the umbrella term clearly captures the visual feature, such as `old industrial buildings`, `visitor facilities`, `commercial facilities`, `transport and pedestrian infrastructure`, or `natural features`.
- For map overviews, keep the model at overview level: summarize broad land-use, access, and facility changes instead of naming every visible feature. A model such as `industrial and parking areas were replaced by visitor facilities and public space, while access was improved` is usually better than `the museum was expanded, the warehouse became a gallery and cafe, and the surface car park became a plaza`.
- For process overviews, keep the model at overview level: summarize the overall route and structure, such as linear/cyclical flow, start and end points, broad phase grouping, branch/by-product handling, or convergence of inputs. Avoid making the model a compressed body paragraph by listing individual steps like `collected, mixed, cleaned, pressed and packed`; use umbrella phrases such as `main processing line`, `preparation stage`, `manufacturing stage`, `side branch`, `by-product stream`, or `two input streams` where accurate.
- Keep enough unused specifics for two detail paragraphs. On sparse diagrams, prefer a structural summary over simultaneously naming all inputs, equipment, outputs, and uses.
- Use natural Task 1 overview language and clear grouping or contrast.
- Correct content omissions as well as grammar.

## Transferable Sentence Patterns

Whenever a learner-facing response provides an answer, model, corrected answer, or direct example, make the overview exactly two complete sentences and place a `可迁移句式` section immediately after the answer block. This applies even when the learner asks only for `示例`, `答案`, `参考答案`, or `怎么写`; never return a model answer by itself.

- Give 2-3 whole-overview templates that transfer to other Task 1 prompts of the same structural type.
- Make every template exactly two connected sentences: sentence 1 states the overall structure or dominant pattern, and sentence 2 adds the complementary feature.
- Present them as `模板 1`, `模板 2`, and optionally `模板 3`; keep both sentences together inside each template.
- Do not split the transferable language into separate one-sentence bullets or isolated sentence fragments.
- Replace topic-specific nouns and figures with placeholders such as `A`, `B`, `X`, `Y`, or `X stages`.
- Preserve the model's two-sentence overview logic rather than repeating individual sentences with only one noun changed.
- Keep the patterns at the same simple, reliable Band 7 level as the model answer.
- Prioritize the structural move taught by the answer, such as start/end, two inputs merging, one route branching, two parallel routes, highest/lowest ranking, or opposite trends.
- If a full feedback response already contains `可迁移句式`, include it once only; do not add a duplicate template section.

## Scoring Format

Use IELTS Academic Writing Task 1 band wording, but label it as an overview-only estimate:

`评分：概述段预估 Band 6.0`

Give one overall estimate, not a full essay band. Judge strictly by overview quality:

- Task Achievement: clear overview role, correct and sufficiently complete main-feature selection, no invented trend, no missing dominant feature, and no unnecessary detail paragraph behavior.
- Coherence and Cohesion: exactly two clear sentences with logical grouping and contrast, not a list of facilities, figures, stages, or locations.
- Lexical Resource: natural overview vocabulary, accurate trend/ranking/map/process language, and appropriate umbrella terms for broad categories.
- Grammatical Range and Accuracy: tense, comparison, articles, plural forms, and sentence structure.

Content selection comes first. An overview can be grammatically polished but still score lower if it misses an important visual feature, over-focuses on one pattern, gives a detail-paragraph list, or fails to summarize the whole chart. Before commenting on wording, check whether the learner has captured the best 2-3 main features for that visual at overview level.

Do not lower the score just because a phrase is broad or abstract if it accurately summarizes a main visual feature. For example, `new transport and pedestrian infrastructure` is suitable in an overview when it summarizes a pier, path, parking, bus stop, or similar access features. Only mark an umbrella term as too vague when it hides the real pattern, misreads the visual, or could apply to almost any chart without naming the main feature.

Calibration:

- `Band 4.0-5.0`: no clear overview, mostly details, invented trend, wrong dominant feature, or major misreading of the visual.
- `Band 5.5`: some broad idea is present, but a key feature is missing or the sentence is too detail-heavy/unclear.
- `Band 6.0`: main picture is partly right, but one important feature is missing, vague, incomplete, or awkwardly worded.
- `Band 6.5`: accurate and clear, but limited, too general, or missing a useful contrast or secondary main feature.
- `Band 7.0`: clear main features, good grouping, natural contrast, minimal detail.
- `Band 7.5-8.0`: concise, accurate, well grouped, and idiomatic; includes the most important trend/ranking/contrast using overview-level wording rather than unnecessary item lists.
- `Band 8.5-9.0`: rare for practice; reserve for a precise, elegant overview with no distracting issue.

Be strict:

- A Task 1 answer without a clear overview is usually capped around Band 5 for Task Achievement.
- A paragraph that lists many numbers without summarizing should score low even if the numbers are accurate.
- A paragraph that lists many facilities, routes, stages, or categories without grouping should be treated as detail-heavy, even if the facts are correct.
- A paragraph that says only `Overall, there were many changes` is too vague.
- A paragraph that is grammatically strong but misses a major category, dominant ranking, stable high group, or second visual should usually not exceed Band 7.0.
- Do not penalize accurate overview-level umbrella wording merely because a more specific detail is visible in the chart; specific item lists usually belong in body paragraphs.
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
| Compressed process body | The learner or model writes a short version of the detail paragraph, naming several operations in sequence rather than summarizing the structure. | Replace step chains with structure-level wording: `two input streams merge`, `the main line produces treated water`, `waste is removed as a by-product`, or `the material passes from preparation to final processing`. |
| Overview exhausts the details | The overview names nearly every input, treatment unit, output, and use, leaving little meaningful content for the two body paragraphs. | Keep the route and main outcome, but replace specific equipment and output labels with umbrella wording such as `a main treatment stage`, `two outputs`, `energy`, or `a by-product`. |
| Map detail list | The learner lists facilities. | Summarize transformation or land-use/access change. |
| Over-specific diagnosis | The learner uses a valid umbrella term for overview-level meaning, but the feedback pushes them to list individual items. | Keep the umbrella term if it is accurate; only add examples in `范例对照` or body-paragraph advice. |
| Misleading umbrella term | The learner uses a broad term that hides or distorts the main pattern. | Replace it with a more accurate overview category, not a long list of details. |
| Mixed-chart omission | Only one visual is summarized. | Mention both visuals or the relationship between them. |

In the `建议` column, give a corrected overview direction, not just "rewrite it".

When diagnosing wording, distinguish overview abstraction from vagueness:

- Good abstraction: `old industrial buildings`, `visitor facilities`, `residential development`, `transport and pedestrian infrastructure`, `natural features`, `local services`.
- Too vague: `things`, `many changes`, `some facilities`, `the area became different`.
- Too detailed for overview: long lists such as `a new pier, pedestrian path, bus stop, visitor parking, hotel, cafes and shops` unless the list is shortened or grouped.
- If a learner writes an accurate overview phrase such as `transport and pedestrian infrastructure`, do not mark it as a problem only because the visual also shows a pier or path. Suggest a specific example only as an optional body-paragraph detail.
- When giving `范例（Band 7）`, do not make the model more detail-heavy than the learner's improved overview. Use specific examples mainly in `范例对照`; keep the model paragraph focused on category-level changes.

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
- For process diagrams, do not let the model overview become a compressed step-by-step description. It should look like an overview: structure, start/end, main phases, branches/cycles/convergence, and final output.
- Do not let an overview consume nearly all of a sparse diagram's labels. Preserve specific stages, equipment, materials, and uses for the two detail paragraphs.
- Do not omit the Band 7 model overview after feedback. The learner should always see one clear, practical `范例（Band 7）`.
- Do not provide any model, corrected answer, or direct example without following it with `可迁移句式`.
- Do not provide a one-sentence or three-sentence overview. Every direct example, `优化版本`, and `范例（Band 7）` must contain exactly two complete sentences.
- Do not present `可迁移句式` as isolated one-sentence patterns. Every transferable template must be a complete two-sentence overview.
- Do not omit the `优化版本`; it helps the learner see how their own sentence can be repaired.
- Do not label the Band 7 model merely as `更自然版本`; this makes the response look like grammar polishing instead of overview training.
- Do not include many exact numbers in the model overview; broad references such as `by far`, `slightly`, `roughly`, or `the majority` are enough when useful.
- Do not add causes, opinions, or explanations.
- Do not overuse formulas mechanically. Adapt the overview to the visual.
- Do not use `it can be seen that` in every model. Prefer concise wording like `Overall, X...`.
- For future years, use future wording such as `is projected to`, `is expected to`, or `will` if the task requires it.
- For past years, use past tense in detail if needed, but overview patterns may use stable summary wording such as `remained`, `rose`, or `declined`.
- For process diagrams, use present simple and passive voice naturally when the process is man-made.
- For process wording, prefer `A and B are combined to produce C`, not `combined into produce C`; prefer `passes through several stages`, not `processes through several stages`.
- For process prompts, show only the exported SVG in the learner-facing response; keep the draw.io source file available locally but do not include its link unless requested.
- Never replace draw.io with Mermaid for a process visual.
- For maps, decide static vs dynamic before writing; do not use change language for a static site-selection task.

## Model Response Style

For a learner overview like:

`Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Online gaming was particularly popular among people under 50, whereas gardening was preferred by those aged 65 and over.`

Use this response structure; the `范例（Band 7）` and `高亮表达` block below is the Markdown fallback when visualization is unavailable:

**评分：概述段预估 Band 7.0**

语言比较自然，online gaming 和 gardening 的年龄变化也抓得准；但内容还不够完整，因为漏掉了 watching films 这个在多个年龄组里都较高、相对稳定的重要特征。

**原题与图表重点**

- online gaming 随年龄增长明显下降。
- gardening 随年龄增长明显上升。
- watching films 在多数年龄组中都比较高，team sports 整体偏低。

**你的概述**

> Overall, online gaming became less popular with age, while gardening showed the opposite pattern. Online gaming was particularly popular among people under 50, whereas gardening was preferred by those aged 65 and over.

**逐处修改**

- ➕ 内容遗漏：**建议补充：watching films 在多数年龄组中保持较高水平，而 team sports 整体较低** — 原概述的第二句仍在重复 online gaming 和 gardening，没有覆盖另一个重要整体特征。

**问题诊断**

| 位置 | 问题 | 建议 |
|---|---|---|
| 内容选择 | 只概括了两个活动的年龄趋势，漏掉 `watching films` 这个整体较高且稳定的重要类别 | 保留 online gaming/gardening 的对比，再补一句或半句概括 `watching films` 和/或 `team sports` 的整体高低 |
| 第二句 | `particularly popular among people under 50` 可以，但内容仍围绕 online gaming/gardening 重复 | 用第二句写更宽的整体对比，例如 `Watching films remained popular across most age groups, whereas team sports attracted lower participation overall.` |

**优化版本**

Overall, online gaming became less popular with age, while gardening showed the opposite pattern. **Watching films remained popular across most age groups, whereas team sports attracted lower participation overall.**

**范例（Band 7）**

Overall, online gaming **became less popular with age**, while gardening **showed the opposite trend**. Watching films **remained popular across most age groups**, whereas team sports were less common overall.

**高亮表达**

- `became less popular with age`：概括随年龄增长而下降。
- `showed the opposite trend`：连接相反趋势。
- `remained popular across most age groups`：概括多数群体中的稳定高位。

**可迁移句式**

- 模板 1：`Overall, X became less common across the groups, while Y showed the opposite pattern. Z remained popular in most groups, whereas W was less common overall.`
- 模板 2：`Overall, the chart shows a clear contrast between X and Y. While X followed one general pattern, Y moved in the opposite direction, and Z remained comparatively stable.`

**范例对照**

| 图表重点 | 范例表达 | 写法 |
|---|---|---|
| 两个相反年龄趋势 | `online gaming became less popular with age, while gardening showed the opposite pattern` | trend by age |
| 另一个重要整体特征 | `Watching films remained relatively popular across most age groups` | content completeness |
| 整体偏低类别 | `team sports attracted comparatively lower levels of participation` | ranking/comparison |

Finish with one targeted mini-practice based on the learner's main weakness.
