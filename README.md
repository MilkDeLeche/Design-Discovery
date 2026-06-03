# design-discovery

A Claude Code skill that turns a vague design or build request into the better
version you didn't know how to describe.

Instead of asking you to describe what you want, it **inspects the actual
element first**, then offers a few concrete directions (one bolder than you
asked for) with previews, converges on your pick, builds it, and verifies the
result against that specific element.

## Install

Copy the `design-discovery` folder into your Claude Code skills directory:

- **Global (all projects):** `~/.claude/skills/design-discovery/`
  (Windows: `C:\Users\<you>\.claude\skills\design-discovery\`)
- **Per-project:** `<project>/.claude/skills/design-discovery/`

Restart Claude Code and the skill is available.

## Use

- Type `/design-discovery` (optionally `/design-discovery make my footer feel premium`), or
- Just say something open-ended like "make this nicer" / "help me figure out what I want"
  and it surfaces on its own.

It skips the full question funnel for trivial, fully-specified tweaks.

## The loop

Locate → Read → Gauge how open the ask is → Propose directions (one bolder than
asked) with previews → Converge → Build → Verify against the real element →
Offer to push further.
