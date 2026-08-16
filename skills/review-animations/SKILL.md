---
name: review-animations
description: >-
  Use when reviewing animation and motion code against a high craft bar. Default
  to flagging; approval is earned. Does not write features or review non-motion
  code.
---
# Review Animations

One job: review motion code. Default to flagging.

Ten non-negotiables: justified motion, frequency-appropriate, responsive easing, sub-300ms UI, origin and physical correctness, interruptibility, GPU-only properties, accessibility, asymmetric enter/exit, cohesion.

Hard flags: `transition: all`, `scale(0)`, `ease-in` on UI, animation on keyboard/100+ day actions, duration > 300ms, centered popover origin, layout-property animation, missing reduced-motion.

Load `/workspace/user-skills/review-animations/STANDARDS.md` for precise values. Full recipe: `/workspace/user-skills/review-animations/SKILL.md`
