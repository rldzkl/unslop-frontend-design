---
name: unslop-frontend-design
description: Visual design for building or redesigning UI, and for polishing UI that reads as generic or AI-generated (unslop).
license: Apache-2.0. Derived from anthropics/skills frontend-design, rewritten with additions; see SOURCES.md. Complete terms in LICENSE.txt
---

# Unslop frontend design

Work as the design lead at a studio known for giving every client an identity no one mistakes for anyone else's. This client has already rejected templated proposals and is paying for a point of view: make opinionated choices about palette, type, and layout that belong to this brief, and take aesthetic risk where the brief justifies it.

The test throughout is **default or choice**. A _default_ is what you would produce for any similar brief; a _choice_ traces to this brief's subject, audience, or job. Generated UI reads as slop because its defaults show. The brief's own words always win, including when they ask for a look that is usually a default. Every axis the brief leaves free gets a choice.

## Steps

Building or redesigning UI runs every step as written. Polishing existing UI keeps its direction: step 2 records the design system it already uses as the plan, step 3 audits the rendered UI as well as that plan, and step 4 changes what the audit flags.

1. **Ground in the subject.** Name the subject, the audience, and the design's primary job. The subject's industry, materials, and vernacular are where distinctive choices come from: a toy for girls aged 8–11 and a dashboard for financial analysts share almost nothing visually. Use the brief's real content throughout. Done when all three are stated by the brief or confirmed by the client. For any the brief leaves out, propose one concrete answer, using what you know of the client's preferences or project as a hint; when you cannot ask, state the proposal as your assumption.
2. **Plan a token system**, drawing on the design principles below. An existing design system is the starting point: extend its tokens and components rather than invent beside them. Done when the plan has:
   - **Color**: 4–6 named hex values.
   - **Type**: the typefaces, their roles, and a type scale.
   - **Layout**: a one-sentence concept, chosen by comparing alternatives as ASCII wireframes, with alignment (left, centred, or justified).
   - **Principles**: what makes this design unlike its neighbours.
3. **Review for defaults.** For each part of the plan, work through a similar prompt and see whether you land in the same place. If you do, it is a default: revise it and say what changed and why. Check the plan, and any existing rendered UI, against the [slop tells](#slop-tells). Done when every axis the brief leaves free is a choice; only then write code.
4. **Build from the tokens.** Before writing or editing interface text, read [COPY.md](COPY.md). Watch CSS specificity: a section class like `.section` and a component class like `.cta` have equal weight, so source order silently decides which wins, most often on padding and margin between sections. Critique as you build, from screenshots when your environment can take them. Done when the code you touched holds no literal color, size, radius, or spacing value outside the token definitions.
5. **Polish.** Run the [polish pass](#polish-pass); the work is done when the pass is. If the project keeps design notes, record the direction you chose and what you tried, so the next pass can try something new.

## Design principles

**Hero.** On a web page, open with the most characteristic thing in the subject's world, in whatever form fits it best: a headline, an image, an animation, a live demo, or an interactive moment. A big number with a small label, supporting stats, and a gradient accent is the default hero; use it only when it truly is the best option. When the subject is a product, show the product: photography, or for software, real UI, a screenshot, or a live component.

**Type carries the personality.** Use one family, or two that are clearly distinct. Pick typefaces for this brief rather than the families you reach for on every project, and set a scale following _The Elements of Typographic Style_, with intentional weights, widths, and spacing. When type is a headline or a visual element, make the treatment itself part of the design. Default to lines under 80 characters; serif text can run slightly longer and takes slightly more line-height than sans.

**Structure earns its place.** Outlines, borders, numbering, eyebrows, dividers, labels, badges, and pills each encode information about the content. Numbered markers (01 / 02 / 03) mark real sequences such as steps or timelines. A badge ("New", "Beta", "Most popular") carries state the viewer acts on. Monospace sets code, commands, and values meant to be copied. Labels are sentence case and appear where content needs naming.

**Hierarchy from size and spacing.** Make the primary feature visibly larger than its peers. Group by proximity: space inside a group is clearly smaller than space between groups, so the grouping reads without dividers, arrows, or extra cards.

**Motion answers people.** Motion that responds to an action (opening, expanding, confirming) is welcome when it shows what changed. Unprompted motion is for drawing attention, sparingly: one orchestrated moment, such as a single page-load sequence or reveal, lands better than scattered effects.

**Restraint.** Spend boldness in one place: one memorable element, everything around it quiet and disciplined, and only decoration that serves the brief. Before you finish, follow Chanel and take one accessory off.

**Quality floor**, met without announcing it: responsive down to mobile, visible keyboard focus, reduced motion respected, visually accessible, and a harmonious palette.

## Slop tells

Generated design currently clusters around these looks. Each suits some brief, but each appears whatever the subject. On an axis the brief leaves free, a match is a default: revise it. Use one of these looks only when the brief asks for it.

1. Warm cream background (near #F4F1EA), high-contrast serif display, and a terracotta or clay accent (near #D97757, Anthropic's own Claude accent, so on a user's brief it reads as a tell).
2. Near-black background with a single acid-green or vermilion accent.
3. Broadsheet layout: hairline rules, zero border-radius, dense newspaper columns.
4. SaaS-card kit: content chopped into identical rounded cards, one radius on everything regardless of hierarchy, the same soft grey shadow (rgba(0,0,0,.1)) under each, and gradient washes as decoration.
5. Template chrome: a tracked-out all-caps eyebrow above every heading; meta strings joined with middle dots ('A · B · C'); 'WORD — fragment' labels with a spaced em dash; tinted near-black (#0B0B0B, #111) standing in for black; monospace for small data labels; '→' appended to link and button text.
6. Headline accents: one word or phrase set apart in italic, bold, or another color.
7. Motion everywhere: a fade-and-slide-up entrance on each section and a hover transition on every card.

## Polish pass

The pass is done when every applicable rule below, every design principle, and every slop tell has been checked (visual rules in the rendered UI at the target viewports, token and component rules in the code), each failure is fixed, and any aesthetic exception is tied to the brief and named in your report. Contrast failures are fixed, never excepted. If you cannot render the UI, check the code and report the visual checks as unchecked.

- **Primary action**: one primary CTA per view, the most prominent element in its region through contrast, weight, or the brief's accent; secondary actions recede (outline, ghost, or text).
- **Concentric radii**: a rounded element uniformly inset in a rounded container uses inner radius = max(0, outer radius − inset), where inset is the parent's border plus padding, so the corners share a centre. Check unequal insets by eye.
- **Icons**: one icon family, one stroke weight, one size per context, vertically centred on the text they accompany.
- **Optical alignment**: align by eye where geometry lies. Nudge play triangles and arrows toward their visual centre, let round and pointed shapes overshoot flat ones slightly, and confirm on a zoomed screenshot.
- **Contrast**: all text at least 4.5:1, or 3:1 when large (at least 24px regular or 18.66px bold); essential icons, control boundaries, and state indicators at least 3:1 against adjacent colors. Muted grey secondary text, button labels, and text over images are the usual misses.
- **Text wrapping**: `text-wrap: balance` on headings and `text-wrap: pretty` on prose; at each target width, fix awkward breaks such as a headline's lone last word by adjusting measure (`max-width` in `ch`) or copy.
- **Numerals**: `font-variant-numeric: tabular-nums` wherever numbers change live or align in columns (prices, tables, timers, counters).
- **Overlays**: modals and sheets are a native `<dialog>` opened with `showModal()`, or the project's existing dialog component, so focus containment, Escape, the backdrop, and the inert page behind come built in; non-modal menus and panels use the `popover` attribute.
- **Viewport height**: full-height regions use `svh` for heroes and page minimums and `dvh` for app shells and bottom-pinned UI (Tailwind `min-h-svh`, `h-dvh`), so nothing hides behind mobile browser chrome. The `mobile-native` skill covers the details if it is installed.
- **Enter to submit**: let a `<form>` submit natively on Enter; a custom keydown handler that acts on Enter returns early while `event.isComposing` is true, so confirming an IME candidate (Chinese, Japanese, Korean) never sends half-typed text.
- **States**: async regions cover their applicable loading, empty, and error states, with skeletons matching the final layout; buttons that trigger async work show a pending state.
- **Feedback**: actions confirm visibly where their effect appears (a button reading "Added", a row appearing). When motion clarifies the change, build it with the `animate` skill from emilkowalski/skills if it is installed.
