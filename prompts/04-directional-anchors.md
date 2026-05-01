# 04 — Directional Anchors (West, North)

From your approved neutral south, generate west-facing and north-facing anchors. **East = horizontal flip of west** — don't regenerate it, you'll just lose consistency.

![Directional anchor contact sheet](../references/anchors/04-directional-contact.png)

## Inputs

- **Image 1** — approved neutral south anchor (identity)
- **Image 2** — pixel-grid reference: [`references/grids/alternating-pixels-1024.png`](../references/grids/alternating-pixels-1024.png)

## Prompt template

Run this once for `{DIRECTION}` = WEST, then again for NORTH.

```text
Intended use: directional anchor sprite for a top-down 2D game character.

Input images:
Image 1 is the approved south-facing identity anchor for {CHARACTER_NAME}. Preserve the same character identity, outfit, palette, proportions, silhouette, accessories, and high-resolution pixelated game-sprite style.
Image 2 is an alternating black/white pixel reference. Use it only as a pixel-texture and clean-background guide.

Primary request:
Create a new {OUTPUT_SIZE} {DIRECTION}-facing full-body anchor frame of the same character, facing {DIRECTION_DESCRIPTION}, in a neutral idle stance.

Pose and direction:
- The character should face {DIRECTION_DESCRIPTION} in a game-ready top-down view.
- Keep both feet visible and stable on the same baseline.
- Keep hands neutral.
- No magic/effects/action pose.
- Preserve readable direction-specific silhouette: {DIRECTIONAL_SILHOUETTE_DETAILS}.

Accessory placement:
- Keep existing accessories attached naturally to the side/hip/hand where appropriate.
- Do not move props to awkward positions just to make them visible.
- If a prop is awkward in this view, reduce its visibility rather than relocating it incorrectly.

Composition:
- Single centered character.
- Full body visible.
- Ample padding on all sides.
- Flat chroma background matching source-anchor style.
- No shadow, props, other characters, UI, or text.

Critical constraints:
- No dynamic attack effects.
- No glow, particles, projectile, aura, or flame.
- No weapon/staff/projectile unless it is part of the neutral identity.
- This is a neutral anchor for later walk, idle, and attack generation.

Style:
- High-resolution pixelated 2D game sprite.
- Crisp readable silhouette.
- Consistent with the south-facing anchor.
```

## Direction descriptions

- WEST: `facing left in profile, both feet visible, body in 3/4 left turn`
- NORTH: `facing away from the camera (back view), both feet visible`
- EAST: **Don't generate.** Horizontally flip your west anchor in any image editor.

## Common pitfall: prop on the wrong side

When generating the north (back-facing) anchor, props the character carries (book, satchel, weapon) often end up centered on the back or floating. Specify in `{DIRECTIONAL_SILHOUETTE_DETAILS}` that the prop stays at the side/hip — or regenerate.

## Next step

→ [05 — Walk Cycle (image-to-video)](05-walk-cycle-i2v.md)
