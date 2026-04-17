# data-display-system

中英双语的数据展示设计系统，面向后台列表页、数据表、资源管理页、审核页与运营页。  
A bilingual data-display design system for admin lists, data tables, resource management pages, review flows, and operations dashboards.

## Overview

`data-display-system` 提供一套适合数据密集型后台页面的结构规则与视觉 token，重点解决以下问题：
- Search / Filter / Toolbar / Table / Pagination 的统一组织
- 数据可读性优先的后台信息层级
- 加载、空态、无结果、错误态的明确表达
- 品牌色可覆盖，但不牺牲扫描效率与状态识别

`data-display-system` provides a structure-first and token-based approach for data-heavy admin pages, with emphasis on:
- consistent organization of Search / Filter / Toolbar / Table / Pagination
- readable information hierarchy for operational interfaces
- explicit loading, empty, no-result, and error states
- brand customization without sacrificing scanability or state clarity

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

## What Is Included

- [SKILL.md](./SKILL.md): skill 入口与总工作流
- [theme-color-intake.md](./theme-color-intake.md): 主题色确认流程与输入优先级
- [Table_List_System.md](./Table_List_System.md): 结构规则、页面骨架、表格/列表/卡片列表选择逻辑
- [Data_Display_DESIGN.md](./Data_Display_DESIGN.md): 视觉 token、品牌覆盖规则、颜色优先级
- [index.html](./index.html): 展示型入口页
- [table-list-system-preview.html](./table-list-system-preview.html): 验收页，展示组件与状态效果

## Recommended Reading Order

1. [README.md](./README.md) or [index.html](./index.html)
2. [theme-color-intake.md](./theme-color-intake.md)
3. [Table_List_System.md](./Table_List_System.md)
4. [Data_Display_DESIGN.md](./Data_Display_DESIGN.md)
5. [table-list-system-preview.html](./table-list-system-preview.html)

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

## Preview

- 展示页 / Presentation page: [index.html](./index.html)
- 验收页 / Validation page: [table-list-system-preview.html](./table-list-system-preview.html)

可直接在浏览器中打开本地 HTML 文件进行预览。  
You can preview the system by opening the local HTML files directly in a browser.

## Usage Principles

- 结构规则优先于视觉 token
- 数据可读性优先于品牌表现
- 状态表达优先于装饰性视觉
- 项目 `DESIGN.md` 只能覆盖 token，不应破坏结构与层级

- Structural rules take priority over visual tokens
- Data readability takes priority over branding
- State expression takes priority over decorative visuals
- Project-level `DESIGN.md` may override tokens only and must not break structure or hierarchy

## Inspiration And Disclaimer

- 本项目可开源发布。
- 设计方法与部分交互组织灵感来源于 Ant Design 的数据展示与后台设计思路。
- 本项目为独立整理与实现，不隶属于 Ant Design 或蚂蚁集团，也不代表其官方立场。

- This project is intended for open-source release.
- Parts of the design approach and interaction organization are inspired by Ant Design's data-display and admin design patterns.
- This is an independent work and is not affiliated with, endorsed by, or officially representing Ant Design or Ant Group.

## License

[MIT](./LICENSE)
