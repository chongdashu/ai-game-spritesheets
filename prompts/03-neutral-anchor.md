# 03 — Neutral Anchor Reset

If your south anchor came out with a baked-in dynamic effect (fireball in hand, drawn weapon, casting glow), regenerate it neutral. **Anchors are boring on purpose.** Effects belong in the attack sheet only.

![Neutral south anchor](../references/anchors/03-neutral-south.png)

## When to use

- Your south anchor has a magic effect, charged weapon, or active pose
- You realize the effect would persist into idle/walk frames downstream

## Inputs

- **Text prompt** (template below)
- **Image 1** — pixel-grid reference: [`references/grids/alternating-pixels-1024.png`](../references/grids/alternating-pixels-1024.png)
- **Image 2** — your existing south anchor (identity reference)

## Why two image inputs

Using only the pixel grid loses identity (the character drifts). Using only the existing anchor loses the pixel-art discipline. **Both** preserves identity while keeping the chunky sprite feel.

## Prompt template

```text
Intended use: corrected reusable SOUTH-facing neutral idle anchor sprite for {CHARACTER_NAME}, a {ARCHETYPE} character in a top-down 2D game.

Image 1 role: pixel/grid anchor. Use it to preserve output discipline and pixelated sprite feel. Do not copy its content.
Image 2 role: identity anchor. Preserve this exact character identity, detail level, face, outfit, palette, prop, proportions, silhouette, and sprite scale.

Primary request:
Create {N} candidate variants of the same SOUTH-facing neutral idle anchor.
The only intended design correction from Image 2 is removing {DYNAMIC_EFFECT}.

Subject:
- {CHARACTER_NAME}, {ARCHETYPE}.
- Facing SOUTH, directly toward the camera.
- Same silhouette, outfit, palette, prop, face readability, and body scale as Image 2.
- {DYNAMIC_EFFECT_HAND_OR_BODY_PART} should be neutral and empty/resting naturally.

Preserve from Image 2:
- same face readability
- same silhouette and proportions
- same costume colors
- same prop size/detail
- same centered composition
- same high-resolution pixelated treatment

Change from Image 2:
- remove {DYNAMIC_EFFECT}
- remove glow, particles, smoke, aura, projectile, and charged action pose
- make the pose read as neutral idle

Background:
- solid uniform chroma background outside the character
- no gradients, noise, shadows, scenery, text, border, or UI

Avoid:
- redesigning the character
- simplifying key identity details
- changing scale or silhouette
- adding action effects
```

## Notes from the wizard run

- v1 had a purple fireball baked into the casting hand — would have persisted across all walk frames.
- Generating 4 variants and picking the cleanest one was faster than re-rolling singles.

## Next step

→ [04 — Directional Anchors](04-directional-anchors.md)
