---
name: better-colors
description: >-
  Use for OKLCH color work: convert hex/rgb/hsl, generate palettes, check
  contrast, handle gamut, theme with Tailwind v4, or apply color with meaning.
  Triggers on oklch, contrast, gamut, design tokens, dark mode colors.
---
# Better Colors

OKLCH is a perceptually uniform color space. Use it when the project already uses OKLCH, when creating a new color system, or when asked for conversion or palette work. Otherwise preserve existing tokens.

Write `oklch(L C H)` / `oklch(L C H / alpha)`. Measure contrast (APCA/WCAG), clamp gamut, one meaning per color. Do not convert notation just because this skill loaded.

Sibling refs: `/workspace/user-skills/better-colors/` (color-conversion, palette-generation, accessibility-contrast, gamut-and-tailwind, color-usage).
