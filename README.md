# unslop-frontend-design

An agent skill for Claude Code and Codex that steers UI work away from the look of AI-generated design.

I wrote it for my own use. Each time I spot another pattern that marks a UI as AI-made, I add a rule for it here. If that sounds useful, try it. If you've found patterns it misses, contributions are welcome.

## What it does

For new UI or a redesign, the agent names the subject, audience and job, plans a small set of design tokens, checks that plan against a list of common AI defaults, builds from the tokens, and then runs a polish checklist. For existing UI, it keeps the current direction and fixes what the checklist flags.

The checklist covers contrast ratios, nested corner radii, icon consistency, optical alignment, text wrapping, tabular numerals, loading and error states, and feedback after actions.

## Install

Copy `skills/unslop-frontend-design` into your skills folder:

- Claude Code: `~/.claude/skills/unslop-frontend-design`
- Codex: `~/.agents/skills/unslop-frontend-design`

Then ask for UI work as usual, or ask the agent to polish or unslop an existing page.

## Contributing

Open an issue or pull request with the pattern, an example of where it shows up, and the rule you would add. Put each rule in the section that owns its topic, and record any new source in `skills/unslop-frontend-design/SOURCES.md`.

## Credits and license

Rewritten from Anthropic's [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) skill, with additions based on Charles Liu's [video on unslopping AI design](https://www.tiktok.com/@charles.unemployed/video/7705468598260665618). Licensed under Apache-2.0; see [LICENSE](LICENSE).
