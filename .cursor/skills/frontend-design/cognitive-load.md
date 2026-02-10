# Cognitive Load Management

Reduce mental effort required to use your interface.

## Three Types of Cognitive Load

| Type | Definition | Designer's Role |
|------|------------|-----------------|
| **Intrinsic** | Inherent complexity of task | Break into smaller steps |
| **Extraneous** | Load from poor design | Eliminate this! |
| **Germane** | Effort for learning | Support and encourage |

## Reduction Strategies

### 1. Simplify (Reduce Extraneous)
```css
.card-clean {
  background: white;
  border-radius: 16px;
  box-shadow: 0 10px 30px -10px rgba(0,0,0,0.1);
}
```

### 2. Chunk Information
```html
<form>
  <fieldset>
    <legend>Step 1: Personal Info</legend>
    <!-- 3-4 fields -->
  </fieldset>
  <fieldset>
    <legend>Step 2: Shipping</legend>
    <!-- 3-4 fields -->
  </fieldset>
</form>
```

### 3. Progressive Disclosure
```html
<div class="filters">
  <div class="filters-basic"><!-- Common filters --></div>
  <button onclick="toggleAdvanced()">Advanced Options ▼</button>
  <div class="filters-advanced" hidden><!-- Complex filters --></div>
</div>
```

### 4. Use Familiar Patterns
✅ Standard navigation placement  
✅ Expected icon meanings (🔍 = search)  
✅ Conventional form layouts  
✅ Common gesture patterns (swipe, pinch)

### 5. Offload Information
```html
<label>
  Card Number
  <input type="text" inputmode="numeric" 
         autocomplete="cc-number" 
         placeholder="1234 5678 9012 3456">
</label>

<div class="order-summary">
  <p>Shipping to: <strong>John Doe, 123 Main St...</strong></p>
  <a href="#">Edit</a>
</div>
```
