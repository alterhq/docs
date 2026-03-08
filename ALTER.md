# ALTER.md

Rules for AI agents contributing to this Alter documentation repository.

## About This Project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint validate` for local checks
- Do **not** run `mint broken-links` on every local edit; broken link checks run in GitHub Actions CI

## 1) First Principles

- Follow progressive disclosure.
- Keep `SKILL.md` short and routing-focused.
- Put detailed content in `workflows/`, `apps-tools/`, `how-to/`, `references/`, `common-issues/`, and onboarding content in `getting-started/`.
- Do not invent product facts. If unsure, mark as needing verification.

## 2) Content Placement

- `getting-started/`: onboarding-first pages for new users ("normie" friendly).
- `workflows/`: primary walkthroughs organized by user outcomes and jobs to be done.
- `apps-tools/`: app integrations, tool capabilities, and integration troubleshooting.
- `how-to/`: short configuration and quick-task instructions.
- `common-issues/`: symptoms, causes, fixes, and verification steps.
- `references/`: stable canonical information, FAQs, and docs map content.
- `api-router/`: API Router setup, operations, and integration guides.

When adding a new file, update the relevant `INDEX.md`.

## 2.1) Information architecture and navigation rules

- Keep top-level tab content unique in `docs.json`. Do not duplicate the same page in multiple tabs.
- If similar content is needed in multiple places, create dedicated pages for each section and cross-link them.
- `Getting Started` should contain only onboarding-specific pages under `getting-started/` plus `index` and `quickstart`.
- `Workflows` should contain deeper product walkthroughs under `workflows/`.
- `Apps & Tools` should contain integration and capability docs under `apps-tools/`.
- `How to` should contain short setup/configuration tasks under `how-to/`.
- `Troubleshooting` should contain issue-resolution content under `common-issues/`.
- `Reference` should contain FAQs and canonical references under `references/`.
- `API Router` owns API-router-specific docs (for example `api-router/api-gateway`, `api-router/development`, `api-router/operations`, `references/api-router-overview`, `references/api-model-names`).
- Prefer an onboarding flow: basics first, then best practices, then advanced workflows and settings.

## 2.2) Internationalization (i18n)

- The docs now support multi-language navigation using `navigation.languages` in `docs.json`.
- English uses `language: "en"` and remains the canonical source language.
- French uses `language: "fr"` with files under `fr/`.
- Keep mirrored paths when possible (for example `quickstart.mdx` -> `fr/quickstart.mdx`).
- If a page is not translated yet, do not add it to French navigation until the file exists.
- Keep top-level tab entries unique per language configuration to avoid Mintlify routing conflicts.
- Translate frontmatter (`title`, `description`) and user-facing labels in tabs/groups/cards.

## 3) Assets And Links

- Bundle media under `images/` directory.
- In docs, reference media with relative paths (e.g., `/images/getting-started/open-notch.gif`).
- Use local asset paths, not external URLs.

## 4) Writing Quality

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- AI-assisted content is welcome, but must be fact-checked.
- Avoid low-signal filler or repetitive "AI slop".
- Keep answers digestible and useful for the community.
- External resources (social posts, YouTube, personal blogs) are allowed when clearly relevant.

## 5) Templates And Naming

- Use folder templates prefixed with `_`, for example `_TEMPLATE.md`.
- Keep filenames descriptive and kebab-case.

## 6) Commits

Use [Conventional Commits](https://www.conventionalcommits.org/).

Examples:

- `docs(guides): add callback integration examples`
- `fix(common-issues): clarify device-limit troubleshooting`
- `chore(assets): add callback screenshot to manifest`

## Terminology

- Use "workspace" not "project"
- Use "action" for AI-powered tasks
- Use "context" for files/app data sent to AI
- Keep command-line/tool names untranslated across all languages (for example: `cURL`, `OpenAI`, `GitHub Actions`, `Tools Manager`, `URL Callbacks`).

## Content Boundaries

- Document user-facing features only
- Don't document internal admin features
- Keep troubleshooting focused on common user issues
