# Reddit Ads Formula — Intellum source

This repository is the source of truth for the custom Reddit Ads Formula homepage and landing pages in Intellum. Changes are pasted into Intellum manually. A saved file, Git commit or local check does not confirm installation or live verification.

## Files to install

| File | Destination |
| --- | --- |
| `custom-css-updated.css` | Replace the entire Intellum Custom CSS field |
| `custom-head-updated.html` | Complete Custom Head snippet; replace the previous customization instead of appending another copy |
| `homepage-hero-embed.html` | Homepage hero HTML section |
| `homepage-why-learn-embed.html` | Homepage “Why choose Reddit Ads Formula?” HTML section |
| `reddit-ads-embed.html` | Understand Reddit Ads page, including its hero |
| `reddit-ads-body-only.html` | Alternative Understand embed when the platform supplies the hero; use one variant per page |
| `why-get-certified-embed.html` | Why get certified page |
| `faq-embed.html` | FAQ page |

## Repository organization

- Root HTML and CSS files are the complete paste-ready sources.
- [docs/](docs/) contains installation and maintenance guides.
- [previews/](previews/) contains standalone local previews. Open them in a browser; do not paste them into Intellum. They load `../custom-css-updated.css`.
- [amend-review-decisions.json](amend-review-decisions.json) records approved changes, exclusions, superseding decisions and verification status.
- `local-archive/` holds older snippets, notes, validation records and generated ZIPs on this computer. It is ignored by Git and is not part of the published source. Earlier reports referenced by the decision history can be found there locally.

## Styling system

Shared colors, typography and recurring measurements live in the opening `:root` block of Custom CSS. Platform container overrides and native components also live in Custom CSS. Embed selectors, layout structure, responsive rules and page-specific differences remain inside each HTML embed.

Supported native stacked homepage layouts use card classes rather than section IDs. Tabloid sections use one column below 768px and three columns with a full-width first card from 768px. Existing 2x and 4x tile arrangements also follow layout classes. Other layout types retain their established treatment.

See [the homepage and shared-token guide](docs/HOMEPAGE-SETUP.md) for measurements and maintenance guidance.

## Install and verify

1. Review the decision record and preserve any newer live copy or confirmed links before replacing a field. Some homepage links still point to staging; production replacements are deferred until destinations are confirmed.
2. Back up the current Intellum fields, then install the complete Custom CSS before the affected HTML embeds. Use the complete Custom Head snippet when updating that customization.
3. Paste each embed into its matching HTML editor, including its `<style>` block. Preview and save. Keep native headers, footer and learning controls platform-owned, with scoped overrides where required.
4. Check desktop, tablet and mobile learner views, keyboard focus, pointer hover and all links. Test a newly created/recreated tabloid section and representative company restrictions using Intellum's native settings.
5. Record which commit was installed and whether staging or production verification passed. Do not label a local-only version as live verified.

Icons are included directly in the HTML, certification images are embedded as PNG data, and difficulty bars are drawn with CSS; no separate artwork folders are required. Typography relies on the fonts and aliases configured in the tenant. Decorative placeholders remain in some files; replace them with approved hosted artwork when available. The Custom Head script manages native difficulty labels and Follow text; it does not manage links or audience permissions.

## Versioning with GitHub Desktop

Review the changed source files, create a descriptive commit, then push it to the private repository. Keep previews synchronized when editing their corresponding embed. Generated ZIPs are delivery copies and should not be committed.

This repository excludes the wider project's audit documents, temporary screenshots and unrelated working files. No package installation or build step is required to install the source files in Intellum.
