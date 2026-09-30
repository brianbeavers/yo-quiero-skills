---
name: taco-bell-mode
description: >-
  Spin up four design directions on a Mild → Medium → Fire → Diablo ambition
  spectrum from a PRD or thin brief. Use when the user says taco-bell-mode,
  "sauce levels", "four heats", or wants stakeholder-ready concept options at
  increasing craft/complexity. Not for labeling existing Figma frames (use
  taco-bell-labeling) or building a single locked design.
disable-model-invocation: true
---

# Taco Bell Mode — Four Heats From a Brief

Generate **exactly four** concept directions for the same problem, calibrated to
**Mild / Medium / Fire / Diablo**. Stakeholders should instantly understand how
ambitious each option is—not just that the options look different.

## When to use

- Greenfield or early exploration with a PRD, requirements doc, or thin brief
- User says `taco-bell-mode`, `/taco-bell-mode`, or asks for sauce-level concepts
- Need side-by-side options that map effort and risk, not only aesthetics

## When not to use

- Labeling existing Figma frames/prototypes → `taco-bell-labeling`
- Implementing one already-chosen direction
- Pure visual theme swaps with no ambition difference

## Required reading

Load [`references/spectrum.md`](references/spectrum.md) before generating heats.
Treat it as the source of truth for ladder definitions, calibration axes, and
per-heat fields.

## Process

### 1. Ingest the brief

Read any linked PRD, requirements, notes, or prior design context. Infer:

- Job to be done / primary user outcome
- Audience and context of use
- Hard constraints (brand, platform, a11y, legal, existing system)
- Whether this is **optimization** (existing UI) or **net-new**

Ask **at most 1–2** clarifying questions only if missing a hard constraint that
would change all four heats. Prefer proceeding with explicit assumptions listed
at the top of the output.

### 2. Lock the constants

Before ideating, write a short **Constants** block that every heat must honor:

- Must-solve user job
- Non-negotiable requirements
- Brand / system constraints (if any)
- Success signal (how we’d know it worked)

These stay fixed. Only ambition, craft, and complexity vary.

### 3. Plan four heats on the ambition axis

Draft one concept per level. Check against `references/spectrum.md`:

| Heat | Optimization brief | Net-new brief |
| --- | --- | --- |
| Mild | Minimal safe polish on what exists | Safest conventional product approach |
| Medium | Noticeable upgrade, still familiar | Clear step up without reinventing |
| Fire | Ambitious surface redesign; new patterns | Complex interactions + new components + eng lift |
| Diablo | 200% swing; may remix product assumptions | Brand-defining moonshot; mark as stretch |

Reject and regenerate any pair that differs only by color, copy tone, or density
tweaks.

### 4. Present side-by-side

Output in this order:

1. **Brief playback** (3–6 bullets) + **Constants**
2. **Heat comparison table** (one row per heat: concept name, one-line thesis, build cost)
3. **Full heat cards** — Mild → Medium → Fire → Diablo, each with every field from
   `references/spectrum.md` → Per-heat output fields
4. **Mix prompts** — 2–3 suggested hybrids (e.g. “Medium IA + Fire motion”)
5. **Decision ask** — which heat (or mix) to deepen next

Keep prose tight. No lorem. Use real product language from the brief.

### 5. Surface artifacts

**Default: Figma-first when Figma is available**

If the user provides a Figma file URL/key and Figma MCP works:

1. Load `figma-use` (mandatory before any `use_figma` call)
2. Create or clear a page named `Taco Bell Mode — <topic>`
3. Lay out **four columns**: Mild | Medium | Fire | Diablo
4. In each column: heat label (per labeling conventions), concept title, thesis
   text, and placeholder frames for key screens (name them clearly)
5. Optionally invoke `taco-bell-labeling` patterns so labels match stakeholder chrome

If Figma is unavailable or the user prefers speed:

- Ship a self-contained **HTML comparison board** under
  `docs/taco-bell/<YYYY-MM-DD>-<topic>/board.html` with four columns and the same
  content, **or**
- Ship markdown-only heat cards when visuals aren’t needed yet

State which artifact path you used.

### 6. Iterate

On follow-up:

- Deepen one heat into flows/screens
- Remix (“Fire interaction model at Medium cost”)
- Regenerate a single heat without touching the others
- Hand off to `taco-bell-labeling` once frames exist in Figma

## Output quality bar

- All four heats feel like credible product directions, not moodboards
- Fire and Diablo call out technical complexity honestly
- Mild never feels like a strawman; it must be a shippable safe path
- Diablo is exciting but labeled stretch so it doesn’t derail scope by accident

## Triggers / aliases

Treat these as invocations of this skill:

- `taco-bell-mode`
- `/taco-bell-mode`
- “run taco bell mode”
- “four heats” / “sauce level concepts” (when asking for new directions)
