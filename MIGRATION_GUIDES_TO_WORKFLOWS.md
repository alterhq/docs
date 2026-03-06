# Guides URL migration plan (outcome-driven docs)

This document is the step-by-step execution plan to migrate legacy `guides/*` URLs into a clearer docs structure while keeping **Workflows** as the user-facing concept.

## Goals

- Remove `guides/*` as a canonical namespace.
- Keep user-facing navigation intuitive: `Getting Started`, `Workflows`, `How to`, `Apps & Tools`, `API Router`, `Troubleshooting`, `Reference`.
- Keep outcome-driven writing as an internal standard (not a front-facing nav label).
- Preserve SEO and existing bookmarks with redirects from all old `guides/*` paths.

## Non-goals

- Full translation parity in this migration pass.
- Rewriting every page at once.
- Changing product terminology or introducing new product claims.

## Guiding principles

- Canonical URL should match user intent:
  - `getting-started/*` = onboarding fundamentals.
  - `workflows/*` = complete "get X done" flows.
  - `how-to/*` = quick, single-task instructions.
  - `apps-tools/*` = capability reference by app/tool.
  - `api-router/*` = developer and integration docs.
- Avoid duplicates. If two pages cover the same topic, keep one canonical page and merge content.
- Keep each page action-first without forcing a rigid structure.
- Prefer common building blocks as needed: user outcome, actionable steps, realistic example, verification, and recovery path.

---

## Phase plan

## Phase 0 - Prep and freeze

### Tasks

- [ ] Freeze nav and URL changes unrelated to this migration.
- [ ] Confirm canonical destination slugs in this plan.
- [ ] Create migration branch.
- [ ] Add owner + reviewer for each section.

### Exit criteria

- Canonical mapping approved.
- Team aligned on sequence and ownership.

## Phase 1 - Canonical map and nav restructuring

### Tasks

- [ ] Update `docs.json` EN navigation so no tab references `guides/*` pages.
- [ ] Place migrated pages under destination tabs/groups (see mapping below).
- [ ] Keep top-level tabs as:
  - [ ] `Getting Started`
  - [ ] `Workflows`
  - [ ] `How to`
  - [ ] `Apps & Tools`
  - [ ] `Troubleshooting`
  - [ ] `Reference`
  - [ ] `API Router`

### Exit criteria

- EN sidebar has zero `guides/*` entries.

## Phase 2 - File moves and redirects

### Tasks

- [ ] Move each `guides/*.mdx` file to its canonical destination path.
- [ ] Add redirects for every old `/guides/*` path.
- [ ] Ensure moved pages preserve frontmatter (`title`, `description`, optional `sidebarTitle`).

### Exit criteria

- Old `guides/*` URLs resolve to new canonical pages.
- No broken links from moved content.

## Phase 3 - Link rewrite (EN first)

### High-priority files

- [ ] `references/docs-map.mdx`
- [ ] `references/faq-core.mdx`
- [ ] `index.mdx`
- [ ] `quickstart.mdx`
- [ ] `getting-started/*.mdx`
- [ ] `workflows/*.mdx`

### Tasks

- [ ] Replace internal `/guides/...` links with canonical destinations.
- [ ] Validate anchors after replacements.

### Exit criteria

- No EN internal links pointing to `/guides/*` unless intentionally redirected legacy references.

## Phase 4 - Outcome-oriented rewrite pass (top pages)

### Priority pages

- [ ] `workflows/meeting-workflow`
- [ ] `workflows/manage-calendar-with-alter`
- [ ] `workflows/manage-mail-with-alter`
- [ ] `workflows/manage-reminders-with-alter`
- [ ] `workflows/manage-notes-with-alter`
- [ ] `workflows/workspaces-actions` (new path after move)
- [ ] `workflows/use-flow-orchestration` (new path after move)

### Tasks

- [ ] Rewrite for intent and clarity without using a single fixed template.
- [ ] Add practical copyable prompt examples where relevant.
- [ ] Add verification and recovery guidance where useful.

### Exit criteria

- Top workflow pages are action-first and scannable.

## Phase 5 - Localization and cleanup

### Tasks

- [ ] Decide localization policy for this migration:
  - [ ] Option A: EN-only canonical now + localized redirects later
  - [ ] Option B: migrate Tier-1 localized pages in same release
- [ ] Update locale navs once EN IA is stable.
- [ ] Remove or de-emphasize locale `guides/index` pages if no longer canonical.

### Exit criteria

- Localized nav intentionally reflects migration scope.

## Phase 6 - Validation and release

### Tasks

- [ ] Run `mint validate`.
- [ ] Manual smoke test of old and new URLs.
- [ ] Spot-check top landing pages on desktop/mobile.
- [ ] Publish release note/changelog entry for docs IA changes.

### Exit criteria

- No broken internal links.
- Redirect coverage complete for `guides/*`.

---

## Canonical mapping table (guides -> destination)

| Legacy path | New canonical path | Section | Action |
|---|---|---|---|
| `/guides/getting-started` | `/getting-started/getting-started-path` | Getting Started | move |
| `/guides/core-features` | `/getting-started/core-features` | Getting Started | move |
| `/guides/dictation` | `/workflows/dictation` | Workflows | move |
| `/guides/meetings` | `/workflows/meetings` | Workflows | move |
| `/guides/workspaces-actions` | `/workflows/workspaces-actions` | Workflows | move |
| `/guides/use-flow-orchestration` | `/workflows/use-flow-orchestration` | Workflows | move |
| `/guides/alter-actions` | `/workflows/alter-actions` | Workflows | move |
| `/guides/url-callbacks` | `/workflows/url-callbacks` | Workflows | move |
| `/guides/web-research-getting-started` | `/workflows/web-research-getting-started` | Workflows | move |
| `/guides/native-web-search-in-alter-routers` | `/workflows/native-web-search-in-alter-routers` | Workflows | move |
| `/guides/web-search-local-tools` | `/workflows/web-search-local-tools` | Workflows | move |
| `/guides/connect-tavily` | `/workflows/connect-tavily` | Workflows | move |
| `/guides/connect-firecrawl` | `/workflows/connect-firecrawl` | Workflows | move |
| `/guides/connect-linkup` | `/workflows/connect-linkup` | Workflows | move |
| `/guides/connect-exa` | `/workflows/connect-exa` | Workflows | move |
| `/guides/managing-context-window` | `/how-to/managing-context-window` | How to | move |
| `/guides/tool-manager` | `/how-to/tool-manager-guide` | How to | move (or merge into `/how-to/tool-manager`) |
| `/guides/choosing-generative-model` | `/how-to/choose-generative-model` | How to | merge into existing |
| `/guides/alter-settings` | `/how-to/alter-settings` | How to | move |
| `/guides/manage-settings` | `/how-to/settings` | How to | merge |
| `/guides/settings` | `/how-to/settings` | How to | merge |
| `/guides/integrations` | `/apps-tools/integrations-guide` | Apps & Tools | move |
| `/guides/api-gateway` | `/api-router/api-gateway` | API Router | move |
| `/guides/api-router-development` | `/api-router/development` | API Router | move |
| `/guides/api-router-operations` | `/api-router/operations` | API Router | move |
| `/guides/api-router-app-integrations` | `/api-router/app-integrations` | API Router | move |
| `/guides/typingmind-alter-api` | `/api-router/typingmind` | API Router | move |
| `/guides/msty-alter-api` | `/api-router/msty` | API Router | move |
| `/guides/index` | (retire) | N/A | remove from nav + redirect to best landing |

Notes:

- If a destination file already exists, merge content rather than duplicating.
- Final slug naming can be adjusted, but canonical section placement should stay the same.

---

## Redirect checklist

Create one redirect per legacy page.

- [ ] `/guides/getting-started` -> `/getting-started/getting-started-path`
- [ ] `/guides/core-features` -> `/getting-started/core-features`
- [ ] `/guides/dictation` -> `/workflows/dictation`
- [ ] `/guides/meetings` -> `/workflows/meetings`
- [ ] `/guides/workspaces-actions` -> `/workflows/workspaces-actions`
- [ ] `/guides/use-flow-orchestration` -> `/workflows/use-flow-orchestration`
- [ ] `/guides/alter-actions` -> `/workflows/alter-actions`
- [ ] `/guides/url-callbacks` -> `/workflows/url-callbacks`
- [ ] `/guides/web-research-getting-started` -> `/workflows/web-research-getting-started`
- [ ] `/guides/native-web-search-in-alter-routers` -> `/workflows/native-web-search-in-alter-routers`
- [ ] `/guides/web-search-local-tools` -> `/workflows/web-search-local-tools`
- [ ] `/guides/connect-tavily` -> `/workflows/connect-tavily`
- [ ] `/guides/connect-firecrawl` -> `/workflows/connect-firecrawl`
- [ ] `/guides/connect-linkup` -> `/workflows/connect-linkup`
- [ ] `/guides/connect-exa` -> `/workflows/connect-exa`
- [ ] `/guides/managing-context-window` -> `/how-to/managing-context-window`
- [ ] `/guides/tool-manager` -> `/how-to/tool-manager-guide`
- [ ] `/guides/choosing-generative-model` -> `/how-to/choose-generative-model`
- [ ] `/guides/alter-settings` -> `/how-to/alter-settings`
- [ ] `/guides/manage-settings` -> `/how-to/settings`
- [ ] `/guides/settings` -> `/how-to/settings`
- [ ] `/guides/integrations` -> `/apps-tools/integrations-guide`
- [ ] `/guides/api-gateway` -> `/api-router/api-gateway`
- [ ] `/guides/api-router-development` -> `/api-router/development`
- [ ] `/guides/api-router-operations` -> `/api-router/operations`
- [ ] `/guides/api-router-app-integrations` -> `/api-router/app-integrations`
- [ ] `/guides/typingmind-alter-api` -> `/api-router/typingmind`
- [ ] `/guides/msty-alter-api` -> `/api-router/msty`
- [ ] `/guides/index` -> `/workflows` (or chosen destination)

---

## Merge decisions needed before implementation

- [ ] `tool-manager`: keep two pages (`quick` + `guide`) or merge into one?
- [ ] `settings`: choose one canonical deep-dive page and merge others.
- [ ] `choose-generative-model`: keep existing `how-to` page and absorb guide content.
- [ ] Final naming for new API Router slugs (`/api-router/typingmind` etc.).

Owner should lock these before Phase 2 to avoid rework.

---

## Outcome-first quality cues (authoring QA)

Use these cues during content rewrite. You do not need every cue on every page:

- [ ] Page starts with user outcome (not feature description).
- [ ] Includes concrete prerequisites.
- [ ] Includes numbered "do this now" steps.
- [ ] Includes at least one realistic example prompt/command.
- [ ] Includes expected result/verification.
- [ ] Includes short troubleshooting section.
- [ ] Includes clear next-step links.
- [ ] No marketing filler language.

---

## Tracking board (fill in during execution)

## In progress

- [ ]

## Blocked

- [ ]

## Done

- [ ]

---

## Definition of done

- [ ] No canonical EN page remains under `guides/*`.
- [ ] No `guides/*` entries in EN nav.
- [ ] Redirects cover all migrated `guides/*` paths.
- [ ] Core internal links updated to canonical paths.
- [ ] `mint validate` passes.
- [ ] Top workflows are action-first and outcome-driven in structure.
