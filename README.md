# unslop-frontend-design

An Agent Skills (`SKILL.md`) skill for building, redesigning, and polishing UI that reads as generic or AI-generated. Works with any agent that loads skills, regardless of model.

```sh
npx skills add rldzkl/unslop-frontend-design
```

Or paste this into your agent's conversation:

```text
Install the unslop-frontend-design skill from https://github.com/rldzkl/unslop-frontend-design/tree/main/skills/unslop-frontend-design using your supported skill installation method. Include the whole folder, then tell me where you installed it and how to use it.
```

I wrote it for my own use. Each time I spot another pattern that marks a UI as AI-made, I add a rule for it here. If that sounds useful, try it. If you've found patterns it misses, contributions are welcome.

## What it does

For new UI or a redesign, the agent names the subject, audience and job, plans a small set of design tokens, checks that plan against common AI defaults, builds from the tokens, and runs a polish pass. For existing UI, it keeps the current direction and fixes what the pass flags.

## UI fixes

The rules in [SKILL.md](skills/unslop-frontend-design/SKILL.md) and [COPY.md](skills/unslop-frontend-design/COPY.md) cover:

- Text contrast of at least 4.5:1, or 3:1 for large text; essential icons, control boundaries, and state indicators at least 3:1.
- Concentric nested corners: inner radius = max(0, outer radius - border - padding) for uniform insets.
- One prominent primary action per view, with secondary actions that recede.
- Consistent icon families, stroke weights, and sizes; optical alignment for icons and shapes.
- Balanced headings, readable prose wrapping, and fixes for awkward line breaks.
- Tabular numerals for changing numbers and aligned columns.
- Loading, empty, and error states; skeletons that match the final layout and pending buttons for async work.
- Visible confirmation after actions, consistent action names, and errors that explain how to recover.
- Mobile layouts, visible keyboard focus, and respect for reduced motion.

## Other ways to install

In Codex, paste this into the conversation:

```text
$skill-installer install https://github.com/rldzkl/unslop-frontend-design/tree/main/skills/unslop-frontend-design
```

If the skill does not appear, restart Codex.

In Claude Code, add the marketplace, then install the plugin:

```text
/plugin marketplace add rldzkl/unslop-frontend-design
/plugin install unslop-frontend-design@unslop-frontend-design
```

For manual installation, copy the entire `skills/unslop-frontend-design` folder into your agent's skills directory.

Then ask for UI work as usual, or try: "Use unslop-frontend-design to polish this page."

## Contributing

Open an issue or pull request with the pattern, an example of where it shows up, and the rule you would add. Put each rule in the section that owns its topic, and record any new source in `skills/unslop-frontend-design/SOURCES.md`.

## Credits and license

Rewritten from Anthropic's [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) skill, with additions based on Charles Liu's [video on unslopping AI design](https://www.tiktok.com/@charles.unemployed/video/7705468598260665618). Licensed under Apache-2.0; see [LICENSE](LICENSE).
