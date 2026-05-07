# Five-Register Design System

A five-register design system for documents, slides, dashboards, marketing pages, in-product UI, reports, catalogues, and sustained reading objects. One vocabulary, one tokens file, twenty-three templates — designed to keep every artifact you generate consistent, considered, and recognizable.

Japanese-craft-influenced, but the discipline is in restraint, not literal Japonisme. The serif carries warmth; the structure carries everything else.

> **Try it now:** open [`templates/Index.html`](./templates/Index.html) in a browser to see the lobby that links to every template.

## The five registers

Identify the register before making any style choices. The registers share one vocabulary but never mix.

### SOUL — warm Japanese craft (default)
Outward-facing artifacts: personal, public-facing, brand. Anything a person will hold or be handed on paper or in a deck.
- **Surface:** bone paper (`#F2EDE3`), sumi ink (`#1A1714`)
- **Metals:** champagne gold, copper, brass — used the way a tea master uses gold leaf: rarely, deliberately
- **Type:** Cormorant Garamond (display, italic), Inter (body), JetBrains Mono (instruments)
- **Templates:** `Threshold.deck.html`, `Hearth.doc.html`, `Folio.memo.html`, `Kozo.letter.html`

### GENKAN — soul material on a software surface
Marketing pages, in-product UI, portfolios, catalogues — anything *digital* but soul-leaning. The genkan is the entry zone between outside and inside: warm metals, hairlines, sharp corners, cockpit-grade structural discipline.
- **Surface (light, default):** bone paper, sumi ink — same as soul
- **Surface (dark variant):** graphite, warm bone text, champagne accent at AAA contrast
- **Activate:** `<html data-register="genkan">` for light, add `data-mode="dark"` for dark
- **Stylesheet:** `genkan.css` (extends `base.css`); product primitives are `.gk-*`
- **Templates:** `Atrium.landing.html` (marketing, light), `Vellum.app.html` (in-product, light), `Engawa.darkapp.html` (in-product, dark — canonical dark-mode reference), `Foyer.catalogue.html` (catalogue / reading list)

### HIROMA — the great room (synthesis register)
The rare artifact that needs all three voices in the same composition: studio pages, case studies, capability briefs, annual reports. Soul prose, genkan structure, cockpit instrumentation — *braided, not mixed*. Each region of the page commits to one voice; the discipline is in the joinery.
- **Surface:** bone (genkan light), with paper-toned and graphite-toned instrument sashes for contrast
- **Activate:** `<html data-register="hiroma">`
- **Stylesheet:** `hiroma.css` (extends `base.css`); components prefixed `.hi-*`
- **Templates:** `Hiroma.studio.html` (canonical studio / case-study page)
- **Caveat:** the hardest register to write well. Default to soul, genkan, or cockpit. Reach for hiroma only when you genuinely need all three.

### COCKPIT — dark, modular, instrumented
Tooling, agent UIs, ops surfaces, terminals — anything you *watch* rather than *read*.
- **Surface:** graphite (`#0F1113`), charcoal panels, restrained metallic accents
- **Type:** mono-forward (JetBrains Mono primary, Inter for headings)
- **Activate:** `class="cockpit"` on `<html>` (or `data-register="cockpit"` on any container)
- **Templates:** `Bastion.dashboard.html`, `Watch.report.html`, `Rampart.missioncontrol.html`

### EVENING — lamp-lit, sustained, private
Slow reading objects — chapbooks, prayers, letters to the body, anything that must hold a difficult subject without flinching. One column, narrow measure, long fall. Read at the end of the day, alone, by lamp. *Never* used for product, marketing, or operational work.
- **Two surfaces, one discipline:**
  - **Vesper** — aubergine near-black (`#14101A`), champagne the held note. Cardo italic display.
  - **Ophelia** — inkwater green-black (`#0A1410`), drowned-rouge accent, petal-white the held note. Cormorant italic display, Source Serif 4 body.
- **Activate:** `<html data-register="vesper">` or `<html data-register="ophelia">`
- **Stylesheets:** `vesper.css` (`.ve-*`), `ophelia.css` (`.op-*`) — both extend `base.css`
- **Templates:** `Vesper.evening.html` (designer's evening prayer, five movements), `Ophelia.evening.html` (a letter to the body, five movements)

**Anti-pattern:** light-mode default for cockpit work, dark-mode default for soul work, evening register for anything operational, mixing two registers in one artifact. Pick one register per artifact and commit.

## Template gallery

Twenty-three templates across the five registers. All cross-platform, all printable where it makes sense, all accessibility-aware.

```
templates/
├── tokens.css                  ← single source of truth: palette, type, scale, motion
├── base.css                    ← reset + primitives (consumes tokens via aliases)
├── torii.css                   ← soul-register slide shell (extends base)
├── genkan.css                  ← genkan-register product shell (extends base)
├── hiroma.css                  ← hiroma-register synthesis shell (extends base)
├── vesper.css                  ← evening register · aubergine (extends base)
├── ophelia.css                 ← evening register · inkwater (extends base)
├── deck-stage.js               ← deck scaling, keyboard nav, speaker-notes
├── Index.html                  ← lobby — links to all templates
│
├── Threshold.deck.html         ← SOUL    · slide deck
├── Hearth.doc.html             ← SOUL    · long-form document
├── Folio.memo.html             ← SOUL    · one-page memo
├── Kozo.letter.html            ← SOUL    · correspondence / single-sheet letter
│
├── Atrium.landing.html         ← GENKAN  · marketing landing (light)
├── Vellum.app.html             ← GENKAN  · in-product app shell (light)
├── Engawa.darkapp.html         ← GENKAN  · in-product app shell (dark — canonical dark reference)
├── Foyer.catalogue.html        ← GENKAN  · catalogue / reading list / portfolio index
│
├── Hiroma.studio.html          ← HIROMA  · studio / case-study page (canonical synthesis)
│
├── Bastion.dashboard.html      ← COCKPIT · ops dashboard
├── Watch.report.html           ← COCKPIT · incident report
├── Rampart.missioncontrol.html ← COCKPIT · mission control (parallel agents, councils, teams)
│
├── Vesper.evening.html         ← EVENING · chapbook / evening prayer (aubergine)
└── Ophelia.evening.html        ← EVENING · sustained prose / letter (inkwater)
```

**To retune the entire system:** edit `tokens.css`. Every artifact updates.

## Quick start

### Browse the templates
```bash
git clone https://github.com/LoFiGamerGuy/five-register-design-system.git
cd five-register-design-system/templates
# Open in a browser:
open Index.html        # macOS
xdg-open Index.html    # Linux
start Index.html       # Windows (PowerShell or cmd)
```

The Index page is the lobby — it links to every template. Click around to see each register rendered.

### Use a template in your work
1. **Identify the register first.** Public-facing print/deck (soul), software with a soul voice (genkan), instrumented dark UI (cockpit), synthesis page (hiroma), or sustained private reading (evening).
2. **Pick the closest template** as a starting point — never start from a blank page.
3. **Copy the file**, rename it, replace the content. Keep the structural classes.
4. **Don't invent new colors, fonts, or spacing values.** If something feels missing, add it to `tokens.css` first so every artifact picks it up.
5. **Density is earned.** High information density is welcome when it carries weight. Ornament and decorative complexity are not.

### Naming convention for new artifacts
Names should reference mythology, literature, martial or craft traditions — particularly **thresholds, guardians, transitions, or disciplined practice**. The reference must do conceptual work, not decorate.

- ✓ Soul candidates: *Hearth, Folio, Threshold, Lantern, Garden, Inkstone, Foyer, Kozo, Washi, Sumi*
- ✓ Genkan candidates: *Atrium, Vellum, Tatami, Shoji, Sumiya, Hiroma, Doma, Foyer, Engawa, Tokonoma*
- ✓ Hiroma candidates (synthesis only — reach sparingly): *Hiroma, Hondo, Zashiki, Honmaru*
- ✓ Cockpit candidates: *Bastion, Watch, Sentinel, Rampart, Postern, Beacon, Helm, Citadel, Garrison, Pylon*
- ✓ Evening candidates: *Vesper, Ophelia, Compline, Lauds, Nocturne, Lamplight, Threnody*
- ✗ Avoid: generic codenames (Project Apollo, Phoenix, Atlas), gamer-RGB names, friendly-blob startup names, decorative mythology that doesn't earn its meaning.

### Section numbering
Use mono section markers — `§ 1`, `— 01`, `WR-2026-0430-0142`. Numbers are instruments; treat them as such.

### House voice
The studio writes in the demo voice you see on `Atrium.landing.html` and `Vellum.app.html`: warm, deliberate, slightly literary, sentences that close cleanly. Speak about the *practice* and the *artifact*, not the *product* and the *user*. The reader is invited in, not converted. If a sentence sounds like it could appear on any SaaS landing, rewrite it.

### Iconography
The system avoids decorative iconography. When a glyph is genuinely needed, use:
- a single CJK character set in mono inside a hairline box (see `.gk-nav__brand .glyph` — `門`, `十`)
- a `.gk-pip` (8px square in token color) for status
- a number — `§ 03`, `— 04` — set in `--font-mono` with `--tracking-caps`

Do not import an icon library. Do not draw line-art SVG icons. Do not use emoji.

### Typeface note
**Cormorant Garamond** is the considered choice for display in soul, genkan, hiroma, and ophelia: a contemporary Garamond revival with elegant italics that pair cleanly with **Inter**'s geometric humanism. The system is Japanese-*influenced* craft, not literal Japonisme — the serif carries warmth; the discipline is in restraint, not provenance.

**Vesper** uses **Cardo** italic instead, for a slightly older, more liturgical voice. **Ophelia** pairs Cormorant display with **Source Serif 4** body for sustained reading.

Defensible swaps: Source Serif 4 (slightly more neutral) or EB Garamond (quieter, denser texture). All swaps go through `--font-display` in `tokens.css` and the Google Fonts import at the top.

### Cormorant is for DISPLAY only
Italic Cormorant body text fails accessibility at small sizes. It is used for headings, leads, eyebrow flourishes, and pull quotes. Body text is always Inter. The `data-a11y="strict"` modifier enforces this automatically — apply it to any container that must meet WCAG AAA.

## Anti-patterns (refuse these)

- Enterprise-speak ("synergize", "leverage solutions", "best-in-class")
- Gamer RGB, neon-noir, oxblood-and-acid-green cyberpunk maximalism
- Friendly-blob startup illustration
- Generic codenames (Phoenix, Atlas, Apollo, Nova)
- Decorative mythology that doesn't do conceptual work
- Minimalism-as-emptiness (low density when density is earned)
- Light-mode default for cockpit work
- Dark-mode default for soul work
- Evening register for product, marketing, dashboards, reports, or any operational artifact
- Reaching for hiroma when soul, genkan, or cockpit alone would carry the artifact
- Inventing new colors outside the token palette
- Italic Cormorant for body text (except in evening register, where the form earns it)
- Importing an icon library
- Adding a seventh decision when six suffice

## Quick CSS reference

### Soul-register classes
- Layout: `.page`, `.page--wide`, `.page--narrow`, `.prose`, `.grid`, `.grid--{2,3,4}`
- Type: `.display`, `.h1` … `.h5`, `.eyebrow`, `.eyebrow--accent`, `.lead`, `.body`, `.small`, `.caption`, `.mono`
- Components: `.masthead`, `.colophon`, `.aside`, `.pullquote`, `.stat`, `.tag`, `.btn`, `.placeholder-img`
- Rules: `.rule`, `.rule--strong`, `.rule--ornament`

### Genkan-register classes (in `genkan.css`)
- Shell: `.gk-shell`, `.gk-container`, `.gk-container--narrow|--wide`
- Nav / footer: `.gk-nav`, `.gk-nav__inner`, `.gk-nav__brand`, `.gk-nav__menu`, `.gk-nav__link`, `.gk-footer`, `.gk-footer__inner`, `.gk-footer__col`
- Sections: `.gk-section`, `.gk-section--tight|--bleed-2|--bleed-3`, `.gk-section__head`, `.gk-section__num`, `.gk-section__title`, `.gk-section__subtitle`
- Hero: `.gk-hero`, `.gk-hero__inner`, `.gk-hero__eyebrow`, `.gk-hero__title`, `.gk-hero__lede`, `.gk-hero__actions`, `.gk-hero__meta`
- Cards / features: `.gk-card`, `.gk-card__num|__title|__body|__foot`, `.gk-feature`
- Buttons: `.gk-cta`, `.gk-cta--ghost`, `.gk-cta--text`, `.gk-cta__arrow`
- Forms: `.gk-field`, `.gk-field__label|__hint`, `.gk-input`, `.gk-select`, `.gk-textarea`
- Status: `.gk-badge`, `.gk-badge--solid|--accent|--ok|--warn`, `.gk-pip`, `.gk-pip--ok|--warn|--crit|--dim`
- In-product: `.gk-tabs`, `.gk-tab`, `.gk-table`, `.gk-empty`

### Cockpit-register patterns (in `Bastion`/`Watch`)
- Top bar with brand glyph, breadcrumb, instrument cells
- Sidebar with status pips (`ok` sage, `warn` champagne, `crit` copper, `dim` bone-4)
- KPI strip (`.kpi__k` label / `.kpi__v` value with mono numerals)
- System matrix table — mono, tabular-nums, hairline rules
- Event log (`.log__row` · time · level · message)
- Disposition strip — single-line outcome, signed
- Footer with pulse indicator

### Status colors (all registers)
- `--ok` sage / pine
- `--warn` champagne / brass
- `--info` steel / indigo
- `--crit` copper

## Accessibility

- Body text in every register meets WCAG AA against its surface; primary text meets AAA. Contrast ratios are documented inline in `tokens.css`.
- The `--sumi-3` / `--bone-3` tier is for *metadata only*; never for body copy.
- The `--sumi-4` / `--bone-4` tier and the warm metals are for *ornament only*; never for text the user must read.
- Apply `data-a11y="strict"` to any container (or `<html>`) to enforce 16px minimum body type, 1.75 line-height, no italic body text, animation-disabled. Strict mode promotes body text from `--fg-2` to `--fg`.
- All registers respect `prefers-reduced-motion` automatically.
- Visible focus rings are mandatory; `base.css` provides them on every interactive element.

## Slide decks (`deck-stage.js`)

Soul-register decks (e.g., `Threshold.deck.html`) load `deck-stage.js`, a tiny custom element that:
- Auto-scales each slide to fit the viewport while preserving 16:9 (or whatever ratio the inner canvas declares)
- Adds keyboard navigation: ←/→ between slides, `g` for grid view, `?` for help
- Stamps `data-screen-label="01 Title"` etc. on each slide for direct-edit context
- Posts `{slideIndexChanged: N}` to the parent so a host can sync speaker notes
- Falls back gracefully without JS — every slide is a real `<section>` element and prints one-per-page when the user uses the browser's print dialog

To use: import the script at the bottom of the deck, wrap slides in a `<deck-stage>` element, and put each slide as a direct child `<section>`. Speaker notes go in a `<script type="application/json" id="speaker-notes">` block of strings, indexed by slide.

## Changing fonts

The system defaults to Cormorant Garamond + Inter + JetBrains Mono.

To swap: edit `--font-display`, `--font-body`, `--font-mono` in `tokens.css` (and update the Google Fonts import at the top of each HTML file).

Avoid overused families: Fraunces, Roboto, Arial, system-ui-only stacks.

## Print

All soul-register templates and the Atrium landing print cleanly. `@media print` strips backgrounds and prevents code/aside/figure breaking across pages. Vellum and the cockpit-register templates are designed for screen.

## Contributing

Contributions are welcome — corrections, new templates that fit one of the five registers, accessibility improvements, additional language support. See [CONTRIBUTING.md](./CONTRIBUTING.md).

The system is opinionated; contributions that introduce new registers, palettes, or aesthetic directions will likely be declined unless they argue convincingly for the addition. The discipline is in restraint.

## Related public repos

This design system is part of a small family of public reference material. The system here gives you the *artifacts*; the others document the *practice*, the *infrastructure*, and complementary *frameworks*. Each has both a source repo and a live site.

- **[share-ai-engineering-patterns](https://github.com/LoFiGamerGuy/share-ai-engineering-patterns)** &middot; [live catalogue →](https://lofigamerguy.github.io/share-ai-engineering-patterns/) — Practitioner's reference for building with AI agents: patterns, infrastructure, tradeoffs. The leaders memo and catalogue front-page for *that* repo were built using *this* design system. CC BY 4.0.
- **[council-of-five](https://github.com/LoFiGamerGuy/council-of-five)** &middot; [live →](https://lofigamerguy.github.io/council-of-five/) — Multi-perspective decision framework. Useful when designing the system *behind* the artifacts this design system templates. CC BY 4.0.
- **[reference-library-methodology](https://github.com/LoFiGamerGuy/reference-library-methodology)** &middot; [live →](https://lofigamerguy.github.io/reference-library-methodology/) — System for building a queryable, AI-readable technical reference library. MIT licensed.
- **[alpha-reader-toolkit](https://github.com/LoFiGamerGuy/alpha-reader-toolkit)** &middot; [live →](https://lofigamerguy.github.io/alpha-reader-toolkit/) — Pipeline for honest alpha-reader feedback on fiction manuscripts using LLM personas. MIT licensed.
- **[terminal-stack](https://github.com/LoFiGamerGuy/terminal-stack)** — Opinionated terminal kit for Git Bash on Windows. 24 themes (including several from this design system's palette), modern Unix tools, fzf widgets.
- **[dotfiles](https://github.com/LoFiGamerGuy/dotfiles)** — Personal dotfiles. Shell config, prompt, tool integrations. Idempotent installer.

More repos in this family will be released over time. The current set will be expanded with explicit cross-links as they ship.

## Author and license

Designed and built by **Ryan Gosnell** ([@LoFiGamerGuy](https://github.com/LoFiGamerGuy)).

Licensed under the [MIT License](./LICENSE) — use freely, attribute when you can, fork without asking.

---

*Set in Cormorant Garamond, Inter & JetBrains Mono. Five-Register Design System · v1.2 · April 2026.*
