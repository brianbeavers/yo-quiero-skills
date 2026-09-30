---
name: taco-bell-labeling
description: >-
  Drop Mild / Hot / Fire / Diablo labels above Figma design frames, flows, or
  prototype screens so stakeholders see ambition level at a glance. Use when the
  user says taco-bell-labeling, asks to sauce-label a board, or wants spectrum
  chrome on existing concepts. Not for inventing four new directions from a PRD
  (use taco-bell-mode).
disable-model-invocation: true
---

# Taco Bell Labeling — Spectrum Chrome for Stakeholders

Place consistent **Mild / Hot / Fire / Diablo** labels **above** design
frames, flows, and prototype screens. The product UI stays untouched; the chrome
communicates ambition level.

## When to use

- User says `taco-bell-labeling`, `/taco-bell-labeling`, or “sauce-label this”
- A Figma board / prototype already has multiple concepts or flows to classify
- Follow-up after `taco-bell-mode` once frames exist

## When not to use

- Generating four new directions from a brief → `taco-bell-mode`
- Restyling the product UI itself to look “spicier”
- Generic Figma component work unrelated to the spectrum

## Required reading

1. [`references/label-spec.md`](references/label-spec.md) — anatomy, color, placement
2. Sibling [`../taco-bell-mode/references/spectrum.md`](../taco-bell-mode/references/spectrum.md)
   — how to infer heat when mapping isn’t given

## Process

### 1. Gather targets

Need:

- Figma file URL or file key (ask once if missing)
- Which frames / flows / prototype screens to label
- Optional: explicit heat mapping from the user

If mapping is missing, infer heats from ambition signals (scope, new components,
motion, eng risk) using the spectrum reference. Confirm Fire vs Diablo when
borderline before writing to the file.

### 2. Load Figma skills

Before any canvas mutation:

1. Load **`figma-use`** (mandatory before every `use_figma` call)
2. Pass `skillNames` including `figma-use` (and this skill’s name for logging if supported)
3. Prefer `$fig` APIs for node creation; never assume raw `figma.create*` helpers exist

If Figma MCP is disconnected or auth fails: use the **fallback** in
`references/label-spec.md` (rename scheme + markdown legend). Do not pretend
labels were applied in Figma.

### 3. Apply labels

For each target (or each heat column):

1. Create a label group per [`references/label-spec.md`](references/label-spec.md)
2. Position it **above** the frame with **24px** gap—never as an overlay sticker on the art
3. Set heat badge, concept name, and “why this heat” subtitle
4. Align labels across a four-up board to a shared baseline
5. Optionally rename target frames: `<Heat> — <Concept> / <Screen>`

For multi-screen flows of one heat: one strong flow-level label above the first
screen; subsequent screens may use light tags (`FIRE · 02`) if helpful.

### 4. Add the legend

Unless the user declines, create a compact **`TB Spectrum Legend`** frame on the
page (copy from label-spec). Stakeholders should understand the ladder without a
meeting preamble.

### 5. Verify

Screenshot the labeled board (prefer `.screenshot()` on new trees via `$fig`).
Check:

- [ ] Correct heat names only (Mild / Hot / Fire / Diablo)
- [ ] Labels above frames, not covering content
- [ ] Consistent alignment and 24px gaps
- [ ] Legend present
- [ ] Layer names follow `TB Label / <Heat> — <Concept>`

### 6. Report

Reply with:

- Mapping table (frame/flow → heat → concept name)
- Link/page name where labels live
- Any assumptions (inferred heats)
- Offer to adjust mapping or hand back to `taco-bell-mode` for a missing heat

## Quality bar

- Readable at zoomed-out board scale (badge + title must scan)
- No decorative stickers, floating promo chips, or on-art badges
- Heat encoding lives in labels, not in random accent changes inside screens
- Diablo clearly reads as stretch when subtitle is present

## Triggers / aliases

- `taco-bell-labeling`
- `/taco-bell-labeling`
- “sauce-label” / “label the heats” / “Mild Hot Fire Diablo labels on this file”
