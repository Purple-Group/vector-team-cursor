# Core UX Laws

Essential psychological principles for interface design.

## Hick's Law

**Principle:** Decision time increases logarithmically with number of choices.

**Application:**
- Navigation: Max 5-7 top-level items
- Forms: Break into steps (progressive disclosure)
- Options: Default selections when possible
- Filters: Prioritize most-used, hide advanced

**Example:**
```
❌ Bad: 15 menu items in one nav
✅ Good: 5 main categories + "More" 

❌ Bad: 20 form fields at once
✅ Good: 3-step wizard with 5-7 fields each
```

## Fitts' Law

**Principle:** Time to reach target = function of distance and size.

**Application:**
- CTAs: Make primary buttons larger (min 44px height)
- Touch targets: 44×44px minimum on mobile
- Placement: Important actions near natural cursor position
- Corners: "Magic corners" (infinite edge = easy to hit)

**Button Sizing:**
```css
.btn-primary { height: 48px; padding: 0 24px; }
.btn-secondary { height: 40px; padding: 0 16px; }
.btn-tertiary { height: 36px; padding: 0 12px; }

@media (hover: none) {
  .btn { min-height: 44px; min-width: 44px; }
}
```

## Miller's Law

**Principle:** Average person can hold 7±2 chunks in working memory.

**Application:**
- Lists: Group into chunks of 5-7 items
- Navigation: Max 7 menu items
- Content: Break long content with headings
- Phone numbers: 555-123-4567 (chunked)

## Von Restorff Effect

**Principle:** Items that stand out are more likely to be remembered.

**Application:**
- CTA buttons: Distinct color from other elements
- Pricing: Highlight recommended plan
- Important info: Visual differentiation
- New features: Badge or callout

## Serial Position Effect

**Principle:** Items at beginning (primacy) and end (recency) remembered best.

**Application:**
- Navigation: Most important items first and last
- Lists: Key info at top and bottom
- Forms: Most critical fields at start
- CTAs: Repeat at top and bottom of long pages
