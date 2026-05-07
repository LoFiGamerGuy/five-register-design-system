# Contributing

This is an opinionated design system. The opinions are deliberate; not every contribution will fit. That's by design — restraint is the load-bearing aesthetic. But there's still meaningful room to contribute.

## What's most welcome

In rough priority order:

1. **Bug fixes.** Broken markup, CSS that doesn't render correctly, accessibility regressions, missing focus rings. These are always welcome.
2. **Accessibility improvements.** WCAG compliance, screen-reader behavior, reduced-motion support, color contrast — anything that makes the templates work for more people.
3. **Print fixes.** Soul-register templates should print cleanly. If a template breaks across pages or loses a margin in print, that's a fix worth making.
4. **New templates within the existing five registers.** A new SOUL-register letter variant, a new GENKAN catalogue layout, a new COCKPIT incident-report shape — anything that fits an existing register and earns its existence.
5. **Additional language / writing-direction support.** RTL support, vertical-writing-mode templates, CJK-specific typography refinements.
6. **Documentation improvements.** Clearer examples, better quick-start instructions, illustrated walk-throughs.
7. **Translations of the README.** If you'd like to translate to another language, open an issue first to discuss structure.

## What will likely be declined

- **New registers.** Five is the deliberate count. A sixth dilutes the system. The case for adding one would have to be very strong (a use case that none of the existing five can serve well).
- **New aesthetic directions** that pull the system away from its Japanese-craft roots. Cyberpunk, brutalist, neumorphic, glassmorphic — none of these fit. Fork the repo and build your own if that's the direction you want.
- **New default fonts.** The Cormorant Garamond / Inter / JetBrains Mono / Cardo / Source Serif 4 picks are deliberate. Defensible *swaps* through tokens.css are documented; new defaults are not.
- **Decorative iconography.** SVG icon packs, emoji additions, line-art glyphs. The "no icons" rule is load-bearing. CJK characters in hairline boxes, mono numerals, and `.gk-pip` status squares are the entire iconographic vocabulary.
- **Additions to the token palette beyond what's needed.** New colors should solve a specific accessibility or semantic gap, not "I wanted more colors to choose from."
- **JavaScript dependencies.** `deck-stage.js` is pure vanilla custom-element code with no dependencies. Additions should follow the same rule.

## How to contribute

### For small changes (fixes, typos, small accessibility improvements):
1. Open a PR with the fix
2. In the PR description, briefly say what changed and why
3. That's it

### For new templates:
1. Open an issue first describing what you want to add and which register it belongs to
2. We'll discuss whether it fits and how it should be scoped
3. Then open a PR with the template

### For changes to `tokens.css` or any of the register stylesheets:
These are the load-bearing files. Changes here ripple across every template. Open an issue first; we'll discuss before coding.

## Style conventions

- **HTML** — semantic, accessible, no inline styles. Use the existing class system; if a class doesn't exist, propose adding it to the relevant register's stylesheet rather than inlining.
- **CSS** — BEM-ish naming, register-prefixed classes (`.gk-*` for genkan, `.hi-*` for hiroma, `.ve-*` for vesper, `.op-*` for ophelia). Use CSS custom properties from `tokens.css` rather than literal values.
- **JavaScript** — vanilla only. No frameworks. No build step. If a feature requires significant JS, reconsider whether it belongs.
- **No bundlers, no build step.** The repo should work by opening any HTML file directly in a browser. Keep it that way.

## Testing your changes

Open the affected templates in:
1. Latest Chrome / Firefox / Safari
2. A mobile-width viewport (responsive design check)
3. Print preview, if you've changed a soul-register or genkan-light template
4. With `prefers-reduced-motion: reduce` set, if you've changed any motion behavior

Accessibility:
- Run an automated checker (axe DevTools or Lighthouse) on the affected templates
- Test keyboard navigation (Tab through every interactive element; check focus rings are visible)
- Test with a screen reader if you've changed semantic structure

## Code of conduct

- Disagree with ideas, not people
- Ask before assuming bad faith
- Thank people who correct your mistakes

## Recognition

Contributors are acknowledged in the README of any release that includes their work. War story contributors (designers who share how they used the system in production) can choose to be named or anonymous.

## Maintainer

Ryan Gosnell — [GitHub @LoFiGamerGuy](https://github.com/LoFiGamerGuy)

---

*This file is MIT licensed, same as the rest of the repo.*
