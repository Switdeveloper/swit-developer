# Swit Developer Design System

**Version:** 1.0  
**Last Updated:** April 24, 2026  
**Sources:** Linear (minimal dark), Vercel (developer-focused), 21st.dev (AI components)

---

## Table of Contents

1. [Design Philosophy](#design-philosophy)
2. [Color Palette](#color-palette)
3. [Typography](#typography)
4. [Components](#components)
5. [21st.dev Integration](#21stdev-integration)
6. [Animation Guidelines](#animation-guidelines)
7. [Responsive Breakpoints](#responsive-breakpoints)

---

## Design Philosophy

### Core Principles

1. **Dark First** - Professional, developer-centric aesthetic
2. **Cyan Accent** - Brand color (#00d4ff) for CTAs and highlights
3. **AI-Ready** - Components designed for AI/agent interfaces (inspired by 21st.dev)
4. **Minimal & Clean** - No clutter, purposeful whitespace
5. **Developer Focused** - Code-friendly, technical aesthetic

### Visual Identity

**Swit Developer** combines:
- **Professional corporate** trust (like a2 insurance site)
- **Developer tool** precision (like Vercel/Linear)
- **AI/Agent** modernity (like 21st.dev components)

---

## Color Palette

### Primary Colors

| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `--bg-dark` | `#0f172a` | 15, 23, 42 | Main background |
| `--bg-darker` | `#0a0f1c` | 10, 15, 28 | Sections, cards |
| `--bg-card` | `#ffffff05` | 255,255,255,5% | Card backgrounds |
| `--brand-cyan` | `#00d4ff` | 0, 212, 255 | Primary accent, CTAs |
| `--brand-purple` | `#7c3aed` | 124, 58, 237 | Secondary accent |

### Extended Palette (21st.dev Inspired)

| Token | Hex | Usage |
|-------|-----|-------|
| `--ai-blue` | `#3b82f6` | AI chat bubbles |
| `--ai-purple` | `#8b5cf6` | Agent indicators |
| `--ai-green` | `#10b981` | Success states |
| `--ai-pink` | `#ec4899` | Highlights |
| `--border-subtle` | `#ffffff10` | Card borders |
| `--border-hover` | `#00d4ff30` | Hover states |
| `--text-primary` | `#ffffff` | Headings |
| `--text-secondary` | `#ffffffb3` | Body (70% opacity) |
| `--text-muted` | `#ffffff60` | Captions (40% opacity) |

### Gradient Patterns

```css
/* Hero Gradient */
background: radial-gradient(ellipse at top, rgba(0, 212, 255, 0.15) 0%, transparent 50%),
            radial-gradient(ellipse at bottom, rgba(124, 58, 237, 0.1) 0%, transparent 50%),
            #0f172a;

/* Button Gradient */
background: linear-gradient(135deg, #00d4ff 0%, #3b82f6 100%);

/* Card Gradient Hover (21st.dev style) */
background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(124, 58, 237, 0.1) 100%);
```

---

## Typography

### Font Families

```css
--font-heading: 'Playfair Display', serif;  /* Elegant, professional */
--font-body: 'Inter', sans-serif;            /* Clean, modern */
--font-mono: 'JetBrains Mono', monospace;    /* Code elements */
```

### Type Scale

| Level | Size | Weight | Usage |
|-------|------|--------|-------|
| H1 | 56px / 3.5rem | 700 | Page titles |
| H2 | 40px / 2.5rem | 600 | Section headings |
| H3 | 24px / 1.5rem | 600 | Card titles |
| Body | 16px / 1rem | 400 | Paragraphs |
| Small | 14px / 0.875rem | 400 | Captions |
| Tiny | 12px / 0.75rem | 500 | Labels, badges |

### Typography Patterns

**Hero Headings:**
```css
font-family: 'Playfair Display', serif;
font-size: 56px;
font-weight: 700;
line-height: 1.1;
letter-spacing: -0.02em;
```

**Gradient Text (Brand):**
```css
background: linear-gradient(135deg, #00d4ff 0%, #7c3aed 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```

---

## Components

### 1. Cards

**Service Card (Current):**
```css
.service-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 32px;
  transition: all 0.3s ease;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 212, 255, 0.1);
}
```

**21st.dev Enhanced Card:**
```css
.ai-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  position: relative;
  overflow: hidden;
}

.ai-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(124, 58, 237, 0.1) 100%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.ai-card:hover::before {
  opacity: 1;
}
```

### 2. Buttons

**Primary Button:**
```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  padding: 16px 32px;
  background: linear-gradient(135deg, #00d4ff 0%, #3b82f6 100%);
  color: white;
  font-weight: 600;
  border-radius: 9999px;
  border: none;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
}
```

**Ghost Button (21st.dev style):**
```css
.btn-ghost {
  padding: 12px 24px;
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: 9999px;
  transition: all 0.3s ease;
}

.btn-ghost:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
}
```

### 3. Navigation (Mega Menu)

**Structure:**
- Fixed top header with backdrop blur
- 4-column mega menu dropdown
- Cyan accent on hover
- Mobile hamburger with slide-down menu

**21st.dev Additions:**
- Search bar with AI-style input
- Component badges (like "Popular", "New")
- Author attribution

### 4. AI Chat Components (from 21st.dev)

**AI Input Box:**
```html
<div class="ai-input-container">
  <div class="ai-input-wrapper">
    <textarea 
      class="ai-input" 
      placeholder="Ask about our services..."
      rows="1"
    ></textarea>
    <button class="ai-submit">
      <svg><!-- send icon --></svg>
    </button>
  </div>
  <div class="ai-suggestions">
    <button class="ai-chip">Shopify</button>
    <button class="ai-chip">WordPress</button>
    <button class="ai-chip">AI Automation</button>
  </div>
</div>
```

```css
.ai-input-container {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 16px;
}

.ai-input {
  width: 100%;
  background: transparent;
  border: none;
  color: white;
  resize: none;
  outline: none;
}

.ai-chip {
  padding: 6px 12px;
  background: rgba(0, 212, 255, 0.1);
  border: 1px solid rgba(0, 212, 255, 0.3);
  color: #00d4ff;
  border-radius: 9999px;
  font-size: 12px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.ai-chip:hover {
  background: rgba(0, 212, 255, 0.2);
}
```

### 5. Component Gallery (21st.dev Pattern)

**Card Grid with Stats:**
```html
<div class="component-grid">
  <div class="component-card">
    <img src="preview.png" alt="Component preview">
    <div class="component-meta">
      <h3>AI Prompt Box</h3>
      <div class="author">
        <img src="avatar.png" class="avatar">
        <span>@easemize</span>
      </div>
      <div class="stats">
        <span>275 views</span>
        <span>98% rating</span>
      </div>
    </div>
  </div>
</div>
```

---

## 21st.dev Integration

### Key Elements to Add

1. **AI Chat Interface**
   - Input box with suggestions
   - Message bubbles (user/assistant)
   - Typing indicators
   - Quick action chips

2. **Component Showcase**
   - Gallery grid with hover previews
   - View counts and ratings
   - Author attribution

3. **Agent Plan Display**
   - Step-by-step process visualization
   - Progress indicators
   - Status badges

4. **Code Blocks with Syntax Highlighting**
   ```
   ```javascript
   // Example service configuration
   const shopifyStore = {
     theme: 'custom',
     plugins: ['analytics', 'seo'],
     optimize: true
   };
   ```
   ```

### Implementation Priority

**High Priority:**
- [ ] AI chat input component on contact page
- [ ] Component gallery for services
- [ ] Hover effects on cards (gradient reveal)

**Medium Priority:**
- [ ] Agent plan visualization
- [ ] Code block components
- [ ] Author badges

**Low Priority:**
- [ ] Live component previews
- [ ] Interactive demos

---

## Animation Guidelines

### Entrance Animations

```css
/* Fade Up (Primary) */
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-up {
  animation: fadeUp 0.6s ease-out forwards;
}

/* Stagger delay for lists */
.fade-up:nth-child(1) { animation-delay: 0s; }
.fade-up:nth-child(2) { animation-delay: 0.1s; }
.fade-up:nth-child(3) { animation-delay: 0.2s; }
```

### Hover Effects

```css
/* Card lift */
.card:hover {
  transform: translateY(-8px);
  transition: transform 0.3s ease;
}

/* Glow effect (21st.dev style) */
.card:hover {
  box-shadow: 0 0 40px rgba(0, 212, 255, 0.15);
}

/* Gradient border reveal */
.card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  padding: 1px;
  background: linear-gradient(135deg, #00d4ff, #7c3aed);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.card:hover::before {
  opacity: 1;
}
```

### Counter Animation

```javascript
// Intersection Observer triggers counting
// Duration: 2000ms
// Easing: ease-out cubic
// Format: Number + suffix (150+, 98%)
```

---

## Responsive Breakpoints

| Breakpoint | Width | Adjustments |
|------------|-------|-------------|
| Mobile | < 640px | Single column, stacked nav |
| Tablet | 640-1024px | 2 columns, simplified menu |
| Desktop | 1024-1280px | Full layout |
| Wide | > 1280px | Max-width containers |

### Mobile Navigation

- Hamburger menu
- Slide-down panel
- Stacked service links
- Simplified mega menu

---

## Usage Guidelines

### Do's ✅

- Use gradient text for key headings only
- Maintain consistent spacing (8px grid)
- Use backdrop-blur for floating elements
- Add hover states to all interactive elements
- Include loading states for async actions

### Don'ts ❌

- Don't use pure black (#000000)
- Don't use more than 2 accent colors together
- Don't make text smaller than 12px
- Don't use borders without rounded corners
- Don't forget focus states for accessibility

---

## Quick Reference

### Spacing Scale

```css
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-6: 24px;
--space-8: 32px;
--space-12: 48px;
--space-16: 64px;
--space-24: 96px;
```

### Border Radius

```css
--radius-sm: 8px;    /* Buttons, inputs */
--radius-md: 12px;   /* Cards */
--radius-lg: 16px;   /* Modals, sections */
--radius-xl: 24px;   /* Hero elements */
--radius-full: 9999px; /* Pills, avatars */
```

### Shadows

```css
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.1);
--shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
--shadow-lg: 0 10px 30px rgba(0, 0, 0, 0.2);
--shadow-glow: 0 0 40px rgba(0, 212, 255, 0.15);
```

---

**Next Steps:**
1. Review design with stakeholders
2. Prioritize 21st.dev component additions
3. Create component library
4. Implement responsive variations
5. Add animation polish

**Questions?** Refer to:
- 21st.dev for component inspiration
- Linear.app for minimal UI patterns
- Vercel.com for developer-focused UX
