# Provenance and attribution

This repository is a **private, personal copy** of a skills collection. It is not an
original work. Almost nothing here was written by me, and this file records where each
part came from.

## Immediate source

Everything under `plugins/alyssas-skills/skills/` was copied on **2026-10-14** from:

- **[damilareoo/damilares-skills](https://github.com/damilareoo/damilares-skills)** —
  curated by [@damilareoo](https://github.com/damilareoo), website at
  [damilares-skills.vercel.app](https://damilares-skills.vercel.app)

**That repository carries no licence file.** It grants no explicit redistribution
rights. Its README invites users to clone the skills into their own
`~/.claude/skills`, and to copy individual `SKILL.md` files into other agents'
context — which is what this repository is for. It is private for that reason.
**Do not make this repository public, and do not redistribute it**, without
permission from @damilareoo and from the upstream authors below.

## Upstream authors

@damilareoo's README credits the following original authors. Where a skill shipped
its own licence file, that file was copied with it and travels with the skill — see
the list at the end.

| Author | Skills |
|---|---|
| [Anthropic](https://github.com/anthropics/skills) | `frontend-design`, `canvas-design`, `algorithmic-art`, `theme-factory`, `brand-guidelines`, `skill-creator`, `mcp-builder`, `internal-comms`, `slack-gif-creator`, `web-artifacts-builder`, `pdf`, `docx`, `pptx`, `xlsx` |
| [Anthony Fu](https://github.com/antfu) | `vue`, `nuxt`, `pinia`, `vite`, `vitepress`, `vitest`, `unocss`, `slidev`, `pnpm`, `antfu` |
| [Jakub Krehel](https://github.com/jakubkrehel/skills) | the `better-*` skills (MIT) |
| [Matt Pocock](https://github.com/mattpocock/skills) | the engineering track — `code-review`, `tdd`, `implement`, `research`, `triage`, `wayfinder`, `wizard`, `to-spec`, `to-tickets`, `domain-modeling`, `grill*`, `writing-*`, `handoff` and others (MIT) |
| [vuejs-ai](https://github.com/vuejs-ai) | `vue-best-practices`, `vue-router-best-practices`, `vue-testing-best-practices` |
| [SerKo](https://github.com/serkodev) | `vueuse-functions` |
| [Vercel](https://github.com/vercel) | `web-design-guidelines`, `turborepo` |
| [VoidZero](https://github.com/voidzero-dev) | `tsdown` |
| [Refero](https://refero.design) | `refero-design` |
| [Josh Puckett](https://github.com/jpuckett) | `interface-craft` |
| [Emil Kowalski](https://emilkowalski.com) | `emil-design-eng` |
| [raphael-salaja](https://github.com/raphaelsalaja) | `12-principles-of-animation` |

Remaining skills are described upstream as original to @damilareoo. Those are the
ones with no licence of any kind attached, and the reason this repository stays
private.

If any attribution here is wrong, the error is mine in copying, not upstream's.

## What was changed in the copy

The copy is otherwise byte-for-byte. Three changes:

1. **44 skills were dropped as broken.** In the source repo their `SKILL.md` is a
   symlink into the author's own home directory
   (`/Users/v/.claude/skills/gstack/...`), committed by the launchd auto-sync his
   README describes. They contain no content and resolve to nothing on any other
   machine. The full list is in [`dropped-skills.txt`](dropped-skills.txt).
2. **`_gstack-command` was dropped.** It is the router for that same gstack suite: it
   dispatches to the 44 skills above and shells out to
   `~/.claude/skills/gstack/bin/` helpers that are not in the repository.
3. **`web/`, `docs/` and `sync.sh` were not copied.** The website is @damilareoo's own
   and vendors commercially licensed fonts (Moderat, Suisse Intl) that are certainly
   not redistributable; `sync.sh` is tied to his machine.

That leaves **138 skills**, each with a real `SKILL.md`.

## Known rough edges inherited from upstream

- Nine skills still reference `~/.claude/skills/gstack/bin/` helpers that are not
  included here: `qa`, `review`, `ship`, `retro`, `connect-chrome`,
  `setup-browser-cookies`, `plan-ceo-review`, `plan-eng-review` and
  `_gstack-command` (dropped). Their content is real and useful, but the preamble
  shell block degrades to no-ops. Left unmodified rather than rewritten.
- Six skills are marked *unfinished upstream* in @damilareoo's README — they ship
  from Matt Pocock's `in-progress/` folder: `setup-ts-deep-modules`,
  `claude-handoff`, `loop-me`, `writing-fragments`, `writing-shape`, `writing-beats`.
- The Matt Pocock engineering track (`triage`, `to-spec`, `to-tickets`, `wayfinder`,
  `domain-modeling`) expects a per-repo tracker layout. Run `setup-matt-pocock-skills`
  once per repository before using them.
- `algorithmic-art/SKILL.md` has CRLF line endings upstream. Left as-is.

## Skills shipping their own licence file

These carry their terms with them; read them before reusing anything:

- `algorithmic-art`
- `brand-guidelines`
- `docx`
- `internal-comms`
- `mcp-builder`
- `pdf`
- `pptx`
- `refero-design`
- `skill-creator`
- `slack-gif-creator`
- `slidev`
- `theme-factory`
- `tsdown`
- `turborepo`
- `vue-best-practices`
- `vue-router-best-practices`
- `vue-testing-best-practices`
- `vueuse-functions`
- `web-artifacts-builder`
- `xlsx`
