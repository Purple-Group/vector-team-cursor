# Persuasive Design (Ethical)

Ethical persuasion techniques and nudge patterns.

## Ethical Persuasion Techniques

| Technique | Ethical Use | Dark Pattern (Avoid) |
|-----------|-------------|----------------------|
| **Scarcity** | Real stock levels | Fake countdown timers |
| **Social Proof** | Genuine reviews | Fake testimonials |
| **Authority** | Real credentials | Misleading badges |
| **Urgency** | Real deadlines | Manufactured FOMO |
| **Commitment** | Progress saving | Guilt-tripping |

## Nudge Patterns

**Smart Defaults:**
```html
<input type="radio" name="plan" value="annual" checked>
  Annual (Save 20%)
```

**Anchoring:**
```html
<div class="price">
  <span class="original">$99</span>
  <span class="current">$79</span>
  <span class="savings">Save 20%</span>
</div>
```

**Social Proof:**
```html
<div class="activity">
  <span>Sarah from NYC just purchased</span>
</div>
<p>Join 50,000+ designers who use our tool</p>
```

**Progress & Commitment:**
```html
<div class="progress">
  <div class="progress-bar" style="width: 60%"></div>
  <span>60% complete - almost there!</span>
</div>
```
