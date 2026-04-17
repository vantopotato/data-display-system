# data-display-system

中英双语的数据展示设计系统入口文档。  
A bilingual entry document for the data-display design system.

## Open Source Notice
- 本项目可开源发布。
- 设计方法与部分交互组织灵感来源于 Ant Design 的数据展示与后台设计思路。
- 本项目为独立整理与实现，不隶属于 Ant Design 或蚂蚁集团，也不代表其官方立场。

- This project is intended for open-source release.
- Parts of the design approach and interaction organization are inspired by Ant Design's data-display and admin design patterns.
- This is an independent work and is not affiliated with, endorsed by, or officially representing Ant Design or Ant Group.

## Purpose
- 为后台列表页、数据表、资源管理页、审核页、运营页提供统一的数据展示规范
- 为 Agent 和人类协作者提供一致的调用顺序与文件导航
- 在不牺牲表格可读性的前提下，支持品牌 token 覆盖

- Provide a unified data-display system for admin lists, data tables, resource libraries, review queues, and operations pages
- Give both agents and human collaborators a consistent reading order and file map
- Allow brand-token overrides without weakening table readability

## Best For
- 后台列表页
- 运营管理页
- 审核页
- 资源库 / 模板库 / 资产平台
- 需要 Search / Filter / Toolbar / Pagination 的数据页面

- Admin list pages
- Operations dashboards
- Review and moderation pages
- Resource libraries / template galleries / asset platforms
- Data-heavy pages with search, filter, toolbar, and pagination

## File Map
- `SKILL.md`
  - skill 入口与总工作流
  - Skill entry and high-level workflow
- `theme-color-intake.md`
  - 主题色确认流程、提问方式、输入优先级
  - Theme-color intake flow, question templates, and input priority
- `Table_List_System.md`
  - 结构规则、页面骨架、表格/列表/卡片列表选择逻辑
  - Structural rules, page anatomy, and Table/List/Card List selection logic
- `Data_Display_DESIGN.md`
  - 视觉 token、品牌覆盖规则、颜色优先级
  - Visual tokens, brand override rules, and color priority
- `index.html`
  - 展示型入口页
  - Presentation-style entry page
- `table-list-system-preview.html`
  - 验收页，展示组件与状态效果
  - Validation page for components and states

## Recommended Reading Order
1. `README.md` 或 `index.html`
2. `theme-color-intake.md`
3. `Table_List_System.md`
4. `Data_Display_DESIGN.md`
5. `table-list-system-preview.html`

1. `README.md` or `index.html`
2. `theme-color-intake.md`
3. `Table_List_System.md`
4. `Data_Display_DESIGN.md`
5. `table-list-system-preview.html`

## Workflow
1. 先确认主题色感觉、色系范围、固定 Hex 色号
2. 再判断当前页面应使用 `Table`、`List` 还是 `Card List`
3. 先按结构规则搭出页面骨架
4. 再应用视觉 token
5. 若项目根有 `DESIGN.md`，仅用于品牌壳覆盖

1. Confirm the color mood, palette family, and any fixed hex values first
2. Decide whether the page should use `Table`, `List`, or `Card List`
3. Build the page skeleton from the structural rules first
4. Apply visual tokens afterward
5. If the project root includes `DESIGN.md`, use it only as a brand-shell override

## Color Confirmation First
- 在没有颜色确认之前，不要直接输出最终视觉稿
- 如果用户只给感觉，先给 1-2 套候选色彩路径
- 如果用户给固定色号，以固定色号为最高优先级

- Do not produce the final visual treatment before color confirmation
- If the user provides only a mood, propose 1-2 candidate palette directions first
- If fixed hex values are provided, treat them as the highest-priority source

## Priority Rules
- 结构规则优先于视觉 token
- 数据可读性优先于品牌表现
- 状态表达优先于装饰性视觉
- 项目 `DESIGN.md` 只能覆盖 token，不应破坏结构与层级

- Structural rules take priority over visual tokens
- Data readability takes priority over branding
- State expression takes priority over decorative visuals
- Project-level `DESIGN.md` may override tokens only and must not break structure or hierarchy

## Prompt Snippet
```text
Read README.md and index.html first. Confirm the theme color direction with theme-color-intake.md. Then use Table_List_System.md as the structural source of truth and Data_Display_DESIGN.md as the token layer. If the project also has DESIGN.md, use it only to override tokens without breaking readability.
```

## Preview Entry
- 展示页 / Presentation page: `./index.html`
- 验收页 / Validation page: `./table-list-system-preview.html`
