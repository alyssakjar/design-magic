# Provenance and attribution

This repository is a **private, personal copy** of a skills collection. It is not an
original work. Most of it was written by other people, and this file records who.

## Immediate source

The 34 skills under `plugins/alyssas-skills/skills/` were copied on **2026-10-14** from:

- **[damilareoo/damilares-skills](https://github.com/damilareoo/damilares-skills)** —
  curated by [@damilareoo](https://github.com/damilareoo), website at
  [damilares-skills.vercel.app](https://damilares-skills.vercel.app)

**That repository carries no licence file.** It grants no explicit redistribution
rights. Its README invites users to clone the skills into their own `~/.claude/skills`,
and to copy individual `SKILL.md` files into other agents' context — which is what this
repository is for. It is private for that reason. **Do not make this repository public,
and do not redistribute it**, without permission from @damilareoo and from the upstream
authors below.

## Upstream authors

Of the 34 skills kept here, 20 are the work
of these authors, per @damilareoo's own credits:

| Author | Skills |
|---|---|
| [Anthropic](https://github.com/anthropics/skills) | `frontend-design` |
| [Jakub Krehel](https://github.com/jakubkrehel/skills) (MIT) | `better-accessibility`, `better-colors`, `better-interface`, `better-layout`, `better-typography`, `better-ui`, `better-writing` |
| [Matt Pocock](https://github.com/mattpocock/skills) (MIT) | `codebase-design`, `diagnosing-bugs`, `grill-me`, `handoff`, `research`, `resolving-merge-conflicts`, `tdd`, `writing-for-agents` |
| [Vercel](https://github.com/vercel) | `web-design-guidelines` |
| [Josh Puckett](https://github.com/jpuckett) | `interface-craft` |
| [Emil Kowalski](https://emilkowalski.com) | `emil-design-eng` |
| [raphael-salaja](https://github.com/raphaelsalaja) (MIT) | `12-principles-of-animation` |

The remaining 14 are described upstream as original to
@damilareoo:

`animation-vocabulary`, `baseline-ui`, `copywriting-skill`, `design-lab`, `design-system-enforcer`, `fixing-accessibility`, `fixing-metadata`, `fixing-motion-performance`, `git-guardrails-claude-code`, `interaction-design`, `interface-design`, `review-animations`, `ui-ux-pro-max`, `wcag-audit-patterns`

Those are the ones with no licence of any kind attached, and the reason this repository
stays private. `review-animations` is his, but its craft bar is derived from Emil
Kowalski's writing.

If any attribution here is wrong, the error is mine in copying, not upstream's.

## Licence gaps to be aware of

- **No skill here ships its own licence file any more.** Twenty of the original 138 did,
  but all twenty were pruned. What remains is covered only by whatever terms its author
  publishes in their own repository.
- **`frontend-design` claims a licence file it does not have.** Its frontmatter reads
  `license: Complete terms in LICENSE.txt`, but no such file exists — upstream dropped
  it while keeping the pointer. It is Anthropic's skill; read the terms at
  [anthropics/skills](https://github.com/anthropics/skills).
- `12-principles-of-animation` declares `license: MIT` in its frontmatter.

## What was changed in the copy

Skill contents are byte-for-byte as upstream. Nothing was rewritten. What changed is
which skills are present:

1. **45 were dropped as broken.** In the source repo their `SKILL.md` is a symlink into
   the author's own home directory (`/Users/v/.claude/skills/gstack/...`), committed by
   the launchd auto-sync his README describes. They contain no content and resolve to
   nothing on any other machine. 44 are listed in
   [`dropped-skills.txt`](dropped-skills.txt); the 45th, `_gstack-command`, was the
   router for them and also shelled out to `gstack` binaries absent from the repo.
2. **104 were pruned as irrelevant to this stack** — see
   [`pruned-skills.txt`](pruned-skills.txt), which gives a reason for every one. The
   largest group, 32 of them, were Cursor's own bundled Codex skills and Codex-migrated
   duplicates of skills already present in plain form.
3. **`web/`, `docs/` and `sync.sh` were not copied.** The website is @damilareoo's own and
   vendors commercially licensed fonts (Moderat, Suisse Intl) that are certainly not
   redistributable; `sync.sh` is tied to his machine.

## Inherited rough edges

Both of the big ones are gone with the prune — no remaining skill depends on the absent
`gstack` binaries, and none of the six skills marked *unfinished upstream* survived. Of
what is left:

- `ask-matt` and `setup-matt-pocock-skills` were pruned, so the eight Matt Pocock skills
  kept here are the ones that stand alone. None of them needs the per-repo tracker setup
  his full track expects.
- `grilling` and `grill-with-docs` were pruned as overlapping; `grill-me` is the one kept.
- Eight of the kept skills are competing takes on visual direction. That is deliberate —
  they are different voices — but expect overlap when more than one triggers.
