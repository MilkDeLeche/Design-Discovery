<div align="center">

# 🧭 design-discovery

### The Claude Code skill that asks the right questions *for* you.

*Stop describing what you want. Point at what you like.*

[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-skill-da7756?logo=anthropic&logoColor=white)](https://docs.claude.com/en/docs/claude-code)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)
[![Stars](https://img.shields.io/github/stars/MilkDeLeche/Design-Discovery?style=social)](https://github.com/MilkDeLeche/Design-Discovery/stargazers)

</div>

---

## The problem

You're vibe coding. You point at a thing and say *"make this cooler."*

The AI either guesses wrong, or fires back *"describe the animation you envision, including start and end states."* — and now **you** have to do the design thinking you opened the AI to avoid.

You don't always know what you want. You just know the current thing isn't it.

## The fix

`design-discovery` flips the script. Instead of asking you to describe a destination, it **reads your actual code first**, then holds up a few concrete directions — one of them bolder than you asked for — and lets you pick by *seeing*.

> You react to options far more creatively than you generate from a blank page. This skill supplies the options.

It's a **discoverer**, not a clarifier. A clarifier pins down what you already had in mind. A discoverer expands what you thought was possible — *then* converges and builds it.

---

## See it work

You point at four service cards and say: **"make these hoverable, with a highlight."**

Instead of guessing, the skill reads the cards, sees they have no hover state, and offers:

```
┌─ Hover style ───────────────────────────────────────────┐
│                                                          │
│  ① Invert (dark fill)     ② Lift + shadow    ③ Tint     │
│  ┌──────────┐             ┌──────────┐      ┌─────────┐  │
│  │ ███ ELEC │ ← dark on   │ accent   │ ↑    │ ▓▓ ELEC │  │
│  │ ███ light│   hover     │ ELEC     │ lift │ ▓▓ tint │  │
│  └──────────┘             └──────────┘      └─────────┘  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

You click **①**. It builds the invert hover — matching your existing CSS variables and easing — then verifies it against *those specific cards*, and offers to add a `prefers-reduced-motion` guard.

No blank-page paralysis. No essay describing pixels. You pointed; it shipped.

---

## How it works

```
Locate → Read → Gauge how open the ask is → Propose directions
  (one bolder, with previews) → Converge → Build
  → Verify against the real element → Keep or switch (the menu stays open)
  → Offer to push further → (on wrap-up) leave a PROGRESS.md handoff
```

1. **Locate** the actual element / component / file you mean.
2. **Read** the real code first — existing tokens, conventions, neighbors.
3. **Gauge** the ask. Trivial + specific? It just does it. Open-ended? It opens up the option space.
4. **Propose** distinct directions with visual previews — always one bolder than you asked, and always with an off-ramp (see below).
5. **Converge** on your pick. Expand once, then commit (no endless interrogation).
6. **Build** it, matching your code's style — leaning on installed expert skills (e.g. GSAP) for the domains they cover.
7. **Verify** against the real thing.
8. **Keep or switch** — re-offers the directions you *didn't* pick, so a choice is never a one-way door.
9. **On wrap-up** (only when it's genuinely time to stop) — create or update a `PROGRESS.md` so the next session resumes cold.

---

## What makes it different

These are the guardrails that keep it useful instead of annoying:

- **🔙 Choices stay reversible.** After it builds, it re-offers the other directions — picking one never buries the rest.
- **🚪 Always an off-ramp.** Every question quietly carries *"I'll take it from here"* and *"Let's talk it through"* — but variety of real options comes first; the exits never crowd them out.
- **🏠 Borrows ideas, builds in your house style.** Ask it to take cues from another site and it researches the *patterns* — then executes 100% in your tokens, type scale, and components, so nothing looks transplanted.
- **🧠 Stands on expert skills.** For domains with a dedicated skill installed (animation → the official GSAP skills, etc.), it invokes that skill instead of improvising — and tells you which one.
- **🧭 Leaves a breadcrumb.** When you wrap up, it updates a `PROGRESS.md` handoff (goal, done, what's left, how to resume) — updated in place, never duplicated.

---

## Install

Drop the `design-discovery` folder into your Claude Code skills directory:

```bash
# Global — available in every project
git clone https://github.com/MilkDeLeche/Design-Discovery.git \
  ~/.claude/skills/design-discovery
```

| Scope | Path |
|-------|------|
| **Global** (all projects) | `~/.claude/skills/design-discovery/` |
| **Per-project** | `<your-project>/.claude/skills/design-discovery/` |

> **Windows:** `C:\Users\<you>\.claude\skills\design-discovery\`

Restart Claude Code and you're set.

## Use

**You don't need to remember a command.** Point at any element and ask a plain question — the skill reads that element and its styles, then runs the whole loop:

```
"what can we do with the nav?"
"make these cards hoverable"
"this hero looks bland"
"help me figure out what I want here"
```

It reads the *real* nav, the *real* cards, the *real* hero — then offers grounded directions with previews. No spec-writing on your end.

Prefer to be explicit? The slash command works too:

```bash
/design-discovery                              # let it lead
/design-discovery make my footer feel premium  # give it a target
```

It **skips the question funnel** for trivial, fully-specified tweaks — so it never gets in your way when you already know exactly what you want.

---

## Works on anything

The skill grounds itself in *your* code, so it isn't tied to any one stack or element.

| It works on… | Examples |
|---|---|
| **Any element** | a single `<div>`, a nav, a card grid, a hero, a whole section |
| **Any framework** | React · Vue · Svelte · Astro · plain HTML |
| **Any styling** | Tailwind · vanilla CSS · CSS variables · styled-components |
| **Anywhere Claude Code runs** | terminal · VS Code · JetBrains · the web app |

Point at a thing, ask "what can we do here?", and it figures out the rest from what's actually on the page.

---

## Why vibe coders like it

- 🎯 **Grounded** — reads your real code, so suggestions actually fit your project.
- 👀 **Show, don't tell** — pick from visual previews instead of writing specs.
- 🚀 **One bolder option, always** — surfaces the thing you didn't know to ask for.
- 🧠 **Knows when to shut up** — small ask, small response. No over-engineering.
- ✅ **Closes the loop** — builds it *and* checks it against the thing you pointed at.

## Companion skill

Pairs with **[FontPlaybook](https://github.com/MilkDeLeche/FontPlaybook)** — keep them separate, but aware:

- **design-discovery** — broad creative director: inspect the real element, offer directions, converge, build, verify.
- **font-playbook** — typography specialist: audit fonts, research industry fit, recommend best/safe/bold fits, implement loading and CSS tokens, verify rendering.

When the problem is specifically fonts, hierarchy, loading, pairing, or industry-matched type, design-discovery delegates to `font-playbook` instead of guessing at Google Fonts.

## Contributing

PRs and ideas welcome — new question patterns, better previews, smarter scope detection. Open an issue or a pull request.

## License

[MIT](./LICENSE) © MilkDeLeche
