# Changelog

## 1.0.0 - 2026-05-16

First public release of the Hermes Dashboard Bootstrap Themes pack.

- Published two portable Hermes dashboard YAML themes:
  - `bootstrap-v5-light.yaml` — Bootswatch Spacelab-inspired light theme.
  - `bootstrap-v5-dark.yaml` — Bootswatch Slate-inspired dark theme.
- Matched Bootswatch v5.3.8 color language for Spacelab and Slate while preserving Bootstrap/system font stacks.
- Added daily-use dashboard refinements for Sessions, Kanban, Models, Profiles, Config controls, Plugins/Achievements, status cards, code blocks, badges, progress bars, theme selector menus, switches, and compact metadata.
- Improved Spacelab light contrast for sidebar navigation, small labels, muted metadata, plugin cards, Kanban text, and Sessions section headings that used dark-theme blend utilities.
- Improved Slate dark readability for model capability chips, progress bars, inline code labels, expanded session code blocks, theme selector text, and filled action-button typography.
- Added sanitized preview images for public GitHub use.
- Added public release documentation, QA checklist, attribution notes, agent-maintenance guidance, and GitHub Actions validation.

## 0.1.2 - 2026-05-16

Pre-release local iteration for the Bootstrap v5 Light theme.

- Updated Bootstrap v5 Light to a Bootswatch Spacelab-inspired palette while keeping the existing system font stack.
- Matched Spacelab v5.3.8 core color tokens from https://bootswatch.com/spacelab/ and https://github.com/thomaspark/bootswatch/tree/v5/dist/spacelab.
- Reworked the light theme around Spacelab body text `#777`, primary `#446e9b`, secondary `#999`, info `#3399f3`, success `#3cb521`, warning `#d47500`, danger `#cd0200`, light `#eee`, and dark `#333`.
- Added Spacelab-style raised blue gradients for primary action buttons while preserving Bootstrap/system fonts.
- Ported the earlier dark-theme refinements into light equivalents for Profiles action buttons, Config custom selects, success-green toggles, theme selector contrast, Models chips/progress bars, inline code, and expanded Sessions transcript code blocks with compact 10px code text.
- Installed `bootstrap-v5-light` locally and applied it in the dashboard for review.
- Improved Spacelab light sidebar contrast by replacing low-opacity cyan nav text with accessible Spacelab primary blue and dark gray states.
- Strengthened light-theme contrast for small badges, muted labels, Achievements plugin badges/filters/cards, and Kanban metadata/labels/placeholders using Spacelab-compatible dark grays and tinted surfaces.
- Fixed Sessions section headings such as `CONNECTED PLATFORMS` and `RECENT SESSIONS` by disabling dark-theme `blend-lighter` blending on light cards and rendering them in Spacelab primary blue.

## 0.1.1 - 2026-05-15

Pre-release local iteration for the Bootstrap v5 Dark theme.

- Updated Bootstrap v5 Dark to a Bootswatch Slate-inspired palette.
- Matched Slate v5.3.8 core tokens from https://bootswatch.com/slate/ and https://github.com/thomaspark/bootswatch/tree/v5/dist/slate.
- Reworked dark theme colors around Slate graphite body `#272b30`, card surface `#32383e`, primary `#3a3f44`, secondary `#7a8288`, info `#5bc0de`, success `#62c462`, warning `#f89406`, danger `#ee5f5b`, white links, and soft gray body text.
- Added Slate-like card/header shadows, borders, white Bootstrap-style inputs, and refreshed Sessions/Kanban screenshots.
- Improved Models page capability chip contrast for Tools, Vision, Reasoning, and model-family chips while keeping Slate-style accent colors.
- Restyled Models page token progress bars with Slate-style recessed tracks, pill geometry, and contextual progress colors for cache/read, reasoning, input, and output segments.
- Updated inline code styling, including plugin slot labels such as `sessions:top`, with a dark Slate code background and readable accent text.
- Updated filled action buttons such as Profiles `+ Create` to use Slate/Bootstrap sans-serif typography and Slate primary button coloring.
- Tuned Profiles edit-mode actions so `Save` stays compact as a Slate primary button and `Cancel` uses a balanced Slate link-button style.
- Styled Config custom select/combobox fields to match Bootswatch Slate `.form-select` controls and dropdown listboxes.
- Updated checked/on toggle switches to use a Slate success-green track with white thumb while leaving off switches subdued gray.
- Improved theme selector dropdown description contrast for both normal white rows and the selected dark Slate row.
- Strengthened the theme selector menu heading contrast with dark, bold Bootstrap-style heading text.
- Fixed expanded Sessions transcript code blocks so fenced JSON uses Slate-dark `<pre><code>` styling instead of inheriting bright inline-code backgrounds, with compact 10px code text.

## 0.1.0 - 2026-05-15

Initial private-review theme pack.

- Added polished Bootstrap v5 Light and Bootstrap v5 Dark Hermes dashboard themes.
- Aligned colors, typography, radius, and focus rings with Bootstrap 5.3 defaults.
- Added custom CSS for daily-use readability, native font stacks, form controls, code blocks, links, and reduced-motion behavior.
- Added portable install instructions, validation notes, license, and screenshot placeholders.
