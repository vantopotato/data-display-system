# data-display-system

## Purpose
Provide AI agents with a dedicated data-display design system for admin lists, data tables, resource management pages, review pages, and operations dashboards.

This skill has two layers:
- `Table_List_System.md`: defines structure, information hierarchy, interaction, and state rules
- `Data_Display_DESIGN.md`: defines visual tokens and a replaceable brand shell

## Files
- Overview doc: `./README.md`
- Structure rules: `./Table_List_System.md`
- Visual tokens: `./Data_Display_DESIGN.md`
- Theme color intake: `./theme-color-intake.md`
- Presentation page: `./index.html`
- Preview page: `./table-list-system-preview.html`

## Recommended Reading Order
1. `README.md` or `index.html`
2. `theme-color-intake.md`
3. `Table_List_System.md`
4. `Data_Display_DESIGN.md`
5. `table-list-system-preview.html`

## How To Use
1. Confirm the theme-color direction first by aligning on color mood, palette family, and any fixed brand hex values
2. Read `Table_List_System.md` to decide whether the page should use `Table`, `List`, or `Card List`
3. Read `Data_Display_DESIGN.md` to apply colors, radius, shadows, font weights, and spacing tokens
4. If the project includes `DESIGN.md`, use it only as a brand-token override without harming readability

## Color Confirmation Workflow
- Confirm the theme-color direction before visual implementation instead of defaulting to the sample blue tokens
- Confirm at least one of the following:
  - color mood: calm / tech / premium / warm / neutral / sharp / soft
  - palette family: blue / cyan / green / orange / red / grayscale / multicolor accents
  - fixed color values: brand primary hex, support hex values, semantic-color constraints
- If the user provides only a mood, derive 1-2 candidate palette directions first
- If the user provides fixed hex values, build token variants from those values for soft fills and hover states
- If no color input is provided, ask before producing the final visual direction
- See `./theme-color-intake.md` for standard prompting and candidate-output formats

## Priority
- Structure and interaction take priority over branding
- Data readability takes priority over visual decoration
- State recognition takes priority over brand expression

## Prompt Snippet
Use `Table_List_System.md` as the structural source of truth for data display pages. Then apply `Data_Display_DESIGN.md` as the visual token layer. If a project `DESIGN.md` is also provided, use it only to override tokens without breaking readability, alignment, spacing, or state clarity.

## Deliverables
- A page with a clear data-display primary mode
- Complete search/filter/toolbar/data/pagination anatomy when relevant
- Explicit handling for loading, empty, no result, and error states
- Responsive behavior that preserves scanning efficiency

## Rules
- Do not mix multiple primary display modes without clear information hierarchy
- Do not let brand styling weaken table readability
- Do not use decorative gradients, oversized shadows, or noisy color blocks in data-heavy pages
- Prefer stable alignment, restrained color use, and explicit state feedback
- Confirm color direction before visual implementation
