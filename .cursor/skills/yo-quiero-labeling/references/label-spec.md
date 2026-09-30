# Yo Quiero Label Spec

Visual and copy rules for stakeholder labels placed **above** design frames,
flows, and prototype screens. Shared with `yo-quiero-mode` when creating boards.

## Heat identity

| Heat | Short label | Accent (approx) | Meaning (stakeholder one-liner) |
| --- | --- | --- | --- |
| Mild | MILD | `#2F6F3E` soft green | Safe, minimal change / conventional path |
| Hot | HOT | `#C47A1A` amber | Noticeable upgrade, still familiar |
| Spicy | SPICY | `#C43B1A` red-orange | Ambitious craft + real complexity |
| Inferno | INFERNO | `#5B1A1A` deep crimson | Stretch / swing for the fences |

Do not invent alternate heat names on the canvas. Normalize Medium→Hot, Fire→Spicy, Diablo→Inferno.

## Label anatomy

Each label sits **above** its target frame (not overlaid on the art):

```
┌─────────────────────────────────────────────┐
│  [HEAT]  Concept name                       │
│          One-line why this heat             │
└─────────────────────────────────────────────┘
        24px gap
┌─────────────────────────────────────────────┐
│                                             │
│              Design frame / flow            │
│                                             │
└─────────────────────────────────────────────┘
```

### Structure

1. **Container** — auto-layout VERTICAL, hug contents, fill width of target frame
2. **Row** — horizontal: heat badge + concept name
3. **Subtitle** — "why this heat" (max about 80 characters)
4. **Gap** — 24px between label block and the top of the design frame

### Typography (Figma)

Prefer existing text styles from the file's design system when present. Fallback:

| Role | Size | Weight | Case |
| --- | --- | --- | --- |
| Heat badge | 12 | Bold | ALL CAPS, tracked +4% |
| Concept name | 16 to 18 | Semi Bold | Sentence / title case |
| Subtitle | 12 to 13 | Regular | Sentence case |

### Heat badge

- Pill / rounded rect, padding about 6×10
- Fill = heat accent at about 15% opacity (or solid accent with white text if file is dark)
- Text = heat accent (or white on solid)
- Characters exactly: `MILD` | `HOT` | `SPICY` | `INFERNO`

### Naming in layers

- Label group: `YQ Label / <Heat> - <Concept>`
- Badge: `Heat Badge`
- Title: `Concept Name`
- Subtitle: `Why This Heat`
- Target frames: `<Heat> - <Concept> / <Screen>`

## Placement rules

1. **Above, never on.** Labels sit above frames/flows. Do not float badges on hero media or inside screens.
2. **One heat per column or flow.** If a flow has multiple screens of the same heat, put a **flow-level label** above the first screen and lighter screen tags (`SPICY 02`) above later screens, or one label spanning the flow group.
3. **Align to frame width.** Label width matches the frame (or the flow group bounds).
4. **Consistent Y.** When four heats sit in a row, align all label baselines.
5. **Prototype screens.** For prototype starting points / device frames, label the outermost device/frame the stakeholder sees first.
6. **Don't restyle the product UI** to encode heat. Chrome is only in the label.

## Legend frame (optional but recommended)

Create a frame `YQ Spectrum Legend` on the same page:

```
Mild → Hot → Spicy → Inferno

Mild     Safe / minimal change
Hot      Clear step up, still familiar
Spicy    Ambitious craft + eng lift
Inferno  Stretch: swing for the fences
```

Place it top-left or above the four-column board. Keep it compact.

## Mapping existing work to heats

When the user asks to label work that wasn't created in yo-quiero-mode:

1. Infer heat from ambition signals (scope, new components, motion, eng risk). See sibling skill `yo-quiero-mode` → `references/spectrum.md`
2. Confirm mapping in chat if ambiguous (especially Spicy vs Inferno)
3. Apply labels; do not redesign screens unless asked

## Fallback without Figma

If Figma MCP is unavailable:

- Propose rename scheme: `Mild - <Concept>`, `Hot - <Concept>`, …
- Provide a markdown legend the user can paste into FigJam/slides
- Optionally write `docs/yo-quiero/<date>-<topic>/labels.md` with the mapping table
- For HTML boards from `yo-quiero-mode`, ensure each column already has heat chrome matching this spec
