# 02 — South-Facing Game Anchor

**This is the most important image you will generate.** Every animation and every other direction is built from this. Get it right.

![Selected south anchor](../references/anchors/02-south-anchor.png)

## When to use

- You have a concept direction and now need a game-ready sprite
- You want chunky pixel-art-style output that reads cleanly at small sizes

## Inputs

- **Text prompt** (template below)
- **Image 1** — pixel-grid reference: [`references/grids/alternating-pixels-1024.png`](../references/grids/alternating-pixels-1024.png) — enforces chunky pixel-art block discipline

> ⚠️ **Do NOT pass your box art as an image reference here.** It will skew the output toward high-fidelity painterly. We tried it (see the rejected example below) — the prompt + grid approach gave the better game sprite.

| ✅ Prompt + grid | ❌ Direct img2img from box art |
|---|---|
| ![Selected](../references/anchors/02-south-anchor.png) | ![Rejected](../references/anchors/02b-south-from-boxart-rejected.png) |

## Prompt template

```text
Intended use: a single south-facing idle sprite frame for a top-down 2D action game. Final artwork should behave like one logical {LOGICAL_FRAME_SIZE} in-game frame, delivered at {OUTPUT_SIZE} so each sprite pixel reads as a clean block.

Image 1 role: pixel-grid anchor. Use it only to enforce chunky pixel-art block discipline and a centered single-frame composition. Do not copy its content.

Subject:
- {CHARACTER_NAME}, {ARCHETYPE}, facing SOUTH directly toward the camera in 3/4 top-down game perspective.
- This is the canonical idle frame.
- {SILHOUETTE_NOTES}
- {COSTUME_DETAILS}
- {PROP_DETAILS}
- calm readable idle expression/pose.

Frame rules:
- One character only, centered.
- Full body visible.
- Visible body fits within the intended logical sprite box.
- Anchor/foot plant at bottom-center.
- Preserve idle readability, not an attack pose.

Style:
- polished SNES-era / high-resolution pixelated game sprite
- chunky readable silhouette
- crisp edges
- limited surface shading plus small highlight pixels
- consistent top-left light source

Background:
- solid removable chroma color, preferably #FF00FF, outside the sprite silhouette
- no scenery, props, borders, UI, text, logo, or watermark

Avoid:
- photorealism
- painterly blending
- anti-aliased halos
- extra characters
- complex background
- symbols/runes/text if not wanted
```

## Recommended sizes

- `{LOGICAL_FRAME_SIZE}` = `256x256` (good balance for top-down 2D games)
- `{OUTPUT_SIZE}` = `1024x1024`

## Notes

- Always specify a **chroma background** (`#FF00FF` magenta or `#00FF00` green) — you'll key it out later in the normalization step.
- Output is "mixels" (fake pixel art) — pixels-of-pixels rather than true 1:1 pixel art. That's fine for prototyping; for true pixel art you'll need a separate snapping step.

## Next step

→ [03 — Neutral Anchor Reset](03-neutral-anchor.md)
