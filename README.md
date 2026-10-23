# design-magic

35 skills for [Claude Code](https://docs.claude.com/en/docs/claude-code), weighted
heavily toward design: visual direction, interface craft, typography and color,
accessibility, motion, and copy. The rest are working practices — test-driven
development, bug diagnosis, module design, merge conflicts — that apply to any
codebase.

They are kept here as a private plugin so the same set is available on any machine,
and so changes are versioned rather than copied around.

## Install

### Copy them into your skills directory

```bash
git clone --depth 1 https://github.com/alyssakjar/design-magic.git /tmp/design-magic-install && rsync -a --exclude='.git' /tmp/design-magic-install/plugins/design-magic/skills/ ~/.claude/skills/ && rm -rf /tmp/design-magic-install
```

Skills load at session start, so open a new session afterwards. They arrive
un-namespaced — `/frontend-design`, `/better-typography` — and are available in every
project. Add `--delete` to the `rsync` when updating to mirror removals too, and check
for name collisions first if `~/.claude/skills` is not empty.

### Or install as a plugin

The repository root is also a plugin marketplace, which namespaces the skills as
`/design-magic:<name>` and lets you pull updates with one command. This route needs
the `claude` CLI on your PATH; the desktop app bundles its own copy and does not
install one.

```bash
claude plugin marketplace add alyssakjar/design-magic
```

```bash
claude plugin install design-magic@design-magic
```

Because the repository is private, the machine needs git access to it — an
authenticated `gh` or an SSH key on the account. Later updates come from
`claude plugin marketplace update design-magic`.

## The skills

Each skill names its author in its own `SKILL.md` frontmatter.

### Design direction and interface

Skills that decide what an interface should look like and hold it to that decision.

| Skill | What it does |
|---|---|
| `frontend-design` | Builds production-grade frontend interfaces — components, pages, landing pages, dashboards, posters — around a committed visual direction instead of default AI aesthetics. The one to reach for when building or restyling any web UI from scratch. |
| `baseline-ui` | An opinionated set of UI constraints that catch generic, obviously-generated interfaces. Invoke it bare to apply the constraints to everything in the current conversation, or against a file to get each violation quoted with a one-line reason it matters and a fix. |
| `better-ui` | Design-engineering detail work: hover states, box shadows, borders and border radius, optical alignment, image outlines, icon choice and stroke weight, enter and exit animations, stagger, and knowing when to hold motion back. The skill for "it feels off" and for final polish. |
| `better-interface` | A cross-discipline review that coordinates the six other `better-*` skills across a whole screen, flow or feature, in either a quick or a full mode. User-invoked, for a holistic audit rather than one detail at a time. |
| `better-layout` | Layout structure: grouping and alignment, negative space, visual hierarchy, reading order, progressive disclosure, breakpoints and container queries, safe areas and full-bleed edges, and right-to-left layout through logical properties. Covers what should collapse at small sizes. |
| `design-lab` | Runs a design interview, generates five distinct UI variations in a throwaway lab, collects your feedback on each, and turns the chosen direction into an implementation plan. For exploring options before committing to one. |
| `design-system-enforcer` | Keeps one visual language running through every section of a landing page or marketing site, so architectural lines, system shapes, background patterns and illustrations carry past the hero instead of petering out. Designed to run both before writing a new section and after finishing it. |
| `interface-design` | Interface design for dashboards, admin panels, apps and interactive tools — deliberately not for marketing pages, landing pages or campaigns. |
| `interface-craft` | A React toolkit in three parts: Storyboard Animation, a human-readable animation DSL with stage-driven sequencing; DialKit, live control panels for tuning animation values as they run; and Design Critique, a systematic UI review following Josh Puckett's own methodology. |
| `emil-design-eng` | Emil Kowalski's philosophy on UI polish, component design, animation decisions and the invisible details that make software feel considered rather than assembled. |
| `ui-ux-pro-max` | A broad UI/UX reference carrying 50 styles, 21 palettes, 50 font pairings and 20 chart types, with patterns for nine stacks including React, Next.js, Tailwind and shadcn/ui. Covers planning, building and reviewing a screen, and can query the shadcn/ui MCP for components and examples. |

### Typography and color

The two token layers that most decide whether a site reads as designed.

| Skill | What it does |
|---|---|
| `better-typography` | Web typography end to end: choosing and pairing typefaces, woff2 and variable fonts, OpenType feature settings, type scales, heading hierarchy, line height, letter spacing and measure, tabular numbers, text wrapping and line clamping, underlines, selection and placeholder styling, text contrast, iOS input zoom, and smart punctuation. |
| `better-colors` | OKLCH color for the web: converting from hex, rgb or hsl, generating palettes, checking contrast ratios, handling gamut boundaries and Display P3, theming with Tailwind v4 semantic tokens, and using color to carry meaning across light, dark and increased-contrast appearances. |

### Accessibility

One engineering reference, one quick checklist, one full audit, and one standards review.

| Skill | What it does |
|---|---|
| `better-accessibility` | Accessibility engineering for real components: focus rings and `focus-visible`, focus traps, tab order and tabindex, ARIA and live regions, semantic HTML, form errors and disabled buttons, alt text, hit areas and touch targets, skip links, autoplay and `prefers-reduced-motion`. |
| `fixing-accessibility` | A rules checklist to apply to UI work as it happens, or to run against a single file to get accessibility violations quoted line by line, each with why it matters and how to fix it. |
| `wcag-audit-patterns` | Full WCAG 2.2 audits: automated testing, manual verification and remediation guidance, plus the accessible design patterns to implement against. |
| `web-design-guidelines` | Reviews UI code against Vercel's Web Interface Guidelines. This is the skill behind "review my UI", "audit my design" or "check my site against best practices". |

### Motion

Judging, naming, building and fixing movement.

| Skill | What it does |
|---|---|
| `12-principles-of-animation` | Audits animation code against Disney's twelve principles adapted for the web — squash and stretch, anticipation, follow-through, timing — and reports what it finds as `file:line` references. |
| `animation-vocabulary` | A reverse-lookup glossary: describe an effect in plain words and get its actual name, so "the bouncy thing when a popover opens" resolves to pop in and "the iOS rubber-band scroll" to rubber-banding. For naming a motion effect, not for designing or building one. |
| `interaction-design` | Designs and implements microinteractions, motion, transitions, loading states and the feedback patterns that tell a user something happened. |
| `review-animations` | Reviews animation and motion code against a high craft bar derived from Emil Kowalski's writing on the subject. |
| `fixing-motion-performance` | A constraints checklist for janky animation. Apply it to animation work in progress, or run it against a file to get each performance problem quoted with its cause and fix. |

### Writing

Interface copy, marketing copy, and documents written to be read by agents.

| Skill | What it does |
|---|---|
| `better-writing` | UX writing and interface copy: voice and tone, button and link labels, form error messages, placeholder text, settings labels, onboarding flows, notifications and empty states, plus capitalization conventions like title versus sentence case. |
| `copywriting-skill` | Marketing and product copy — headlines, hero text, taglines, about sections and any written content for a website, app, poster or brand. |
| `writing-for-agents` | How to write documents an agent will actually follow, whether a skill, an `AGENTS.md` or a `CLAUDE.md`. Covers context pointers, why a skill's description wording rather than its body decides when it triggers, and how hard to prune text that loads on every turn. |

### Engineering

Agent-agnostic working practices, plus two repo guardrails.

| Skill | What it does |
|---|---|
| `tdd` | The red-green-refactor loop, with the part that makes tests worth keeping: verifying behavior through public interfaces rather than internals, agreeing the seams under test before writing anything, and the anti-patterns to avoid. Defers to `codebase-design` for interface vocabulary. |
| `codebase-design` | Shared vocabulary for designing deep modules — module, interface, depth, seam, adapter, leverage, locality. Use it to design or improve a module's interface, decide where a seam belongs, or make code more testable. A reference to consult, not a workflow to run. |
| `diagnosing-bugs` | A diagnosis discipline for hard bugs and performance regressions, built around earning a tight pass/fail signal first and only then spending it on bisection, hypothesis testing and instrumentation. Redacts secrets from anything it surfaces. |
| `research` | Investigates a question against high-trust primary sources and captures the findings as a Markdown file in the repo. Suited to delegating reading legwork to a background agent. |
| `resolving-merge-conflicts` | Works an in-progress merge or rebase hunk by hunk: recover each side's original intent from commit messages, PRs and issues, preserve both where they are compatible, then run the project's own checks and finish the merge. It always resolves and never aborts. |
| `handoff` | Writes a handoff document so a fresh agent can pick the work up, saved outside the workspace, pointing at existing specs, plans and commits rather than restating them, with secrets redacted and a note on which skills the next agent should call. |
| `grilling` | Stress-tests a plan or decision by interviewing you until nothing is left silently assumed. It maps the work as a design tree and asks it in rounds — every question whose prerequisites are already settled, numbered, each with its recommended answer — then recomputes what is answerable from your replies. Facts it looks up itself; decisions it puts to you. |
| `grill-me` | The user-invoked entry point to `grilling`, for when you want to be grilled on demand rather than waiting for the model to decide a plan needs it. |
| `fixing-metadata` | A constraints checklist for page metadata. Apply it while working on metadata, or run it against a file to get each gap or error quoted with why it matters. |
| `git-guardrails-claude-code` | Installs Claude Code hooks that block destructive git commands — `push`, `reset --hard`, `clean`, `branch -D` and friends — before they run, rather than relying on being asked first. |

## Adding a skill

One directory per skill under `plugins/design-magic/skills/<name>/`, holding a
`SKILL.md` with `name`, `author` and `description` in its frontmatter. The description
is what decides when the skill triggers, so it is worth more care than the body —
`/writing-for-agents` covers how to word it. Add a row to the table above, and push.

```
.claude-plugin/marketplace.json          the marketplace (repo root)
plugins/design-magic/
├── .claude-plugin/plugin.json           the plugin manifest
└── skills/<skill-name>/SKILL.md         the skills
```

The marketplace entry name, the plugin manifest name and the plugin directory name
must all stay `design-magic`, or installs fail confusingly.

## License

These skills were written by other people — each one's `author` field names who. Many
carry a license of their own, declared in the skill itself; some carry none at all.
Check the individual skill before reusing it anywhere, because the terms differ from
skill to skill.

This repository is private and should stay that way: these licenses are not mine to
re-grant. See [NOTICE.md](https://github.com/alyssakjar/design-magic/blob/main/NOTICE.md).
