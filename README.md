# Yo Quiero

Cursor Agent Skills for presenting design options on a **Mild → Hot → Spicy → Inferno** ambition spectrum.

## Two skills

| Skill | Folder | Invoke with | Job |
| --- | --- | --- | --- |
| **yo-quiero-mode** | [`.cursor/skills/yo-quiero-mode/`](.cursor/skills/yo-quiero-mode/) | `yo-quiero-mode` or `/yo-quiero-mode` | From a PRD/brief → four ambition-level directions + **HTML board** |
| **yo-quiero-labeling** | [`.cursor/skills/yo-quiero-labeling/`](.cursor/skills/yo-quiero-labeling/) | `yo-quiero-labeling` or `/yo-quiero-labeling` | Drop heat labels **above** existing Figma frames / prototype screens |

Each skill is its own directory with its own `SKILL.md`. They share the ladder via
[`yo-quiero-mode/references/spectrum.md`](.cursor/skills/yo-quiero-mode/references/spectrum.md).
Both set `disable-model-invocation: true`, so the agent only loads them when you
invoke them.

## How to invoke one vs the other

1. Open **Agent** chat in a project that includes this repo (or copy `.cursor/skills/` into yours).
2. Type `/` and search for the skill name, or start your message with the trigger phrase.
3. Attach the right input:

| You want… | Say… | Attach… |
| --- | --- | --- |
| Four new directions | `yo-quiero-mode` | PRD, requirements, or thin brief |
| Labels on existing designs | `yo-quiero-labeling` | Figma file URL + which frames/flows |

### Example: mode

```text
yo-quiero-mode

Here's our PRD for team onboarding. Give me Mild → Inferno directions.
```

### Example: labeling

```text
yo-quiero-labeling

Figma: <file url>
Label the four concept columns Mild / Hot / Spicy / Inferno and add the legend.
```

## Spectrum (ambition levels)

| Heat | Meaning |
| --- | --- |
| **Mild** | Minimal safe change (optimization) or safest conventional path (net-new) |
| **Hot** | Noticeable upgrade, still familiar |
| **Spicy** | Ambitious craft, new components/interactions, real eng lift |
| **Inferno** | Swing for the fences: stretch / 200% |

## Artifacts

- **yo-quiero-mode (default):** HTML comparison board at `docs/yo-quiero/<date>-<topic>/board.html`
- **yo-quiero-labeling:** Figma labels via Figma MCP + `figma-use`; if Figma isn't connected, markdown rename map + legend under `docs/yo-quiero/`

### Figma prerequisite (labeling)

1. Figma MCP connected and authenticated in Cursor
2. Access to the target file
3. Agent loads **`figma-use`** before any `use_figma` mutations (the skill instructs this)

Label visual rules: [`.cursor/skills/yo-quiero-labeling/references/label-spec.md`](.cursor/skills/yo-quiero-labeling/references/label-spec.md)

## How-it-works demo (in this repo)

Laid-out demo (GitHub Pages):

**[¡Yo Quiero! Mode board](https://brianbeavers.github.io/yo-quiero-skills/yo-quiero/how-it-works/board.html)**

Source file: [`docs/yo-quiero/how-it-works/board.html`](docs/yo-quiero/how-it-works/board.html) (the `/blob/` GitHub URL shows code only — use the Pages link above for the designed page).

## Repo layout

```text
.cursor/skills/
  yo-quiero-mode/
    SKILL.md
    references/spectrum.md
  yo-quiero-labeling/
    SKILL.md
    references/label-spec.md
docs/yo-quiero/          # trial / generated boards
README.md
```

## Install elsewhere

```bash
git clone https://github.com/brianbeavers/yo-quiero-skills.git ~/.cursor/skills/yo-quiero
```

Or copy both skill folders into another project’s `.cursor/skills/`.
Refresh Customize → Skills if they don’t appear.

Publishing this repo to GitHub: see [PUBLISH_PERSONAL_GITHUB.md](PUBLISH_PERSONAL_GITHUB.md).

## Out of scope (for now)

- Marketplace publishing
- Full design-lab rating / feedback overlay loops
- Auto-implementing all four heats in production code
