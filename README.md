# alyssas-skills

34 agent skills for [Claude Code](https://docs.claude.com/en/docs/claude-code), kept as
a private plugin so they can be installed on any machine I work from. The set is
deliberately small: design, interface craft, accessibility, motion and a few
agent-agnostic engineering skills.

**This is a copy, not original work.** It was assembled from
[damilareoo/damilares-skills](https://github.com/damilareoo/damilares-skills), which in
turn curates skills from Anthropic, Matt Pocock, Jakub Krehel, Vercel and others. Read
[NOTICE.md](NOTICE.md) before doing anything with it — the source repo has **no
licence**, which is why this one is private and must stay that way.

## Install

### As a plugin (recommended)

The repository root is a plugin marketplace. Register it, then install the plugin:

```bash
claude plugin marketplace add alyssakjar/alyssas-skills
```

```bash
claude plugin install alyssas-skills@alyssas-skills
```

Skills then load namespaced, as `/alyssas-skills:<name>`. Because the repository is
private, the machine doing this needs git access to it — an authenticated `gh` or an
SSH key on the account.

To pick up later changes:

```bash
claude plugin marketplace update alyssas-skills
```

### Or copy the skills straight in

```bash
git clone --depth 1 https://github.com/alyssakjar/alyssas-skills.git /tmp/alyssas-skills-install && rsync -a --exclude='.git' /tmp/alyssas-skills-install/plugins/alyssas-skills/skills/ ~/.claude/skills/ && rm -rf /tmp/alyssas-skills-install
```

Add `--delete` to the `rsync` when updating, to clear out skills that have since been
removed. This drops all 34 into `~/.claude/skills/` alongside anything already there,
so check for name collisions first if that directory is not empty.

### Other agents

Each `SKILL.md` is self-contained Markdown. Paste one into Codex, Cursor, Copilot or
anything else that reads context.

## Layout

```
.claude-plugin/marketplace.json          the marketplace (repo root)
plugins/alyssas-skills/
├── .claude-plugin/plugin.json           the plugin manifest
└── skills/<skill-name>/SKILL.md         the skills
```

The marketplace entry name, the plugin manifest name and the directory name are all
`alyssas-skills`, and installs fail confusingly if they ever drift apart.

Adding a skill means adding a `skills/<name>/SKILL.md` and pushing. Anything written by
me rather than copied should say so in its frontmatter, so the provenance in NOTICE.md
stays true.

## Why only these

The source repo shipped 183 directories. 45 of them were unusable on arrival, and of the
138 that worked, 104 were pruned as irrelevant to this stack — about a third of those
were Cursor's own bundled Codex skills, swept up by the author's auto-sync. See
[pruned-skills.txt](pruned-skills.txt) for every removal and its reason, and
[dropped-skills.txt](dropped-skills.txt) for the broken ones.

## The skills

### Design direction and interface

| Skill | What it does |
|---|---|
| `frontend-design` | Create distinctive, production-grade frontend interfaces with high design quality. Use this skill… |
| `baseline-ui` | Enforces an opinionated UI baseline to prevent AI-generated interface slop. |
| `better-ui` | Design engineering principles for making interfaces feel polished. Use when building UI components,… |
| `better-interface` | User-invoked, cross-discipline interface review that coordinates better-accessibility,… |
| `better-layout` | Layout structure for web interfaces, from grouping and alignment to reading order, progressive… |
| `design-lab` | Conduct design interviews, generate five distinct UI variations in a temporary design lab, collect… |
| `design-system-enforcer` | Enforces visual system consistency across every section of a landing page or marketing site. Use… |
| `interface-design` | This skill is for interface design — dashboards, admin panels, apps, tools, and interactive… |
| `interface-craft` | Interface Craft by Josh Puckett — a toolkit for building polished, animated interfaces in React.… |
| `emil-design-eng` | This skill encodes Emil Kowalski's philosophy on UI polish, component design, animation decisions,… |
| `ui-ux-pro-max` | UI/UX design intelligence. 50 styles, 21 palettes, 50 font pairings, 20 charts, 9 stacks (React,… |

### Typography and colour

| Skill | What it does |
|---|---|
| `better-typography` | Web typography from choosing fonts to spacing, wrapping and accessibility. Use when picking or… |
| `better-colors` | OKLCH color space and color usage for web projects. Convert hex/rgb/hsl to oklch, generate… |

### Accessibility

| Skill | What it does |
|---|---|
| `better-accessibility` | Accessibility engineering for product interfaces, from focus states and keyboard support to ARIA,… |
| `fixing-accessibility` | Fix accessibility issues. |
| `wcag-audit-patterns` | Conduct WCAG 2.2 accessibility audits with automated testing, manual verification, and remediation… |
| `web-design-guidelines` | Review UI code for Web Interface Guidelines compliance. Use when asked to "review my UI", "check… |

### Motion

| Skill | What it does |
|---|---|
| `12-principles-of-animation` | Audit animation code against Disney's 12 principles adapted for web. Use when reviewing motion,… |
| `animation-vocabulary` | Reverse-lookup glossary that turns a vague description of a web animation or motion effect into its… |
| `interaction-design` | Design and implement microinteractions, motion design, transitions, and user feedback patterns. Use… |
| `review-animations` | Reviews animation and motion code against a high craft bar derived from Emil Kowalski's design… |
| `fixing-motion-performance` | Fix animation performance issues. |

### Writing and copy

| Skill | What it does |
|---|---|
| `better-writing` | UX writing and interface copy, from voice and button labels to error messages and empty states. Use… |
| `copywriting-skill` | Use when writing any copy for a website, landing page, app, poster, brand, or marketing material.… |
| `writing-for-agents` | Writing documents for agents. Use when creating or editing skills, or modifying AGENTS.md or… |

### Engineering

| Skill | What it does |
|---|---|
| `codebase-design` | Shared vocabulary for designing deep modules. Use when the user wants to design or improve a… |
| `diagnosing-bugs` | Diagnosis loop for hard bugs and performance regressions. Use when the user says "diagnose"/"debug… |
| `grill-me` | A relentless interview to sharpen a plan or design. |
| `handoff` | Compact the current conversation into a handoff document for another agent to pick up. |
| `research` | Investigate a question against high-trust primary sources and capture the findings as a Markdown… |
| `resolving-merge-conflicts` | Use when you need to resolve an in-progress git merge/rebase conflict. |
| `tdd` | Test-driven development. Use when the user wants to build features or fix bugs test-first, mentions… |
| `git-guardrails-claude-code` | Set up Claude Code hooks to block dangerous git commands (push, reset --hard, clean, branch -D,… |
| `fixing-metadata` | Ship correct, complete metadata. |
