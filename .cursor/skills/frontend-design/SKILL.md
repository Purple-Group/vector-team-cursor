---
name: frontend-design
description: Design thinking and decision-making for web UI. Use when designing components, layouts, color schemes, typography, or creating aesthetic interfaces. Teaches principles, not fixed values.
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

# Frontend Design System

> **Philosophy:** Every pixel has purpose. Restraint is luxury. User psychology drives decisions.  
> **Core Principle:** THINK, don't memorize. ASK, don't assume.

## 🎯 Selective Reading Rule

**REQUIRED:** [ux-psychology.md](ux-psychology.md) - Index (read first, then specific modules as needed)  
**UX Modules:** [ux-laws.md](ux-laws.md), [emotional-design.md](emotional-design.md), [trust-building.md](trust-building.md), [cognitive-load.md](cognitive-load.md), [persuasive-design.md](persuasive-design.md), [user-personas.md](user-personas.md)  
**OPTIONAL:** color-system.md, typography-system.md, visual-effects.md, animation-guide.md, motion-graphics.md, decision-trees.md (only if relevant)

**Runtime:** `python scripts/ux_audit.py <project_path>` for UX audits

## ⚠️ CRITICAL: ASK BEFORE ASSUMING

**If vague, ASK:** Color? Style? Layout? Don't default to AI favorites.

**Avoid:** Bento grids, hero split layouts, mesh/aurora gradients, glassmorphism, deep cyan/fintech blue, rounded everything, dark+neon defaults, generic copywriting

## 1. Constraint Analysis (ALWAYS FIRST)

Ask/answer: Timeline, Content, Brand, Tech, Audience

**Audience → Design:** Gen Z (bold/fast/mobile), Millennials (clean/minimal), Gen X (familiar/trustworthy), Boomers (readable/high-contrast), B2B (professional/data-focused), Luxury (restrained/whitespace)

## 2. UX Psychology

**Core Laws:** Hick's (limit choices), Fitts' (size CTAs), Miller's (chunk into 7±2), Von Restorff (distinct CTAs), Serial Position (key info start/end)

**Emotional Design:** Visceral (first impression) → Behavioral (use) → Reflective (memory)

**Trust:** Security indicators, social proof, clear contact, consistent design, transparent policies

## 3. Layout Principles

**Golden Ratio (1.618):** Content:Sidebar ≈ 62:38, heading scale ×1.618, spacing progression

**8-Point Grid:** Spacing in multiples of 8 (4px micro, 8px small, 16px medium, 24-32px large, 48-80px XL)

**Sizing:** Touch targets min 44px, buttons by importance, inputs match buttons, cards consistent padding, reading width 45-75ch

## 4. Color Principles

**60-30-10 Rule:** 60% primary/background, 30% secondary, 10% accent

**Psychology:** Trust/calm (blue), Growth/nature (green), Energy/urgency (orange/red), Luxury/creativity (teal/gold/emerald), Clean/minimal (neutrals)

**Process:** Industry → Emotion → Light/dark mode → ASK USER if unclear

See [color-system.md](color-system.md) for details

## 5. Typography Principles

**Scale:** Dense UI (1.125-1.2), General web (1.25), Editorial (1.333), Hero/display (1.5-1.618)

**Pairing:** Contrast + harmony, display+neutral or serif+sans

**Readability:** Line length 45-75ch, line height 1.4-1.6, WCAG contrast, 16px+ body

See [typography-system.md](typography-system.md) for details

## 6. Visual Effects

**Glassmorphism:** Semi-transparent + backdrop blur + subtle border. ⚠️ Avoid standard blue/white cliché

**Shadows:** Higher = larger, Y-offset > X-offset, multiple layers, dark mode may need glow

**Gradients:** Adjacent colors or same hue different lightness. 🚫 NO mesh/aurora gradients

See [visual-effects.md](visual-effects.md) for details

## 7. Animation Principles

**Timing:** Based on distance, size, importance, context

**Easing:** Enter (ease-out), Leave (ease-in), Emphasis (ease-in-out), Playful (bounce)

**Performance:** Animate only transform/opacity, respect reduced-motion, test low-end devices

See [animation-guide.md](animation-guide.md), [motion-graphics.md](motion-graphics.md) for details

## 8. "Wow Factor" Checklist

**Premium:** Whitespace, subtle depth, smooth animations, attention to detail, cohesive rhythm, custom elements

**Trust:** Security cues, social proof, clear value, professional imagery, consistent language

**Emotional:** Hero emotion, human elements, progress indicators, moments of delight

## 9. Anti-Patterns

**Lazy:** Default fonts, stock imagery, inconsistent spacing, too many colors, text walls, poor contrast

**AI Tendencies:** Same colors, dark+neon defaults, purple everything (BAN), bento grids, mesh gradients, Vercel clones, not asking preferences

**Dark Patterns:** Hidden costs, fake urgency, forced actions, deceptive UI, confirmshaming

## 10. Decision Process

1. **CONSTRAINTS** → Timeline/brand/tech/audience (ASK if unclear)
2. **CONTENT** → What exists? Hierarchy?
3. **STYLE** → Appropriate for context (ASK if unclear, don't default)
4. **EXECUTION** → Apply principles, check anti-patterns
5. **REVIEW** → Serves user? Different from defaults? Proud of it?

## Reference Files

**UX Psychology (Modular):**
- [ux-psychology.md](ux-psychology.md) - Index/overview
- [ux-laws.md](ux-laws.md) - Core UX laws
- [emotional-design.md](emotional-design.md) - Three levels of processing
- [trust-building.md](trust-building.md) - Trust signals
- [cognitive-load.md](cognitive-load.md) - Load reduction
- [persuasive-design.md](persuasive-design.md) - Ethical persuasion
- [user-personas.md](user-personas.md) - Demographics & emotion mapping

**Design Systems:**
- [color-system.md](color-system.md) - Color theory
- [typography-system.md](typography-system.md) - Font pairing
- [visual-effects.md](visual-effects.md) - Effects principles
- [animation-guide.md](animation-guide.md) - Motion design
- [motion-graphics.md](motion-graphics.md) - Advanced motion
- [decision-trees.md](decision-trees.md) - Context templates

> **Remember:** Design is THINKING, not copying. Avoid the Modern SaaS Safe Harbor!
