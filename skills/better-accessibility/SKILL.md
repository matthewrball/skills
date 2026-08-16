---
name: better-accessibility
description: >-
  Use when building or reviewing UI components, modals, menus, forms, or custom
  widgets, or when the user says make this accessible or reports keyboard or
  screen-reader issues. Triggers on a11y, WCAG, ARIA, focus, keyboard
  navigation, screen reader, hit area, prefers-reduced-motion.
---
# Better Accessibility

Accessibility is the floor for interface craft. Prefer native elements over ARIA. Walk the UI as keyboard-only, then as a screen reader.

Core rules: native elements first; style `:focus-visible`; full keyboard support (APG); trap and restore focus in modals; 24×24px minimum hit area (44×44 touch); label every control; errors announce with aria-invalid; icon-only buttons need aria-label; don't rely on color alone; honor prefers-reduced-motion; announce dynamic content; alt text by purpose; real heading/landmark structure.

Color contrast → better-colors. Text sizing → better-typography. RTL layout → better-layout.

When reviewing, load sibling refs in `/workspace/user-skills/better-accessibility/` (focus-and-keyboard, semantics-and-aria, forms, screen-readers, hit-areas, motion-and-zoom).
