# Taco Bell Skills

Cursor Agent Skills for presenting design options on a **Mild → Medium → Fire → Diablo** ambition spectrum (sauce-packet levels stakeholders already understand).

Nothing in the official Cursor / Claude / Codex libraries ships this ladder. These two skills encode it as explicit workflows you invoke by name.

## Skills

| Skill | Invoke with | What it does |
| --- | --- | --- |
| **taco-bell-mode** | `taco-bell-mode` | From a PRD or thin brief, spin up **four** directions at increasing craft/complexity |
| **taco-bell-labeling** | `taco-bell-labeling` | Drop spectrum labels **above** Figma frames, flows, or prototype screens |

Both live under [`.cursor/skills/`](.cursor/skills/) and use `disable-model-invocation: true`, so they run when you call them—not on every design chat.

## Spectrum

| Heat | Meaning |
| --- | --- |
| **Mild** | Minimal safe change (optimization) or safest conventional path (net-new) |
| **Medium** | Noticeable upgrade, still familiar |
| **Fire** | Ambitious craft, new components/interactions, real eng lift |
| **Diablo** | Swing for the fences — stretch / 200% |

Full calibration: [`.cursor/skills/taco-bell-mode/references/spectrum.md`](.cursor/skills/taco-bell-mode/references/spectrum.md)

## How to use in Cursor

1. Open Agent chat in a project that includes this repo (or copy `.cursor/skills/` into yours).
2. Type `/` and pick the skill, **or** say `taco-bell-mode` / `taco-bell-labeling` in the prompt.
3. Attach a PRD/brief (mode) or a Figma file URL plus target frames (labeling).

### Example — concept development

```text
taco-bell-mode

Here's our PRD for onboarding. Give me Mild → Diablo directions.
```

### Example — stakeholder board chrome

```text
taco-bell-labeling

Figma: <file url>
Label the four concept columns Mild / Medium / Fire / Diablo and add the legend.
```

## Figma prerequisite (labeling + Figma boards)

`taco-bell-labeling` (and Figma output from `taco-bell-mode`) needs:

1. **Figma MCP** connected and authenticated in Cursor
2. Access to the target file
3. The agent loading **`figma-use`** before any `use_figma` mutations (the skill instructs this)

If Figma isn’t available, labeling falls back to a rename scheme + markdown legend; mode falls back to markdown heat cards or an HTML comparison board under `docs/taco-bell/`.

Label visual rules: [`.cursor/skills/taco-bell-labeling/references/label-spec.md`](.cursor/skills/taco-bell-labeling/references/label-spec.md)

## Repo layout

```text
.cursor/skills/
  taco-bell-mode/
    SKILL.md
    references/spectrum.md
  taco-bell-labeling/
    SKILL.md
    references/label-spec.md
README.md
```

## Install elsewhere

Copy `.cursor/skills/taco-bell-mode` and `.cursor/skills/taco-bell-labeling` into another project’s `.cursor/skills/` (or your user-level `~/.cursor/skills/`). Restart or refresh Agent skills if they don’t appear under Customize → Skills.

## Out of scope (for now)

- Marketplace publishing
- Full design-lab rating / feedback overlay loops
- Auto-implementing all four heats in production code
