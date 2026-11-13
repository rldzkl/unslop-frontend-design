# Sources

This skill is rewritten from its sources, not merged with them, so upstream changes are ported by meaning. To update: for each source, read what changed since its pin, carry each new or changed rule into the section that owns that topic (one rule, one place), then advance the pin.

| Source | Pin | Contributed |
| --- | --- | --- |
| [anthropics/skills `skills/frontend-design`](https://github.com/anthropics/skills/tree/41bbe19d1a1a7eaab5e7bb9050a417e5c6cffc8f/skills/frontend-design) (Apache-2.0) | `41bbe19d1a1a7eaab5e7bb9050a417e5c6cffc8f` | Persona, subject grounding, design principles, token plan and default review, slop tells 1–7, restraint, copy guidance |
| [Charles Liu, "unslop AI design" tips](https://www.tiktok.com/@charles.unemployed/video/7705468598260665618) | video `7705468598260665618` | Product over illustration, badge and monospace tests, hierarchy by size and proximity, design-system tokens, polish pass |
| [GoogleChrome/modern-web-guidance-src `guides/`](https://github.com/GoogleChrome/modern-web-guidance-src/tree/3bb177a6de62b7fd8cd0432c33756e6f3c9ece9d/guides) (Apache-2.0) | `3bb177a6de62b7fd8cd0432c33756e6f3c9ece9d` | Polish-pass overlay, viewport-height, and Enter-to-submit rules (`ui-components/dialog`, `css/responsive-design`, `forms/ime-safe-enter-submit`) |

Check Anthropic's changes since the pin:

```sh
git -C <anthropics-skills-clone> fetch origin
git -C <anthropics-skills-clone> log --oneline 41bbe19d1a1a7eaab5e7bb9050a417e5c6cffc8f..origin/main -- skills/frontend-design
git -C <anthropics-skills-clone> diff 41bbe19d1a1a7eaab5e7bb9050a417e5c6cffc8f origin/main -- skills/frontend-design
```

Modifications from the Apache-2.0 source: renamed, restructured into steps with completion criteria, reworded throughout, copy guidance moved to `COPY.md`, and new rules added from the sources above.
