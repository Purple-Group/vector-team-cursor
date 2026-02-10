# Emotional Design (Don Norman)

Three levels of user processing and how to design for each.

## Three Levels of Processing

**VISCERAL (Lizard Brain):** Immediate, automatic reaction. First impressions (50ms). Aesthetics: colors, shapes, imagery.

**BEHAVIORAL (Functional Brain):** Usability and function. Pleasure from effective use. Performance, reliability, ease.

**REFLECTIVE (Conscious Brain):** Conscious thought and meaning. Personal identity and values. Long-term memory and loyalty.

## Designing for Each Level

**Visceral:**
```css
.hero {
  background: linear-gradient(135deg, #0ea5e9 0%, #14b8a6 100%);
  color: white;
}

.button:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
}
```

**Behavioral:**
```javascript
button.onclick = () => {
  button.disabled = true;
  button.textContent = 'Saving...';
  save().then(() => showSuccess('Saved!'));
};
```

**Reflective:**
```html
<section class="about">
  <h2>Why We Exist</h2>
  <p>We believe technology should empower, not complicate...</p>
</section>

<blockquote>
  "This tool helped me become the designer I wanted to be."
</blockquote>
```
