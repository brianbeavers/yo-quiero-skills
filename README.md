# Taco Bell Skills

Cursor Agent Skills for presenting design options on a **Mild → Hot → Fire → Diablo** ambition spectrum (sauce-packet levels stakeholders already understand).

## Two skills — not one file

| Skill | Folder | Invoke with | Job |
| --- | --- | --- | --- |
| **taco-bell-mode** | [`.cursor/skills/taco-bell-mode/`](.cursor/skills/taco-bell-mode/) | `taco-bell-mode` or `/taco-bell-mode` | From a PRD/brief → four ambition-level directions + **HTML board** |
| **taco-bell-labeling** | [`.cursor/skills/taco-bell-labeling/`](.cursor/skills/taco-bell-labeling/) | `taco-bell-labeling` or `/taco-bell-labeling` | Drop heat labels **above** existing Figma frames / prototype screens |

Each skill is its own directory with its own `SKILL.md`. They share the ladder via
[`taco-bell-mode/references/spectrum.md`](.cursor/skills/taco-bell-mode/references/spectrum.md).
Both set `disable-model-invocation: true`, so the agent only loads them when you
invoke them—not on every design chat.

## How to invoke one vs the other

1. Open **Agent** chat in a project that includes this repo (or copy `.cursor/skills/` into yours).
2. Type `/` and search for the skill name, **or** start your message with the trigger phrase.
3. Attach the right input:

| You want… | Say… | Attach… |
| --- | --- | --- |
| Four new directions | `taco-bell-mode` | PRD, requirements, or thin brief |
| Labels on existing designs | `taco-bell-labeling` | Figma file URL + which frames/flows |

### Example — mode

```text
taco-bell-mode

Here's our PRD for team onboarding. Give me Mild → Diablo directions.
```

### Example — labeling

```text
taco-bell-labeling

Figma: <file url>
Label the four concept columns Mild / Hot / Fire / Diablo and add the legend.
```

## Spectrum (ambition levels)

| Heat | Meaning |
| --- | --- |
| **Mild** | Minimal safe change (optimization) or safest conventional path (net-new) |
| **Hot** | Noticeable upgrade, still familiar |
| **Fire** | Ambitious craft, new components/interactions, real eng lift |
| **Diablo** | Swing for the fences — stretch / 200% |

## Artifacts

- **taco-bell-mode (default):** HTML comparison board at `docs/taco-bell/<date>-<topic>/board.html`
- **taco-bell-labeling:** Figma labels via Figma MCP + `figma-use`; if Figma isn’t connected, markdown rename map + legend under `docs/taco-bell/`

### Figma prerequisite (labeling)

1. Figma MCP connected and authenticated in Cursor  
2. Access to the target file  
3. Agent loads **`figma-use`** before any `use_figma` mutations (the skill instructs this)

Label visual rules: [`.cursor/skills/taco-bell-labeling/references/label-spec.md`](.cursor/skills/taco-bell-labeling/references/label-spec.md)

## Trial run (in this repo)

Sample outputs from a dry-run brief live under [`docs/taco-bell/`](docs/taco-bell/):

- Mode board: open the latest `board.html`
- Labeling fallback: open the latest `labels.md` (used when Figma isn’t available)

## Repo layout

```text
.cursor/skills/
  taco-bell-mode/
    SKILL.md
    references/spectrum.md
  taco-bell-labeling/
    SKILL.md
    references/label-spec.md
docs/taco-bell/          # trial / generated boards
README.md
```

## Install elsewhere

Copy both skill folders into another project’s `.cursor/skills/` (or `~/.cursor/skills/`).
Refresh Customize → Skills if they don’t appear.

## Out of scope (for now)

- Marketplace publishing
- Full design-lab rating / feedback overlay loops
- Auto-implementing all four heats in production code
