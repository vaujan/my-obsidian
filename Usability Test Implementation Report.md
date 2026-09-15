# Usability Test Implementation Report

**Date:** 13 September 2026  
**Source:** [[dev/Usability Test]]  
**Release target:** Early release readiness

## Executive summary

The highest-priority usability issues from the findings have been addressed in dependency order: window behavior first, then data-integrity feedback, reading stability, responsive navigation, file intake, and Live-mode rendering. Existing work for the slash menu, math rendering, Vim caret, Zen exit, code-block overflow, and detail-pane sidebar behavior was also covered by the repository test suite.

The early-release path is clear after a short manual smoke test on Windows. The larger workflow ideas—command palette, search redesign, tabs, richer language support, and note restructuring—should remain outside the release-critical scope until their product behavior is defined.

## Implemented in recommended order

|     1 |    P0    | Quick Capture ignored **Window Material**                    | Quick Capture now reads the saved material preference, applies it through the native window API, reacts to preference changes from the main window, and falls back to opaque if activation fails.                    |  Done  |
| ----: | :------: | ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----: |
|     2 |    P0    | “External changes merged” appeared during ordinary editing   | Automatic non-overlapping merges remain silent. A notification now appears only when concurrent edits overlap, with wording that explains what requires review.                                                      |  Done  |
|     3 |    P0    | Toggling a checkbox in Read mode changed the scroll position | The current reading viewport is captured before the task update and restored after React commits the change.                                                                                                         |  Done  |
|     4 |    P1    | Floating sidebar appeared above the smallest breakpoint      | Floating behavior is now limited to widths of 767 px and below. Medium and wide layouts keep the sidebar docked.                                                                                                     |  Done  |
|     5 |    P1    | Opening a Markdown file did not load its content immediately | Dropped or selected `.md` files now load directly into a note draft; other files continue through the existing staged-file flow. Empty Markdown files receive a clear error.                                         |  Done  |
| Order | Priority | Finding                                                      | Resolution                                                                                                                                                                                                           | Status |
|     6 |    P1    | Remote images and Mermaid did not render in Live mode        | Remote HTTP(S) images render lazily with a no-referrer policy. Inactive Mermaid fences render as theme-aware diagrams and return to editable source when active. Invalid diagrams preserve their source as fallback. |  Done  |

## Existing findings verified by automated checks

- Slash commands open for an eligible active word in Live mode.
- Math blocks use the shared rendered code-card presentation in Read and Live modes.
- Note selection persists across editor mode changes.
- The Zen-mode exit control and detail-pane sidebar controls remain represented in the interface contract.
- Editable note surfaces prevent app-level horizontal overflow.
- Reduced-transparency behavior continues to preserve the user’s material preference.

## Verification

- TypeScript checks passed for the Electron main process and renderer.
- Full test suite: **268 passed, 4 skipped, 0 failed**.
- Diff whitespace validation passed.
- Focused regression coverage was added for every changed behavior.

## Phase 2 integration

Phase 2 connects the existing keyboard, search, editing, and performance foundations instead of
introducing parallel implementations.

| Area | Integrated behavior | Status |
| --- | --- | :---: |
| Find or create | `Ctrl+K` now opens **Find or create item**. The same query can open an existing result or create a note whose initial heading and title use the query. | Done |
| Keyboard-first notes | `Ctrl+N` remains the direct blank-note path and focuses the canonical full-detail editor. Repeating it after persistence starts another note; an unpersisted draft is protected from replacement. | Verified |
| Performance telemetry | Packaged measurements now report settled CPU usage, working-set memory, and process count together, alongside startup and typing responsiveness. | Done |
| External navigation | Rendered HTTP links route through the validated main-process system-browser action. Rendered images use in-app zoom and do not navigate the application surface. | Verified |
| Live table and image authoring | The existing editable table widget preserves Markdown through typing, paste, IME, row/column actions, undo grouping, and image previews. | Verified |

### Phase 2 benchmark sample

The service benchmark passed on this development machine with zero no-op record writes:

| Items | Cold rebuild | Search | Rename | Archive |    RSS |
| ----: | -----------: | -----: | -----: | ------: | -----: |
|   100 |       137 ms |   1 ms |  19 ms |   18 ms | 146 MB |
| 1,000 |       989 ms |   3 ms |  29 ms |   28 ms | 197 MB |

The production build and static performance budget also passed. CPU and full-app working-set values
are emitted by the packaged runner; they still require the packaged Windows smoke run to produce
representative numbers.

## Manual release smoke test

Before cutting the early release, verify these interactions in a packaged Windows build:

1. Toggle **Window Material** in the main window, then open Quick Capture with `Ctrl+Shift+Space`; confirm both opaque and Acrylic states follow the preference.
2. Edit a note while changing a different line on disk; confirm no merge toast appears. Then edit the same line in both places; confirm the concurrent-edit warning appears.
3. Scroll a long note in Read mode and toggle a checkbox; confirm the viewport remains anchored.
4. Resize across 767/768 px; confirm only the smallest layout uses the floating sidebar.
5. Drop a populated `.md` file into the workspace; confirm its text opens as an editable note draft.
6. In Live mode, verify one remote image and one Mermaid fence in light and dark themes.

## Remaining priorities

### P1 — define and address before broad beta

- Run the packaged Windows benchmark to record representative startup, idle, and typing CPU/RAM values.
- Extend the packaged scenario to multiple detached note windows only if that optional workflow remains in scope for broad beta.
- Decide whether vault search eventually needs a persistent Obsidian-style results surface in addition to **Find or create item**.

### P2 — useful after the core workflow stabilizes

- Word and character counts in Read mode.
- Separate note-content font preferences from UI and code fonts.
- Command palette for theme, settings, date insertion, Window Material, Vim, and Zen actions.
- Language selection and dictionary support.
- Duplicate note and Copy file path actions.
- Outline navigation and task counters.
- Optional single-note versus tabbed multi-note behavior.

### Research / later

- Split and merge notes by heading hierarchy.
- Version history and notification history.
- Vim navigation gaps, indentation guides, and formatting behavior in Vim modes.
- Link behavior across YAML, Read, and Live surfaces.

## Release recommendation

Proceed to the packaged Windows smoke test. If the six implemented flows pass, none of the remaining P2 or research items should block an early release; the unresolved P1 workflow and performance questions should be tracked with explicit acceptance criteria for the next milestone.
