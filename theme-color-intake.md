# Theme Color Intake

## Purpose
Confirm the theme-color direction with a minimal but stable workflow before implementing the visual layer of a data-display page. Do not default to sample tokens without this step.

## Required Intake Order
1. Confirm the intended color mood
2. Confirm the palette family
3. Confirm whether fixed hex values exist

## Acceptable Inputs

### 1. Color Mood
- Calm
- Tech
- Premium
- Warm
- Neutral
- Sharp
- Soft

### 2. Palette Family
- Blue
- Cyan
- Green
- Orange
- Red
- Grayscale
- Multicolor accents

### 3. Fixed Hex Values
- Brand primary
- Support colors
- Restricted colors
- Semantic-color constraints

## Input Priority
1. Fixed hex values provided by the user
2. User-specified brand VI or project `DESIGN.md`
3. User-described mood and palette family
4. Default tokens in the current skill

## Default Interaction Rules
- If fixed hex values are provided, derive tokens from them directly instead of guessing a new primary color
- If only a mood is provided, propose 1-2 palette directions before continuing
- If only a palette family is provided, ask for the intended style mood before locking it
- If no color input exists, ask before producing the final visual direction

## Standard Questions

### Minimal Prompt
Confirm the theme-color direction first:
1. What mood do you want: calm, tech, premium, warm, neutral, sharp, or soft?
2. Which palette family do you prefer: blue, cyan, green, orange, red, grayscale, or multicolor accents?
3. If you already have fixed brand hex values, provide them directly.

## Candidate Output Format

### When The User Gives Only Mood
- Option A: Calm blue tech
  - Suggested primary: `#315efb`
  - Best for: data platforms, admin dashboards, analytics pages
- Option B: Deep cyan professional
  - Suggested primary: `#0f8b8d`
  - Best for: tooling dashboards, operations systems, asset platforms

### When The User Gives Fixed Hex
- Primary: `#xxxxxx`
- Soft fill: derived from the primary with low saturation and high lightness
- Hover layer: slightly darker or denser than the soft fill
- Border-adjacent tone: low-contrast tint derived from the primary

## Output Rule
- Before color confirmation is complete, provide only candidate directions and avoid the final visual treatment
