# Project Pulse implementation plan

## Goal

Create a compact Project Pulse dashboard that makes it easy for contributors to see which projects are active, who owns them, what status they are in, recent activity, and priority or risk. The dashboard should be a polished static frontend with a clear card layout and a runnable preview.

## Implementation phases

### Phase 1: Planning and file ownership

- Orchestrator coordinates the request and delegates file ownership.
- Planner defines the sequence of work, dependency order, and validation checks.
- Files assigned: `docs/project-pulse-plan.md`, `app/index.html`, `app/styles.css`, `app/project-data.json`, `.vscode/launch.json`.

### Phase 2: Design and layout

- Designer creates the experience direction for a dashboard-first interface.
- The main UX goals are strong hierarchy, status readability, card-based layout, and accessibility.
- Files assigned: `app/index.html`, `app/styles.css`.

### Phase 3: Data and implementation

- Coder implements the static dashboard using structured project data.
- The page reads project details from `app/project-data.json` and renders them as visible project cards.
- Files assigned: `app/index.html`, `app/styles.css`, `app/project-data.json`.

### Phase 4: Launch and preview support

- Coder adds `.vscode/launch.json` for local preview.
- The launch configuration should serve the files in `app/` and open `index.html` in the browser.
- File assigned: `.vscode/launch.json`.

### Phase 5: Validation and handoff

- Orchestrator reviews the integrated result, confirms cross-file consistency, and writes the final summary.
- Files assigned: `docs/final-handoff.md` plus existing review inputs.

## File assignments

| File | Owner | Purpose |
| --- | --- | --- |
| `app/index.html` | Designer + Coder | Structure and card rendering for the Project Pulse dashboard |
| `app/styles.css` | Designer + Coder | Visual polish, spacing, hierarchy, badges, and responsive layout |
| `app/project-data.json` | Coder | Structured project information for ownership, status, activity, and priority |
| `.vscode/launch.json` | Coder | Run configuration that serves the app and opens the dashboard |
| `docs/project-pulse-plan.md` | Planner | Implementation guidance and validation checklist |

## Dependencies

- `app/project-data.json` must exist before the dashboard can render project details in `app/index.html`.
- `app/index.html` depends on `app/styles.css` for layout and the visual shell of the dashboard.
- `.vscode/launch.json` depends on the app being ready to preview from `app/` and opening `index.html`.
- Validation depends on the HTML, CSS, and JSON all matching the expected Project Pulse structure.

## Parallel work decisions

- Designer and Coder can work in parallel on the dashboard UI and data model once the plan is approved, as long as the same file scopes are not overlapping in risky ways.
- The page structure and styling can be authored concurrently because the CSS and markup are separate artifacts, but the final integration must be checked together.
- The launch configuration can be created after the app structure is in place, because it depends on the expected app folder and target page.

## Validation expectations

The dashboard is considered complete when:

- `app/index.html` contains the exact title `Project Pulse`.
- `app/index.html` links to `styles.css` and requests `project-data.json`.
- Each project card includes visible values for status, recent activity, and priority.
- `app/styles.css` includes `.dashboard` and `.project-card` selectors.
- The CSS includes polished styling such as `border-radius` and `box-shadow`.
- `app/project-data.json` is valid JSON and contains a top-level `projects` array.
- `.vscode/launch.json` exists and includes the configuration named `Run Project Pulse Dashboard`.
- The debug configuration serves from `app/` and opens `http://localhost:%s/index.html`.

## Open questions

- None at this stage; the requirements are explicit and the implementation work can proceed directly.
