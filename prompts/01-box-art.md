# 01 — Box Art

Generate the initial high-resolution identity image for your character. This is **vibe/silhouette reference only** — never feed it directly into sprite generation.

![Box art example](../references/anchors/01-box-art.png)

## When to use

- You're starting a new character from scratch
- You want a visual anchor for color palette, silhouette, prop, and personality
- You'll use it for character-select screens later

## Inputs

- Text prompt only (no image references at this stage)
- Tool: GPT Image 2.0 / Nano Banana 2 / your favorite image model

## Prompt template

```text
Create a high-resolution character box-art portrait for {CHARACTER_NAME}, a {CHARACTER_ARCHETYPE}, for a top-down 2D battle game.

Format:
- 1024x1536 PNG
- 2:3 portrait
- full-body or near full-body 3/4 hero composition
- painterly illustration with strong silhouette logic that can later translate into pixel/game sprites

Character:
- {CORE_IDENTITY}
- {COSTUME_AND_COLOR_PALETTE}
- {SIGNATURE_PROP}
- {PERSONALITY_OR_POSE}

World/background:
- {CHARACTER_SPECIFIC_BIOME}
- same world language as the rest of the roster
- background supports the character, but does not overpower them

Avoid:
- text, logos, UI, watermark
- symbols/runes/glyphs unless explicitly part of the design
- background motifs that belong to another character
```

## Notes from the wizard run

The wizard's first box art had arcane runes baked into the robe, hat, book, and stones. A second pass explicitly removing all runes/symbols gave a much cleaner final.

## Next step

→ [02 — South Anchor](02-south-anchor.md)
