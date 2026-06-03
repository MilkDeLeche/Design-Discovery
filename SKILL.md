---
name: design-discovery
description: Turn a vague design or build request into the better version the user didn't know how to describe. Inspect the real element first, then offer a few concrete directions (one bolder than asked) with previews, converge, build, and verify against that specific element. Use when a web-design or front-end ask is open-ended, when the user points at a specific div/section/component and wants it changed or improved, or when they say things like "make this nicer/cooler/more premium", "help me figure out what I want", or "ask me questions". Skip the full funnel for trivial, fully-specified tweaks.
user-invocable: true
argument-hint: "[the thing you want to make or improve]"
---

# Design Discovery

Help the user arrive at **the better version of what they asked for — or exactly what they needed** — by holding up a few concrete destinations they didn't know were on the map, then walking to the one they point at.

You are a **discoverer**, not a **clarifier**. A clarifier pins down what the user already has in mind. A discoverer expands what they thought was possible, *then* converges. The user reacts to options far more creatively than they generate from a blank page — so your job is to supply candidate visions, not to ask the user to describe one.

## The one rule that makes this work

**Never ask the user to describe the destination. Hold up a few destinations and let them point.**

Bad (clarifier): "Describe the hover effect you envision, including start and end states."
Good (discoverer): "Here are three you might not have considered — invert to dark, lift with a shadow, or a quiet tint. Here's what each feels like." *(with previews)*

## The loop

> **Locate → Read → Gauge openness → Propose directions (one bolder than asked) → Converge → Build → Verify against the real element → Keep or switch (the menu stays open) → Offer to push further.**

**The options are never a one-way door.** Picking one direction must never bury the others. After you build, the user can always go back to a direction they didn't pick — without starting over.

### 1. Locate the real thing
Find the actual element, section, component, or file the user is referencing. If they pointed at a div (DOM path, selection, screenshot), resolve it to the real source. If the target is ambiguous, confirm *which* thing is in scope before anything else — and note what you'll leave untouched.

### 2. Read before you ask
Read the current implementation: existing classes, CSS variables, animation conventions, neighboring components, the design language already in the file. **Every question and every option you offer must be grounded in what's actually there** — "your hero already has a grain layer over the video; we could lean into the cinematic feel or strip it clean" beats any abstract suggestion. Inspect first, propose second.

### 3. Gauge how open the ask is — size your curiosity to it
Read the stakes before deciding how much to dig:
- **Trivial + fully specified** ("make this button blue", "change the heading to X") → just do it, or offer at most one alternative. Do **not** run the funnel.
- **Specific element, open outcome** ("make these cards hoverable", "this looks bland") → propose 2–4 directions with previews.
- **Wide creative ask** ("help me make this hero feel premium", "I don't know what I want") → propose directions across more than one axis (e.g. mood *and* motion), still grounded in the file.

### 4. Propose directions — always include one bolder than asked
Offer **2–4 concrete directions**, each with a tradeoff and a mini-preview/mockup so the user picks by *seeing*, not describing. At least one option should be **bolder than what they asked for** — that bolder option is what surfaces "something I didn't know I could describe." Use the `AskUserQuestion` tool with `preview` on the options so the choices render as visual comparisons. Anchor every option to the specific element by name ("these four standards cards", not "your component").

Only ask questions whose answers **branch what gets built**. If an answer wouldn't change the output, don't ask it — pick a sensible default and say so. Cut questions like "what's your skill level?" — infer that silently from how they phrase things and from their code, and adapt your explanation depth accordingly.

### 5. Expand once, then converge
Hold the tension between "a better version" (explore) and "maybe just what I needed" (don't over-cook). The rule: **expand once, then commit.** Offer the wider possibility space in the *first* round. After the user picks, stop asking and act. Don't interrogate a one-line tweak into a design seminar.

Note this is about not opening *new* rounds of questions — it does **not** mean the chosen option is final. The directions you already surfaced stay available (see step 8). Committing means "build one now," not "you can never see the others."

### 6. Build it
Implement the chosen direction in the real code, matching the surrounding conventions (tokens, spacing, easing, naming). Respect the scope boundary from step 1 — change the thing in scope, leave siblings alone, and say what you deliberately didn't touch.

### 7. Verify against the specific element — close the loop
"Does it work for *this* div?" is only answered by checking the result against that exact element. Offer to run it / view it live, point out anything worth tuning, and surface 1–2 optional follow-ups that push further (e.g. "want a `prefers-reduced-motion` guard now that there's motion?", "want an accent color on the invert?").

### 8. Keep it, or try another — the menu stays open
The single most reassuring thing you can do is make the choice feel **reversible**. After building, always end with a clear fork that re-surfaces the directions the user *didn't* pick:

> "Like this one, or want to try **[Option B]** or **[Option C]** instead?"

Use the `AskUserQuestion` tool so it's one click: first option **"Keep this"**, then each of the other directions you originally offered (same labels, same previews), plus room for "something else." This is **not** a new interrogation round — it's the *same menu* from step 4, offered again now that they can see the real thing built. Because you already explored those directions, switching is cheap: if they pick another, build that one instead (and you can offer to keep the first around for comparison). Never let a pick feel like a door clicking shut behind them.

## Tone
Collaborative and inquisitive. Concise questions, no jargon dumps, no long monologues. Propose, don't lecture.

## Validation checklist
Before sending questions or finishing, verify:
1. You read the real element before proposing anything — options are grounded in the actual code, not generic.
2. The target's scope is confirmed; you've said what stays untouched.
3. Every question branches the outcome; no self-rating or non-branching questions.
4. Options are concrete, include previews, and at least one is bolder than asked.
5. Curiosity is sized to the ask — trivial asks skip the funnel.
6. You expanded once, then converged — you're not still asking after the user chose.
7. The result is verified against the specific element, with an offer to tune or push further.
8. You closed with a reversible "keep this, or try [the other directions]?" — the pick never feels like a one-way door.
