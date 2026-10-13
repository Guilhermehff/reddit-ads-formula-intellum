# Homepage section and typography

1. Add an HTML Embed homepage section in the position of “Why Learn With Reddit Ads Formula”. Paste all of homepage-why-learn-embed.html. Hide the platform-generated section title for this embed so the heading appears once.
2. Replace the entire Custom CSS field with custom-css-updated.css. It preserves the existing global CSS and all three page overrides. It also sizes homepage section headings at 48px/1.1 and introductory subheads at 18px/1.1 bold with a 4px gap. Mobile headings use 36px.
3. The supplied current homepage no longer contains the old native section (1434649). Its automatic hiding rule has been removed. If you add a native section alongside the replacement embed, Intellum will display both; manage duplicates through Home Sections Layout.

The current HTML contains Figma icons, descriptions, 24px titles, shared pale #f6f9fb backgrounds, 32px grid gaps, shared 4px corners and 16px internal padding. The subhead-to-cards spacing is 40px. Full-card links still use the three staging destinations; production replacements remain deferred to migration. No JavaScript or expiring asset URLs.

The universal homepage rules target the actual #catalog_home_page wrapper verified on the public catalog. They cover native catalog headings/descriptions and the current custom HTML pattern of a top-level h1/h2 followed by a description div/p. New structures may need additional selectors. Card titles, FAQ questions, navigation, and headings on other pages are intentionally not treated as 48px section titles.

All styles specific to the replacement cards live inside their HTML. The complete Custom CSS controls shared colors, homepage typography, native card styling and platform container overrides. Exact font weight still depends on the platform loading Reddit Display Bold; the existing Roboto alias is a fallback.

Supported stacked tabloid, 2x and 4x activity-card sections receive shared styling through their card classes. The 2x and 4x responsive column rules also use classes, so replacing their section IDs does not require a styling update. All stacked tabloid activity-card homepage sections now use one column below 768px and three columns with a full-width first card from 768px. This arrangement follows the tabloid card classes, so newly created or recreated sections inherit it without updating IDs. The Custom CSS contains no catalog-section-ID selectors. Scroll, list, event and other unsupported layouts keep their previous treatment.

The old section 1430754 spacing rules and unused --raf-card-gap token have also been removed. Global rules for other platform pages remain supported even when they do not appear on the homepage.

## Maintaining the Custom CSS

The stylesheet is organized into shared tokens, native cards, navigation, metadata/difficulty chips, platform controls, landing-page wrappers, learning-path accordions and homepage layout. Repeated selectors are consolidated within their component and responsive context. Selector specificity and required platform overrides are retained.

Edit shared design values in the opening `:root` block. The native sections and HTML embeds consume these values through their own scoped layout rules:

| Variable | Current value | Purpose |
| --- | --- | --- |
| `--raf-card-padding` | 16px | Native/embed card padding, card outsets and native final-card spacing compensation; FAQ row horizontal padding |
| `--raf-section-gap` | 80px | Default homepage section rhythm |
| `--raf-section-gap-mobile` | 40px | Mobile homepage section rhythm |
| `--raf-home-gutter-mobile` | 15px | Mobile native-section gutter; card outset is capped to this gutter |
| `--raf-home-gutter-tablet` | 30px | Tablet native-section gutter |
| `--raf-heading-gap` | 4px | Native and embedded homepage heading-to-description gap |
| `--raf-description-gap` | 24px | Native section header-to-card gap |
| `--raf-view-all-gap` | 20px | Native View all footer gap |
| `--raf-motion-duration` | 160ms | Customized native and embed transitions |
| `--raf-font-sans` | Reddit Sans, Lora, Arial, sans-serif | Shared body-font stack where the existing mapping matches |
| `--raf-font-display` | Reddit Display, Roboto, Arial, sans-serif | Shared display-font stack where the existing mapping matches |
| `--raf-reading-width` | 700px | Understand, certification and FAQ reading columns |
| `--raf-wide-width` | 1280px | Shared hero inner-width limit |
| `--raf-content-gap` | 40px | Embed content flow spacing |
| `--raf-band-padding` | 40px | Hero vertical padding |
| `--raf-hero-gutter-desktop` | 80px | Approved desktop hero gutters |
| `--raf-hero-gutter-tablet` | 40px | Approved tablet hero gutters |
| `--raf-hero-gutter-mobile` | 24px | Approved mobile hero gutters |
| `--raf-page-gutter` | 24px | Reading-column outer gutters |
| `--raf-action-gap` | 12px | Embed action groups |
| `--raf-card-content-gap` | 16px | Card interior content gaps where already 16px |

Changing a token affects every native or embed rule that uses it and requires staging review. Shared values live in Custom CSS; embed selectors, layout structure, responsive rules and intentional exceptions remain inside each HTML embed. For example, desktop native homepage sections retain their 80px rhythm while embed content sections retain 40px flow spacing. Banner heights, artwork dimensions and differing heading sizes retain their approved page-specific values.

Install the complete updated Custom CSS before replacing the affected HTML embeds. Update both homepage embeds, Understand (choose the full or body-only variant), Why get certified, and FAQ. Standalone local previews have been removed; paste into Intellum and check the saved learner view directly. Preserve any newer live copy or confirmed links when applying the local files; production link changes remain deferred.

Breakpoint values remain explicit in media queries because standard CSS custom properties cannot be used directly in media-query conditions. Keep the 767/768px and 991/992px boundaries paired if changing them.

Local checks use supplied markup with a minimal platform fixture; the external tenant theme is not included. Replace the entire Custom CSS field manually, then verify the saved learner view, section recreation, links and audience restrictions in staging. Local edits and checks do not confirm live Intellum behavior.


## Homepage hero CTA

The hero title is “Reddit Ads training built for your team”. With the current Custom Head installed, “Get your team started” jumps to the visible native homepage heading “The right training for your team” and moves keyboard focus there. It resolves the heading at activation time, so section IDs and order can change. Keep that section heading text unchanged if this CTA should continue targeting it.

If the section is absent, hidden, or the Custom Head script is unavailable, the HTML link opens the existing staging Why get certified Path. Update that fallback when production destinations are confirmed. Replace both the complete homepage hero HTML and Custom Head snippets, then check the behavior in Intellum.

Difficulty chips use one decorative circle beside the visible Beginner, Intermediate or Advanced label. The shared `--raf-difficulty-dot-size` is 12px and `--raf-tag-radius` is 999px for fully rounded pills; approved colors and the 24px chip height remain unchanged. The text label communicates difficulty independently of color.
