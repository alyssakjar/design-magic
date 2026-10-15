# alyssas-skills

138 agent skills for [Claude Code](https://docs.claude.com/en/docs/claude-code), kept
as a private plugin so they can be installed on any machine I work from.

**This is a copy, not original work.** It was assembled from
[damilareoo/damilares-skills](https://github.com/damilareoo/damilares-skills), which in
turn curates skills from Anthropic, Anthony Fu, Matt Pocock, Jakub Krehel, Vercel and
others. Read [NOTICE.md](NOTICE.md) before doing anything with it — the source repo has
**no licence**, which is why this one is private and must stay that way.

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
removed. Note that this drops all 138 into `~/.claude/skills/` alongside anything
already there, so check for name collisions first if that directory is not empty.

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
me rather than copied should say so in its frontmatter, so the provenance in
NOTICE.md stays true.

## Caveats

- Nine skills reference `gstack` helper binaries that are not included; their preambles
  degrade to no-ops. Six more are unfinished upstream. The engineering track needs
  `setup-matt-pocock-skills` run once per repo. See
  [NOTICE.md](NOTICE.md#known-rough-edges-inherited-from-upstream).
- 44 entries in the source repo were broken symlinks into the author's home directory
  and were dropped. See [dropped-skills.txt](dropped-skills.txt).

## The skills

| Skill | Description |
|---|---|
| `12-principles-of-animation` | Audit animation code against Disney's 12 principles adapted for web. Use when reviewing motion, implementing… |
| `algorithmic-art` | Creating algorithmic art using p5.js with seeded randomness and interactive parameter exploration. Use this when users… |
| `animation-vocabulary` | Reverse-lookup glossary that turns a vague description of a web animation or motion effect into its exact term ("the… |
| `antfu` | Anthony Fu's opinionated tooling and conventions for JavaScript/TypeScript projects. Use when setting up new projects… |
| `ask-matt` | Ask which skill or flow fits your situation. A router over the skills in this repo. |
| `automate` | Use this skill to create Codex Automations. |
| `autopilot` | >- |
| `baseline-ui` | Enforces an opinionated UI baseline to prevent AI-generated interface slop. |
| `better-accessibility` | Accessibility engineering for product interfaces, from focus states and keyboard support to ARIA, forms, and screen… |
| `better-colors` | OKLCH color space and color usage for web projects. Convert hex/rgb/hsl to oklch, generate palettes, check contrast… |
| `better-interface` | >- |
| `better-layout` | Layout structure for web interfaces, from grouping and alignment to reading order, progressive disclosure, and adaptive… |
| `better-typography` | Web typography from choosing fonts to spacing, wrapping and accessibility. Use when picking or pairing typefaces… |
| `better-ui` | Design engineering principles for making interfaces feel polished. Use when building UI components, reviewing frontend… |
| `better-writing` | >- |
| `brand-guidelines` | Applies Anthropic's official brand colors and typography to any sort of artifact that may benefit from having… |
| `branding-system-skill` | Use when designing or generating any brand identity, website, poster, UI, motion piece, or visual asset for any… |
| `canvas-design` | Create beautiful visual art in .png and .pdf documents using design philosophy. You should use this skill when the user… |
| `canvas` | >- |
| `claude-handoff` | Hand the current conversation off to a fresh background agent that picks up the work immediately. |
| `code-review` | Review the changes since a fixed point (commit, branch, tag, or merge-base) along two axes: Standards (does the code… |
| `codebase-design` | Shared vocabulary for designing deep modules. Use when the user wants to design or improve a module's interface, find… |
| `connect-chrome` | Launch GStack Browser — AI-controlled Chromium with the sidebar extension baked in. |
| `consolidate-memory` | Reflective pass over your memory files — merge duplicates, fix stale facts, prune the index. |
| `copywriting-skill` | Use when writing any copy for a website, landing page, app, poster, brand, or marketing material. Activates on requests… |
| `create-hook` | >- |
| `create-rule` | >- |
| `create-skill` | >- |
| `create-subagent` | >- |
| `design-lab` | Conduct design interviews, generate five distinct UI variations in a temporary design lab, collect feedback, and… |
| `design-system-enforcer` | \| |
| `diagnosing-bugs` | Diagnosis loop for hard bugs and performance regressions. Use when the user says "diagnose"/"debug this", or reports… |
| `doc-coauthoring` | Guide users through a structured workflow for co-authoring documentation. Use when user wants to write documentation… |
| `docx` | Use this skill whenever the user wants to create, read, edit, or manipulate Word documents (.docx files). Triggers… |
| `domain-modeling` | Build and sharpen a project's domain model. Use when discussing codebase terminology, writing or editing a CONTEXT.md… |
| `emil-design-eng` | This skill encodes Emil Kowalski's philosophy on UI polish, component design, animation decisions, and the invisible… |
| `figma-to-code-skill` | Use when translating a Figma design, component, frame, or design system into code. Activates when Figma MCP is in use… |
| `fixing-accessibility` | Fix accessibility issues. |
| `fixing-metadata` | Ship correct, complete metadata. |
| `fixing-motion-performance` | Fix animation performance issues. |
| `frontend-design` | Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to… |
| `git-guardrails-claude-code` | Set up Claude Code hooks to block dangerous git commands (push, reset --hard, clean, branch -D, etc.) before they… |
| `goal` | Set a goal that Codex will pursue to completion. |
| `grill-me` | A relentless interview to sharpen a plan or design. |
| `grill-with-docs` | A relentless interview to sharpen a plan or design, which also creates docs (ADR's and glossary) as we go. |
| `grilling` | Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or… |
| `handoff` | Compact the current conversation into a handoff document for another agent to pick up. |
| `implement` | Implement a piece of work based on a spec or set of tickets. |
| `improve-codebase-architecture` | Scan a codebase for deepening opportunities, present them as a visual HTML report, then grill through whichever one you… |
| `interaction-design` | Design and implement microinteractions, motion design, transitions, and user feedback patterns. Use when adding polish… |
| `interface-craft` | Interface Craft by Josh Puckett — a toolkit for building polished, animated interfaces in React. Includes Storyboard… |
| `interface-design` | This skill is for interface design — dashboards, admin panels, apps, tools, and interactive products. NOT for… |
| `internal-comms` | A set of resources to help me write all kinds of internal communications, using the formats that my company likes to… |
| `loop-me` | Grill me about specs for the workflows I want to build, within this workspace. |
| `loop` | >- |
| `mcp-builder` | Guide for creating high-quality MCP (Model Context Protocol) servers that enable LLMs to interact with external… |
| `migrate-to-shoehorn` | Migrate test files from `as` type assertions to @total-typescript/shoehorn. Use when user mentions shoehorn, wants to… |
| `migrate-to-skills` | >- |
| `new-repo` | >- |
| `nuxt` | Nuxt full-stack Vue framework with SSR, auto-imports, and file-based routing. Use when working with Nuxt apps, server… |
| `onboard` | >- |
| `origin` | >- |
| `pdf` | Use this skill whenever the user wants to do anything with PDF files. This includes reading or extracting text/tables… |
| `pinia` | Pinia official Vue state management library, type-safe and extensible. Use when defining stores, working with… |
| `plan-ceo-review` | \| |
| `plan-eng-review` | \| |
| `pnpm` | Node.js package manager with strict dependency resolution. Use when running pnpm specific commands, configuring… |
| `pptx` | Use this skill any time a .pptx file is involved in any way — as input, output, or both. This includes: creating… |
| `prototype` | Build a throwaway prototype to answer a design question. Use when the user wants to sanity-check whether a state model… |
| `qa` | \| |
| `refero-design` | Research-First design methodology using Refero MCP. Use when creating new screens, flows, or interfaces—especially… |
| `rename-chat` | >- |
| `research` | Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo. Use… |
| `resolving-merge-conflicts` | Use when you need to resolve an in-progress git merge/rebase conflict. |
| `retro` | \| |
| `review-animations` | Reviews animation and motion code against a high craft bar derived from Emil Kowalski's design engineering philosophy… |
| `review-bugbot` | Review code changes with Bugbot subagent. |
| `review-security` | Review code changes with Security Review subagent. |
| `review` | \| |
| `scaffold-exercises` | Create exercise directory structures with sections, problems, solutions, and explainers that pass linting. Use when… |
| `schedule` | Create a scheduled task that can be run on demand or automatically on an interval. |
| `sdk` | >- |
| `setup-browser-cookies` | \| |
| `setup-cowork` | Guided Cowork setup — install a matching plugin, try a skill, connect tools. |
| `setup-matt-pocock-skills` | Configure this repo for the engineering skills: set up its issue tracker, triage label vocabulary, and domain doc… |
| `setup-pre-commit` | Set up Husky pre-commit hooks with lint-staged (Prettier), type checking, and tests in the current repo. Use when user… |
| `setup-ts-deep-modules` | Wire dependency-cruiser into a TypeScript repo so each package is a deep module, with implementation hidden in… |
| `share` | >- |
| `shell` | >- |
| `ship` | \| |
| `skill-creator` | Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to create a… |
| `slack-gif-creator` | Knowledge and utilities for creating animated GIFs optimized for Slack. Provides constraints, validation tools, and… |
| `slidev` | Create and present web-based slides for developers using Markdown, Vue components, code highlighting, animations, and… |
| `source-command-baseline-ui` | Enforces an opinionated UI baseline to prevent AI-generated interface slop. |
| `source-command-canvas-design` | Create beautiful visual art in .png and .pdf documents using design philosophy. You should use this skill when the user… |
| `source-command-design-lab` | Conduct design interviews, generate five distinct UI variations in a temporary design lab, collect feedback, and… |
| `source-command-fixing-accessibility` | Fix accessibility issues. |
| `source-command-fixing-metadata` | Ship correct, complete metadata. |
| `source-command-fixing-motion-performance` | Fix animation performance issues. |
| `source-command-frontend-design` | Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to… |
| `source-command-interface-design` | This skill is for interface design — dashboards, admin panels, apps, tools, and interactive products. NOT for… |
| `source-command-ui-ux-pro-max` | UI/UX design intelligence. 50 styles, 21 palettes, 50 font pairings, 20 charts, 9 stacks (React, Next.js, Vue, Svelte… |
| `source-command-web-design-guidelines` | Review UI code for Web Interface Guidelines compliance. Use when asked to \"review my UI\", \"check accessibility\"… |
| `split-to-prs` | >- |
| `statusline` | >- |
| `swiftui-ui-patterns` | Best practices and example-driven guidance for building SwiftUI views and components. Use when creating or refactoring… |
| `tdd` | Test-driven development. Use when the user wants to build features or fix bugs test-first, mentions… |
| `teach` | Teach the user a new skill or concept, within this workspace. |
| `theme-factory` | Toolkit for styling artifacts with a theme. These artifacts can be slides, docs, reportings, HTML landing pages, etc… |
| `to-questionnaire` | Turn a decision you can't fully answer into a questionnaire for someone else to fill in. |
| `to-spec` | Turn the current conversation into a spec and publish it to the project issue tracker: no interview, just synthesis of… |
| `to-tickets` | Break a plan, spec, or the current conversation into a set of tracer-bullet tickets, each declaring its blocking edges… |
| `triage` | Move issues and external PRs through a state machine of triage roles, categorise, verify, grill if needed, and write… |
| `tsdown` | Bundle TypeScript and JavaScript libraries with blazing-fast speed powered by Rolldown. Use when building libraries… |
| `turborepo` | \| |
| `ui-ux-pro-max` | UI/UX design intelligence. 50 styles, 21 palettes, 50 font pairings, 20 charts, 9 stacks (React, Next.js, Vue, Svelte… |
| `unocss` | UnoCSS instant atomic CSS engine, superset of Tailwind CSS. Use when configuring UnoCSS, writing utility rules… |
| `update-cli-config` | >- |
| `update-cursor-settings` | >- |
| `vite` | Vite build tool configuration, plugin API, SSR, and Vite 8 Rolldown migration. Use when working with Vite projects… |
| `vitepress` | VitePress static site generator powered by Vite and Vue. Use when building documentation sites, configuring themes, or… |
| `vitest` | Vitest fast unit testing framework powered by Vite with Jest-compatible API. Use when writing tests, mocking… |
| `vue-best-practices` | MUST be used for Vue.js tasks. Strongly recommends Composition API with `<script setup>` and TypeScript as the standard… |
| `vue-router-best-practices` | Vue Router 4 patterns, navigation guards, route params, and route-component lifecycle interactions. |
| `vue-testing-best-practices` | Use for Vue.js testing. Covers Vitest, Vue Test Utils, component testing, mocking, testing patterns, and Playwright for… |
| `vue` | Vue 3 Composition API, script setup macros, reactivity system, and built-in components. Use when writing Vue SFCs… |
| `vueuse-functions` | Apply VueUse composables where appropriate to build concise, maintainable Vue.js / Nuxt features. |
| `wait-what` | Stop. That last message did not land: re-pitch it. |
| `wayfinder` | Plan a huge chunk of work (more than one agent session can hold) as a shared map of decision tickets on your issue… |
| `wcag-audit-patterns` | Conduct WCAG 2.2 accessibility audits with automated testing, manual verification, and remediation guidance. Use when… |
| `web-artifacts-builder` | Suite of tools for creating elaborate, multi-component claude.ai HTML artifacts using modern frontend web technologies… |
| `web-design-guidelines` | Review UI code for Web Interface Guidelines compliance. Use when asked to "review my UI", "check accessibility", "audit… |
| `wizard` | Generate an interactive bash wizard that walks a human through steps only they can perform. Use when provisioning… |
| `writing-beats` | Writing, exploit; assemble raw material into a journey of beats, grounding each term before a beat leans on it. |
| `writing-for-agents` | Writing documents for agents. Use when creating or editing skills, or modifying AGENTS.md or CLAUDE.md. |
| `writing-fragments` | Writing, explore: mine raw fragments, no structure yet. |
| `writing-shape` | Writing, exploit: shape raw material into an article, paragraph by paragraph. |
| `xlsx` | Use this skill any time a spreadsheet file is the primary input or output. This means any task where the user wants to… |
