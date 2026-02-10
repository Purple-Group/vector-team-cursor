# Trust Building System

Trust signals and their strategic placement.

## Trust Signal Categories

| Category | Elements | Implementation |
|----------|----------|----------------|
| **Security** | SSL, badges, encryption | Visible padlock, security logos on forms |
| **Social Proof** | Reviews, testimonials, logos | Star ratings, customer photos, brand logos |
| **Transparency** | Policies, pricing, contact | Clear links, no hidden fees, real address |
| **Professional** | Design quality, consistency | No broken elements, consistent branding |
| **Authority** | Certifications, awards, media | "As seen in...", industry certifications |

## Trust Signal Placement

**Header:** Trust banner ("Free shipping | 30-day returns | Secure checkout")  
**Hero:** Social proof ("Trusted by 10,000+")  
**Product:** Reviews visible, security badges  
**Checkout:** Payment icons, SSL badge, guarantee  
**Footer:** Contact info, policies, certifications

## Trust-Building CSS Patterns

```css
.trust-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 16px;
  background: #F0FDF4;
  border-radius: 2px;
  font-size: 14px;
  color: #166534;
}

.secure-form::before {
  content: '🔒 Secure form';
  display: block;
  font-size: 12px;
  color: #166534;
  margin-bottom: 8px;
}

.testimonial {
  display: flex;
  gap: 16px;
  padding: 24px;
  background: white;
  border-radius: 16px;
  box-shadow: var(--shadow-sm);
}
```
