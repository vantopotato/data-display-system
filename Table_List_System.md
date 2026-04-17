# Table List System

## Purpose
Provide AI agents with an executable structural specification for high-frequency data-display pages such as admin lists, operations panels, review queues, resource libraries, order pages, and user pages.

This specification focuses on:
- Table
- List
- Card List
- Search / Filter / Toolbar / Batch Action / Pagination
- Loading / Empty / Error / No Result

This specification has higher priority than brand-visual rules. If `DESIGN.md` conflicts with this file, prioritize data readability, action discoverability, and state recognition.

## Core Principle
- Follow Ant Design's data-display logic: clear, stable, and low cognitive load
- Allow brand tokens to change the look without weakening density control, alignment, state expression, or table readability
- Define one primary display mode per page; if Table, List, and Card List coexist, keep hierarchy and section boundaries explicit

## Component Selection

### Use Table When
- Data fields are fixed and horizontal comparison matters
- Users need sorting, filtering, bulk selection, or bulk actions
- Each record has more than 4 fields with consistent column definitions
- The page goal is scanning, comparing, processing, reviewing, or exporting

### Use List When
- Record structures are flexible and field importance is uneven
- Each record needs richer summaries, tags, descriptions, or secondary metadata
- The goal is fast browsing, filtering, and entering detail views instead of strict column comparison

### Use Card List When
- Records include covers, avatars, thumbnails, state blocks, or richer grouped metadata
- The page needs stronger chunking or more natural narrow-screen behavior
- The page is closer to asset browsing, content libraries, template galleries, or project libraries

### Avoid
- Do not force obviously structured dense data into cards
- Do not force highly heterogeneous content into tables
- Do not use all three display modes at the same page level without a clear reason

## Page Anatomy
- Header: page title, summary description, primary action
- Search / Filter Bar: keyword search, status filter, date filter, enum filter
- Toolbar: bulk actions, export, column settings, density switch, view switch
- Data Region: the primary Table / List / Card List area
- Footer Controls: pagination, total count, page size, selection summary

### Header Rules
- Left-align the title
- Allow one short supporting line under the title when needed
- Place the primary action on the right; keep one primary action and at most 1-3 secondary actions

### Filter Bar Rules
- Place search on the left and prioritize keyword input
- Keep high-frequency filters visible and collapse lower-frequency filters into advanced controls
- Use this default order: keyword > status > type > time > owner / source / tags
- Keep a clear visual separation between filters and the data region

### Toolbar Rules
- Activate bulk actions only when rows are selected
- Show view switching only when the same dataset supports multiple display modes
- Place column settings, density controls, and export actions on the right

## Table Rules

### Columns
- Use column types such as primary info, text, numeric, status, time, tags, and actions
- Place the primary info column on the far left
- Keep the action column on the far right with stable width
- Right-align numeric columns, left-align text columns, and keep status alignment consistent across the page
- Use a single time format and avoid mixing relative and absolute timestamps in the same table

### Column-Level Alignment Contract
- Define alignment at the column level, not cell by cell
- Keep every cell in the same column aligned under the same rule as its header
- Do not center one row and left-align another inside the same semantic column
- Use these defaults unless there is a strong reason not to:
  - selection: center
  - primary info: left
  - text: left
  - status / tags: left
  - owner / assignee: left
  - numeric: right
  - time / date: left
  - actions: right
- Keep action links, badges, and metadata blocks aligned to the column rule instead of using ad hoc local alignment
- If a column needs a different alignment rule, apply it to the full column, including header and body

### Width Strategy
- Keep the primary info column flexible
- Use fixed or minimum widths for status, time, and action columns
- Do not split width evenly across all columns
- Truncate long text by default and reveal full values through tooltip, detail view, or expansion

### Header Style
- Visually separate the header row from body rows
- Keep header labels short and direct
- Make sortable columns visibly sortable

### Row Density
- Support `comfortable` and `compact` density modes
- Default to `comfortable`
- Let density affect spacing only, not alignment logic or type scale

### Cell Content
- Keep one primary meaning per cell; allow secondary information only when it stays within two levels
- Use `-` for empty values
- Prefer badge / tag components for status instead of color alone
- Use inline links only for navigable primary information
- Treat the cell as a container that inherits the column alignment rule
- Keep multi-line cells internally aligned to the same column edge
- Do not use centered badges or links inside a left-aligned column unless the whole column is defined as centered
- Do not let action cells drift left while numeric or status columns stay visually rigid

### Selection And Batch Actions
- Show row selection only when the page has a real batch-processing use case
- Surface selected count and available bulk actions after selection
- Keep bulk actions limited and high-frequency, ideally no more than 3

### Row Actions
- Show 1-2 common actions directly
- Move low-frequency actions into an overflow menu
- Keep high-risk actions secondary and out of the main focus path

### Sorting / Filtering
- Expose only high-value sorting options by default
- Do not duplicate the same filter dimension both inside the table and outside it
- Keep sort state and filter state visible and clearable

## List Rules

### Information Hierarchy
- Each list item should include a primary title, secondary metadata, status, and action area
- Make the title strongest, summaries and tags secondary, and time/source tertiary
- Keep list items within three visual hierarchy levels

### Common Patterns
- Avatar / thumbnail + title + summary + metadata + tags + actions
- Title + two-column metadata + status + right-side actions
- Content summary + last updated time + owner + status

### Actions
- Keep actions in a stable location on the right or top-right
- Hover may enhance visibility, but actions must stay discoverable on mobile

## Card List Rules
- Use cards for browse-heavy and comparison-light scenarios
- Follow this internal order: cover/icon > title > key metadata > tags/status > actions
- Keep cards on a stable grid instead of a chaotic masonry layout unless the page is explicitly discovery-driven
- Clamp titles to 2 lines and summaries to 2-3 lines

## Status Rules

### Loading
- Use skeletons or structured placeholders
- Preserve the real page layout instead of showing only a spinner

### Empty
- Use for truly empty datasets
- Provide a short explanation and a useful next action

### No Result
- Use when data exists but the current search or filter yields nothing
- Tell users to adjust filters or clear search

### Error
- Clarify whether the failure is load-related or permission-related
- Provide retry or refresh actions

### Disabled
- Explain why something is disabled instead of only dimming it

## Responsive Rules
- Design desktop first
- On narrow screens, preserve the primary info, status, and time columns first
- Hide, fold, or move secondary columns into details or card views as needed
- Do not force full 8+ column tables on mobile
- Horizontal scrolling is allowed as an intermediate state, but keep enough context visible

## Do
- Use consistent alignment to support rapid scanning
- Make status, time, and primary title easy to locate at first glance
- Provide clear feedback for selection, sorting, and filtering
- Keep whitespace stable and avoid decorative backgrounds that compete with data
- Keep the page focused on finding, comparing, processing, and entering details
- Make the header and body read like one shared grid
- Let users learn alignment once per column instead of re-parsing each row

## Don't
- Do not stack too many colors, icons, and badges inside a single cell
- Do not flatten every filter onto one line
- Do not let the action column become too wide or show more than 4 direct actions
- Do not express status through color alone
- Do not add strong gradients, heavy shadows, or decorative textures for branding
- Do not decide alignment per row or per individual cell
- Do not mix left-aligned and centered statuses in the same table
- Do not let the action column visually float without a stable right edge

## Prompt Contract For Agents
- First determine whether the current scenario should use `Table`, `List`, or `Card List`
- Build the page skeleton, hierarchy, filters, and states from this file first
- Apply tokens from `Data_Display_DESIGN.md` or the project-root `DESIGN.md` afterward
- If brand styling conflicts with readability, keep readability
- Any HTML output must contain at least one clear primary data-display area instead of a loose component collage

## Deliverable Checklist
- The primary display mode is explicit
- Search / filter / toolbar / data region / pagination are complete, or their omission is clearly justified
- State handling is complete, including loading / empty / no result / error
- Primary info, status, time, and actions are quickly scannable
- Responsive behavior is explicit and not left to guesswork
