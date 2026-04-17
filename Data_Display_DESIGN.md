# Data Display Design

## Purpose
Define the visual token shell for data-display pages. This file does not determine page structure; it defines a unified visual language without harming readability.

## Priority
- Structure and interaction: follow `Table_List_System.md`
- Visual tokens: follow this file
- If conflicts happen, prioritize structural clarity, reasonable density, and clear state recognition

## Color Confirmation First
- Confirm the theme-color direction with the user before applying any visual tokens
- Confirm color mood first, then palette family, then whether fixed hex values exist
- If the user provides only descriptive direction, propose 1-2 palette options before locking one
- If fixed brand hex values are provided, derive primary, soft-fill, hover, and border-adjacent tones from them
- Do not produce a final visual direction before color confirmation is complete
- Refer to `./theme-color-intake.md` for standard prompts and candidate-output formats

## Brand Intent
- Tone: calm, professional, restrained, trustworthy
- Goal: help users scan quickly and make decisions, not browse immersively
- Avoid: heavy skeuomorphism, flashy gradients, exaggerated radius, colorful noise, decorative shadows

## Color Tokens
- `--bg-app`: `#f5f7fb`
- `--bg-surface`: `#ffffff`
- `--bg-surface-muted`: `#f7f8fc`
- `--bg-hover`: `#eef3ff`
- `--border-default`: `#d9e0ef`
- `--border-strong`: `#c6d0e5`
- `--text-primary`: `#162033`
- `--text-secondary`: `#5b6780`
- `--text-tertiary`: `#8b96ab`
- `--brand-primary`: `#315efb`
- `--brand-primary-soft`: `#e8eeff`
- `--success`: `#117a43`
- `--success-soft`: `#e9f7ef`
- `--warning`: `#b26a00`
- `--warning-soft`: `#fff4df`
- `--danger`: `#b42318`
- `--danger-soft`: `#fdeceb`
- `--info`: `#155eef`
- `--info-soft`: `#eaf1ff`

## Typography Tokens
- `--font-sans`: `"Inter", "PingFang SC", "Noto Sans SC", sans-serif`
- `--font-size-12`: `12px`
- `--font-size-13`: `13px`
- `--font-size-14`: `14px`
- `--font-size-16`: `16px`
- `--font-size-20`: `20px`
- `--font-size-28`: `28px`
- `--line-height-tight`: `1.25`
- `--line-height-normal`: `1.5`
- `--weight-medium`: `500`
- `--weight-semibold`: `600`
- `--weight-bold`: `700`

## Radius Tokens
- `--radius-xs`: `8px`
- `--radius-sm`: `10px`
- `--radius-md`: `14px`
- `--radius-lg`: `18px`

## Shadow Tokens
- `--shadow-sm`: `0 1px 2px rgba(18, 28, 45, 0.04)`
- `--shadow-md`: `0 8px 24px rgba(18, 28, 45, 0.06)`

## Spacing Tokens
- `--space-4`: `4px`
- `--space-8`: `8px`
- `--space-12`: `12px`
- `--space-16`: `16px`
- `--space-20`: `20px`
- `--space-24`: `24px`
- `--space-32`: `32px`

## Surface Rules
- Use `--bg-app` for the page background
- Use `--bg-surface` for primary data containers
- Use `--bg-surface-muted` for filter bars and secondary sections
- Prefer light borders over heavy shadows for separation

## Table Visual Rules
- Separate headers gently from body rows without high-contrast inversion
- Use `--bg-hover` for row hover states
- Prefer `--border-default` for dividers
- Keep numeric, status, and action columns visually restrained

## List And Card Visual Rules
- Keep list items consistent in padding and boundaries
- Let cards rely on outline and whitespace instead of marketing-style gradients
- Use small, precise areas of color for tags and statuses

## Status Styling
- Use dark text + soft background + light border for success, warning, error, and info states
- Do not rely on color alone; state labels must remain explicit
- Error blocks may strengthen borders or add a left indicator, but should avoid large high-saturation red fills

## Agent Instructions
- Build structure from `Table_List_System.md` first
- Use this file for color, weight, border, radius, shadow, and spacing tokens
- If a brand layer is required, replace tokens only and keep structure intact
- If the page contains multiple data modules, keep a single token system throughout

## Optional Brand Layering
- If the user specifies a brand `DESIGN.md`, allow overrides for:
  - `--brand-primary`
  - `--brand-primary-soft`
  - font family
  - radius scale
  - shadow intensity
- Do not allow the brand layer to override:
  - semantic state meaning
  - table alignment rules
  - information hierarchy
  - baseline state readability

## Theme Color Intake
- Theme-color input priority:
  1. fixed hex values provided by the user
  2. brand VI or existing `DESIGN.md` specified by the user
  3. user-described mood and palette preference
  4. default tokens in this file
- If multiple inputs conflict, higher-priority sources override lower-priority ones
- Use the default blue token set only when none of the higher-priority inputs exist
