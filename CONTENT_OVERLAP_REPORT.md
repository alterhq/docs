# Content overlap report

Date: 2026-03-06

## Scope

This report reviews overlap in the current docs after the `guides/*` migration, with focus on English canonical pages.

## Current status

- No `guides/*` files remain.
- No `/guides/` links remain in MDX files.
- `docs.json` navigation has no `guides/*` entries.
- `mint validate` passes.
- `mint broken-links` passes.

## Method

- Compared related pages by section, title intent, and approximate body size.
- Flagged overlaps where multiple pages appear to serve the same user intent.
- Prioritized by risk of user confusion and maintenance cost.

## High-confidence overlaps

## 1) Settings cluster (highest priority)

Pages:

- `how-to/settings.mdx` (quick entry, ~31 words)
- `how-to/manage-settings.mdx` (short guide, ~95 words)
- `how-to/settings-guide.mdx` (deep guide, ~1646 words)
- `how-to/alter-settings.mdx` (deep guide, ~1243 words)

What overlaps:

- Two deep pages (`settings-guide` and `alter-settings`) cover mostly the same tabs and concepts.
- One medium page (`manage-settings`) repeats the same objective at a lighter level.
- One short page (`settings`) is a useful quick action page and should stay minimal.

Recommendation:

- Keep `how-to/settings.mdx` as the short "open settings" task page.
- Keep one deep canonical settings guide only.
  - Prefer `how-to/settings-guide.mdx` as canonical base (already structured and locally hosted image paths).
- Merge value from `how-to/alter-settings.mdx` into canonical guide, then retire `how-to/alter-settings.mdx`.
- Fold `how-to/manage-settings.mdx` into canonical guide (or keep as a tiny hub page only if needed for IA).

## 2) Tool Manager pair (high priority)

Pages:

- `how-to/tool-manager.mdx` (~85 words)
- `how-to/tool-manager-guide.mdx` (~196 words)

What overlaps:

- Both are task pages with similar goals and steps.
- Current split is workable, but distinction is weak.

Recommendation:

- Keep both only if the intent is explicit:
  - `how-to/tool-manager.mdx` = 60-second quick task.
  - `how-to/tool-manager-guide.mdx` = setup strategy and troubleshooting.
- If you want less maintenance, merge into one page and keep `how-to/tool-manager.mdx` as canonical.

## 3) Open Alter pair (medium priority)

Pages:

- `how-to/open-alter.mdx` (~33 words)
- `getting-started/open-alter.mdx` (~87 words)

What overlaps:

- Both explain the same action.
- This can be acceptable if one is onboarding context and one is quick task.

Recommendation:

- Keep both, but sharpen separation:
  - `getting-started/open-alter.mdx` = first-time context + first prompt.
  - `how-to/open-alter.mdx` = quick instruction only.
- Ensure each page links to the other with explicit intent labels.

## 4) Integrations overview vs guide (medium priority)

Pages:

- `apps-tools/integrations-overview.mdx` (~61 words)
- `apps-tools/integrations-guide.mdx` (~1376 words)

What overlaps:

- Not a strict duplicate, but titles are very close and may confuse users.

Recommendation:

- Keep both but rename for clarity:
  - `integrations-overview` -> short orientation page.
  - `integrations-guide` -> implementation and troubleshooting guide.
- Add one-line scope statement at top of each page.

## 5) API Router hub vs detailed pages (low priority)

Pages:

- `references/api-router-overview.mdx` (~342 words)
- `api-router/api-gateway.mdx` (~253 words)
- `api-router/development.mdx` (~214 words)
- `api-router/operations.mdx` (~245 words)

What overlaps:

- Some conceptual overlap is expected and healthy.

Recommendation:

- Keep all four.
- Ensure `references/api-router-overview.mdx` stays a hub and does not absorb setup/troubleshooting details already covered elsewhere.

---

## Proposed consolidation plan

## Phase A - decide canonicals (small)

- [ ] Settings canonical: pick `settings-guide` as source of truth.
- [ ] Tool manager strategy: keep two pages vs merge to one.
- [ ] Confirm open-alter dual-page strategy.

## Phase B - merge and tighten (medium)

- [ ] Merge `how-to/alter-settings.mdx` into `how-to/settings-guide.mdx` and retire old page.
- [ ] Merge or retire `how-to/manage-settings.mdx`.
- [ ] Add intent line at top of `apps-tools/integrations-overview.mdx` and `apps-tools/integrations-guide.mdx`.

## Phase C - polish links (small)

- [ ] Update internal links to canonical pages after retirements.
- [ ] Re-run `mint broken-links` and `mint validate`.

---

## Quick wins first

1. Consolidate settings pages (largest maintenance reduction).
2. Clarify or merge tool manager pages.
3. Keep open-alter split, but sharpen intent copy.

## Definition of done for overlap cleanup

- No topic has more than one deep canonical guide unless explicitly justified.
- Any quick page has a clearly distinct purpose from its related deep page.
- Navigation labels and page intros make page scope obvious in under 5 seconds.
