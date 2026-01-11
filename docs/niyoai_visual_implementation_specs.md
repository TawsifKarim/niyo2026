# NIYO AI — VISUAL IMPLEMENTATION SPECS & TECHNICAL GUIDE

> **Purpose:** Technical specifications for designers and developers. Exact measurements, animations, responsive breakpoints, and component details.

---

## TABLE OF CONTENTS

1. [Design System Fundamentals](#design-system-fundamentals)
2. [Hero Section Layout](#hero-section-layout)
3. [Section-by-Section Specs](#section-by-section-specs)
4. [Animation & Motion Guidelines](#animation--motion-guidelines)
5. [Responsive Breakpoints](#responsive-breakpoints)
6. [Component Library](#component-library)
7. [Performance Optimization](#performance-optimization)

---

## DESIGN SYSTEM FUNDAMENTALS

### Color Palette

```css
/* Primary Colors */
--niyo-primary: #2563EB;      /* Blue - trust, confidence */
--niyo-primary-dark: #1E40AF;
--niyo-primary-light: #60A5FA;

/* Semantic Colors */
--niyo-success: #10B981;      /* Green - positive outcomes */
--niyo-warning: #F59E0B;      /* Orange - attention */
--niyo-danger: #EF4444;       /* Red - pain points, urgency */

/* Neutrals */
--niyo-black: #0F172A;        /* Text primary */
--niyo-gray-900: #1E293B;     /* Text secondary */
--niyo-gray-700: #334155;     /* Text tertiary */
--niyo-gray-500: #64748B;     /* Text muted */
--niyo-gray-300: #CBD5E1;     /* Borders */
--niyo-gray-100: #F1F5F9;     /* Backgrounds */
--niyo-white: #FFFFFF;

/* State Colors - Problem Sections */
--niyo-chaos-red: #DC2626;    /* Pain sections background tint */
--niyo-chaos-overlay: rgba(220, 38, 38, 0.05);

/* State Colors - Solution Sections */
--niyo-clarity-blue: #3B82F6;
--niyo-clarity-overlay: rgba(59, 130, 246, 0.03);

/* Accent - Social Proof & Success */
--niyo-gold: #F59E0B;
--niyo-gold-light: #FCD34D;
```

---

### Typography

```css
/* Font Stack */
--font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-mono: 'JetBrains Mono', 'Fira Code', 'Courier New', monospace;

/* Font Sizes - Desktop */
--text-hero: 72px;           /* Main headlines */
--text-h1: 48px;             /* Section headlines */
--text-h2: 36px;             /* Subsection headlines */
--text-h3: 24px;             /* Component headlines */
--text-body-lg: 20px;        /* Lead paragraphs */
--text-body: 18px;           /* Body text */
--text-body-sm: 16px;        /* Supporting text */
--text-caption: 14px;        /* Captions, labels */
--text-stat: 64px;           /* Large stat numbers */

/* Font Weights */
--weight-regular: 400;
--weight-medium: 500;
--weight-semibold: 600;
--weight-bold: 700;
--weight-extrabold: 800;

/* Line Heights */
--leading-tight: 1.1;        /* Headlines */
--leading-snug: 1.3;         /* Subheadlines */
--leading-normal: 1.6;       /* Body text (readability) */
--leading-relaxed: 1.8;      /* Long-form content */

/* Letter Spacing */
--tracking-tight: -0.02em;   /* Large headlines */
--tracking-normal: 0;
--tracking-wide: 0.05em;     /* All-caps labels */
```

---

### Spacing System (8px base grid)

```css
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
--space-20: 80px;
--space-24: 96px;
--space-32: 128px;
--space-40: 160px;

/* Section Padding */
--section-padding-y: var(--space-32);  /* Desktop: 128px */
--section-padding-y-mobile: var(--space-20);  /* Mobile: 80px */
```

---

### Border Radius

```css
--radius-sm: 4px;    /* Small elements */
--radius-md: 8px;    /* Cards, buttons */
--radius-lg: 12px;   /* Large cards */
--radius-xl: 16px;   /* Hero cards */
--radius-2xl: 24px;  /* Feature sections */
--radius-full: 9999px; /* Pills, badges */
```

---

### Shadows

```css
--shadow-xs: 0 1px 2px rgba(0, 0, 0, 0.05);
--shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.1), 0 1px 2px rgba(0, 0, 0, 0.06);
--shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
--shadow-2xl: 0 25px 50px -12px rgba(0, 0, 0, 0.25);

/* Interactive Shadows */
--shadow-button-hover: 0 4px 12px rgba(37, 99, 235, 0.3);
--shadow-card-hover: 0 12px 24px rgba(0, 0, 0, 0.12);
```

---

## HERO SECTION LAYOUT

### Desktop Layout (1440px viewport)

```
┌─────────────────────────────────────────────────────────────┐
│                        NAVIGATION                           │
│  Logo    How It Works  |  Why ChatGPT?  |  Pricing  [CTA]  │ 60px height
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                        80px top padding                     │
│                                                             │
│  ┌───────────────────────────────────────────────────────┐ │
│  │                                                       │ │
│  │  EYEBROW (optional): "Used by 500+ teams"            │ │ 14px, gray-500, uppercase
│  │                                                       │ │
│  │  HEADLINE:                                            │ │ 72px, bold, black
│  │  Your Next Great Hire Is Buried                      │ │ Max-width: 800px
│  │  Under 847 Unread CVs                                │ │ Leading: 1.1
│  │                                                       │ │
│  │  SUBHEADLINE:                                         │ │ 24px, gray-700
│  │  Niyo finds them in 47 seconds.                      │ │ 20px margin-top
│  │                                                       │ │
│  │  ┌─────────────────────────────┐                     │ │
│  │  │  PRIMARY CTA BUTTON         │                     │ │ 32px margin-top
│  │  │  See Your Shortlist Now     │                     │ │ 56px height, large
│  │  └─────────────────────────────┘                     │ │
│  │                                                       │ │
│  │  Trust line: No credit card • Upload real CVs        │ │ 12px margin-top, 16px, gray-500
│  │                                                       │ │
│  │  ┌────────────────────────────────────────────────┐  │ │
│  │  │ STAT BAR (4 columns)                          │  │ │ 40px margin-top
│  │  │ ✓ 94% accuracy  •  ✓ 3.8x faster  •  ✓ 500+  │  │ │ Light background
│  │  └────────────────────────────────────────────────┘  │ │
│  │                                                       │ │
│  └───────────────────────────────────────────────────────┘ │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │                                                     │   │
│  │         HERO VISUAL / DEMO                          │   │ 600px height
│  │         (Split screen or animated dashboard)        │   │
│  │                                                     │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│                        80px bottom padding                  │
└─────────────────────────────────────────────────────────────┘

Total Hero Height: ~900px viewport height (full screen on desktop)
```

---

### Hero Section CSS

```css
.hero-section {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background: linear-gradient(
    180deg,
    var(--niyo-white) 0%,
    var(--niyo-gray-100) 100%
  );
  padding: var(--space-20) var(--space-6);
}

.hero-content {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.hero-eyebrow {
  font-size: var(--text-caption);
  font-weight: var(--weight-semibold);
  color: var(--niyo-gray-500);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wide);
  margin-bottom: var(--space-4);
}

.hero-headline {
  font-size: var(--text-hero);
  font-weight: var(--weight-extrabold);
  color: var(--niyo-black);
  line-height: var(--leading-tight);
  letter-spacing: var(--tracking-tight);
  max-width: 800px;
  margin: 0 auto;
}

.hero-headline strong {
  color: var(--niyo-primary);
}

.hero-subheadline {
  font-size: var(--text-h3);
  font-weight: var(--weight-medium);
  color: var(--niyo-gray-700);
  line-height: var(--leading-snug);
  max-width: 600px;
  margin: var(--space-5) auto 0;
}

.hero-cta-wrapper {
  margin-top: var(--space-8);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-3);
}

.hero-trust-line {
  font-size: var(--text-body-sm);
  color: var(--niyo-gray-500);
  display: flex;
  align-items: center;
  gap: var(--space-3);
}

.hero-trust-line::before,
.hero-trust-line::after {
  content: '•';
  color: var(--niyo-gray-300);
}

.hero-stat-bar {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-8);
  margin-top: var(--space-10);
  padding: var(--space-6);
  background: rgba(37, 99, 235, 0.03);
  border-radius: var(--radius-lg);
  border: 1px solid var(--niyo-gray-300);
}

.hero-stat-item {
  display: flex;
  align-items: center;
  gap: var(--space-2);
  font-size: var(--text-body-sm);
  color: var(--niyo-gray-700);
}

.hero-stat-item::before {
  content: '✓';
  color: var(--niyo-success);
  font-weight: var(--weight-bold);
}

.hero-visual {
  margin-top: var(--space-16);
  border-radius: var(--radius-2xl);
  overflow: hidden;
  box-shadow: var(--shadow-2xl);
}
```

---

## PRIMARY CTA BUTTON SPECS

```css
.btn-primary {
  /* Size */
  height: 56px;
  padding: 0 var(--space-8);
  min-width: 240px;

  /* Typography */
  font-size: var(--text-body);
  font-weight: var(--weight-semibold);

  /* Colors */
  background: var(--niyo-primary);
  color: var(--niyo-white);

  /* Border */
  border: none;
  border-radius: var(--radius-md);

  /* Shadow */
  box-shadow: var(--shadow-md);

  /* Interaction */
  cursor: pointer;
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.btn-primary:hover {
  background: var(--niyo-primary-dark);
  box-shadow: var(--shadow-button-hover);
  transform: translateY(-2px);
}

.btn-primary:active {
  transform: translateY(0);
  box-shadow: var(--shadow-sm);
}

/* Pulsing animation for high-priority CTAs */
@keyframes pulse-glow {
  0%, 100% {
    box-shadow: 0 0 0 0 rgba(37, 99, 235, 0.7);
  }
  50% {
    box-shadow: 0 0 0 10px rgba(37, 99, 235, 0);
  }
}

.btn-primary.pulse {
  animation: pulse-glow 2s infinite;
}
```

---

## SECTION 2: THE VILLAIN (Pain Section)

### Layout Specs

```
┌─────────────────────────────────────────────────────────────┐
│                    SECTION BACKGROUND                       │
│           background: rgba(220, 38, 38, 0.03)              │ Subtle red tint
│                  128px padding top/bottom                   │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  HEADLINE (centered):                                       │ 48px, bold, black
│  Six Weeks. Three Hundred CVs. Still No Hire.              │ Max-width: 700px
│                                                             │
│  SUBHEADLINE (centered):                                    │ 24px, gray-700
│  You're not slow. The system is broken.                    │ 24px margin-top
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │                                                     │   │
│  │  PAIN POINTS (Left-aligned list):                  │   │ 20px body text
│  │  → Your best candidates accept other offers        │   │ 16px spacing
│  │  → Recruiters burn out on unqualified apps         │   │ Red arrow icon
│  │  → Hiring managers lose faith in the process       │   │
│  │  → Competitor's new hire is already shipping       │   │
│  │                                                     │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  ┌───────────────────────────────────────────────────────┐ │
│  │                                                       │ │
│  │   VISUAL PAIN GRID (6 images, 2x3 grid)             │ │ Each: 300x200px
│  │   [Exhausted recruiter] [Email inbox hell]          │ │ 24px gap
│  │   [Spreadsheet chaos]   [ChatGPT tabs]              │ │ Grayscale filter
│  │   [Calendar mess]       [Empty desk]                │ │ Red overlay
│  │                                                       │ │
│  └───────────────────────────────────────────────────────┘ │
│                                                             │
│  TRANSITION LINE (centered):                                │ 24px, primary color
│  There's a better way. And it takes 47 seconds.            │ Semibold
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

### CSS Implementation

```css
.section-villain {
  background: var(--niyo-chaos-overlay);
  border-top: 3px solid var(--niyo-danger);
  padding: var(--section-padding-y) var(--space-6);
  text-align: center;
}

.pain-points-list {
  max-width: 600px;
  margin: var(--space-12) auto;
  text-align: left;
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
}

.pain-point {
  display: flex;
  align-items: flex-start;
  gap: var(--space-3);
  font-size: var(--text-body);
  color: var(--niyo-gray-900);
}

.pain-point::before {
  content: '→';
  color: var(--niyo-danger);
  font-size: 24px;
  flex-shrink: 0;
}

.pain-visual-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-6);
  max-width: 1000px;
  margin: var(--space-16) auto;
}

.pain-visual-card {
  aspect-ratio: 3/2;
  border-radius: var(--radius-lg);
  overflow: hidden;
  position: relative;
  filter: grayscale(0.5);
  transition: filter 0.3s ease;
}

.pain-visual-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: rgba(220, 38, 38, 0.1);
  mix-blend-mode: multiply;
}

.pain-visual-card:hover {
  filter: grayscale(0);
}

.transition-line {
  font-size: var(--text-h3);
  font-weight: var(--weight-semibold);
  color: var(--niyo-primary);
  margin-top: var(--space-16);
}
```

---

## SECTION 3: THE REVELATION (Solution Intro)

### Three-Panel Transformation Visual

```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│  HEADLINE (centered): What If Your Perfect Shortlist      │ 48px, bold
│                       Appeared in 47 Seconds?             │
│                                                            │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐         │
│  │  PANEL 1   │  │  PANEL 2   │  │  PANEL 3   │         │ Each: 360px wide
│  │            │  │            │  │            │         │       400px tall
│  │  CHAOS     │→ │   NIYO     │→ │   HIRED    │         │
│  │            │  │            │  │            │         │
│  │ [messy     │  │ [clean     │  │ [team      │         │
│  │  desk]     │  │  dash]     │  │  celebration]│         │
│  │            │  │            │  │            │         │
│  │ "40+ hrs"  │  │ "47 sec"   │  │ "Focused"  │         │ Label below
│  └────────────┘  └────────────┘  └────────────┘         │
│                                                            │
│  ┌──────────────────────────────────────────────────────┐ │
│  │  STAT GRID (4 columns)                              │ │
│  │  47 sec     94%         3.8x        $47K            │ │ 64px numbers
│  │  shortlist  accuracy    faster      saved           │ │ 14px labels
│  └──────────────────────────────────────────────────────┘ │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

---

### CSS Implementation

```css
.section-revelation {
  background: linear-gradient(
    180deg,
    var(--niyo-white) 0%,
    var(--niyo-clarity-overlay) 50%,
    var(--niyo-white) 100%
  );
  padding: var(--section-padding-y) var(--space-6);
}

.transformation-panels {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-8);
  max-width: 1200px;
  margin: var(--space-16) auto;
  position: relative;
}

/* Arrow between panels */
.transformation-panels::before,
.transformation-panels::after {
  content: '→';
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 48px;
  color: var(--niyo-primary);
  font-weight: var(--weight-bold);
}

.transformation-panels::before {
  left: 32%;
}

.transformation-panels::after {
  right: 32%;
}

.transformation-panel {
  background: var(--niyo-white);
  border-radius: var(--radius-xl);
  padding: var(--space-6);
  box-shadow: var(--shadow-lg);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.transformation-panel:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-card-hover);
}

.panel-visual {
  aspect-ratio: 4/3;
  border-radius: var(--radius-md);
  overflow: hidden;
  margin-bottom: var(--space-4);
}

.panel-label {
  font-size: var(--text-body);
  font-weight: var(--weight-semibold);
  color: var(--niyo-gray-700);
  text-align: center;
}

/* Stat Grid */
.stat-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: var(--space-8);
  max-width: 1000px;
  margin: var(--space-20) auto 0;
  padding: var(--space-10) var(--space-6);
  background: var(--niyo-gray-100);
  border-radius: var(--radius-lg);
}

.stat-item {
  text-align: center;
}

.stat-number {
  font-size: var(--text-stat);
  font-weight: var(--weight-extrabold);
  color: var(--niyo-primary);
  line-height: 1;
  display: block;
}

.stat-label {
  font-size: var(--text-caption);
  color: var(--niyo-gray-500);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wide);
  margin-top: var(--space-2);
  display: block;
}
```

---

## ANIMATION & MOTION GUIDELINES

### Counter Animation (for stats)

```javascript
// Counter animation from 0 to target value
function animateCounter(element, targetValue, duration = 2000) {
  const start = 0;
  const increment = targetValue / (duration / 16); // 60fps
  let current = start;

  const timer = setInterval(() => {
    current += increment;
    if (current >= targetValue) {
      element.textContent = targetValue;
      clearInterval(timer);
    } else {
      element.textContent = Math.floor(current);
    }
  }, 16);
}

// Trigger when element enters viewport
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const target = entry.target.dataset.target;
      animateCounter(entry.target, target);
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.5 });
```

---

### Fade-In-Up Animation

```css
@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-on-scroll {
  opacity: 0;
  animation: fade-in-up 0.6s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

/* Stagger children */
.stagger-children > * {
  opacity: 0;
}

.stagger-children.in-view > *:nth-child(1) { animation-delay: 0.1s; }
.stagger-children.in-view > *:nth-child(2) { animation-delay: 0.2s; }
.stagger-children.in-view > *:nth-child(3) { animation-delay: 0.3s; }
.stagger-children.in-view > *:nth-child(4) { animation-delay: 0.4s; }
```

---

### Scroll-Triggered Parallax

```css
.parallax-element {
  will-change: transform;
  transition: transform 0.1s linear;
}

/* JavaScript */
window.addEventListener('scroll', () => {
  const scrolled = window.pageYOffset;
  const parallaxElements = document.querySelectorAll('.parallax-element');

  parallaxElements.forEach(el => {
    const speed = el.dataset.speed || 0.5;
    const yPos = -(scrolled * speed);
    el.style.transform = `translateY(${yPos}px)`;
  });
});
```

---

## RESPONSIVE BREAKPOINTS

```css
/* Mobile First Approach */
:root {
  /* Base (Mobile): 0-639px */

  /* SM: 640px */
  --breakpoint-sm: 640px;

  /* MD: 768px */
  --breakpoint-md: 768px;

  /* LG: 1024px */
  --breakpoint-lg: 1024px;

  /* XL: 1280px */
  --breakpoint-xl: 1280px;

  /* 2XL: 1536px */
  --breakpoint-2xl: 1536px;
}

/* Mobile (default) */
.hero-headline {
  font-size: 36px;
}

/* Tablet */
@media (min-width: 768px) {
  .hero-headline {
    font-size: 56px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .hero-headline {
    font-size: 72px;
  }
}

/* Mobile: Stack everything */
@media (max-width: 767px) {
  .transformation-panels {
    grid-template-columns: 1fr;
    gap: var(--space-6);
  }

  .stat-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .pain-visual-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

---

## COMPONENT LIBRARY

### Comparison Table Component

```html
<div class="comparison-table">
  <table>
    <thead>
      <tr>
        <th>What Hiring Requires</th>
        <th>ChatGPT</th>
        <th>Niyo</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Bulk CV ingestion</td>
        <td class="negative">❌ Manual copy-paste</td>
        <td class="positive">✅ Automatic collection</td>
      </tr>
      <!-- More rows -->
    </tbody>
  </table>
</div>
```

```css
.comparison-table {
  width: 100%;
  max-width: 900px;
  margin: var(--space-12) auto;
  overflow-x: auto;
}

.comparison-table table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  background: var(--niyo-white);
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-lg);
}

.comparison-table th {
  background: var(--niyo-gray-900);
  color: var(--niyo-white);
  padding: var(--space-4) var(--space-6);
  font-weight: var(--weight-semibold);
  text-align: left;
}

.comparison-table td {
  padding: var(--space-4) var(--space-6);
  border-bottom: 1px solid var(--niyo-gray-300);
}

.comparison-table tr:last-child td {
  border-bottom: none;
}

.comparison-table td.negative {
  color: var(--niyo-gray-500);
}

.comparison-table td.positive {
  color: var(--niyo-success);
  font-weight: var(--weight-semibold);
}

/* Highlight Niyo column */
.comparison-table td:last-child {
  background: var(--niyo-clarity-overlay);
}
```

---

### Testimonial Card Component

```html
<div class="testimonial-card">
  <div class="testimonial-quote">
    <p>"We filled three engineering roles in two weeks. Before Niyo,
    that would've taken two months and burned out our entire team."</p>
  </div>

  <div class="testimonial-attribution">
    <img src="avatar.jpg" alt="Marcus Rodriguez" class="testimonial-avatar">
    <div class="testimonial-author">
      <span class="author-name">Marcus Rodriguez</span>
      <span class="author-title">Founder @ TechFlow</span>
      <span class="author-context">Series A, 47 employees</span>
    </div>
  </div>

  <div class="testimonial-stat">
    <span class="stat-label">Saved:</span>
    <span class="stat-value">180 hours of screening time</span>
  </div>
</div>
```

```css
.testimonial-card {
  background: var(--niyo-white);
  border-radius: var(--radius-xl);
  padding: var(--space-8);
  box-shadow: var(--shadow-lg);
  border-left: 4px solid var(--niyo-primary);
  max-width: 500px;
}

.testimonial-quote {
  font-size: var(--text-body);
  line-height: var(--leading-relaxed);
  color: var(--niyo-gray-900);
  margin-bottom: var(--space-6);
}

.testimonial-quote p::before {
  content: '"';
  font-size: 48px;
  color: var(--niyo-primary);
  line-height: 0;
  margin-right: var(--space-2);
}

.testimonial-attribution {
  display: flex;
  gap: var(--space-4);
  align-items: center;
  margin-bottom: var(--space-4);
  padding-top: var(--space-4);
  border-top: 1px solid var(--niyo-gray-300);
}

.testimonial-avatar {
  width: 56px;
  height: 56px;
  border-radius: var(--radius-full);
  object-fit: cover;
}

.testimonial-author {
  display: flex;
  flex-direction: column;
  gap: var(--space-1);
}

.author-name {
  font-weight: var(--weight-semibold);
  color: var(--niyo-black);
}

.author-title,
.author-context {
  font-size: var(--text-body-sm);
  color: var(--niyo-gray-500);
}

.testimonial-stat {
  background: var(--niyo-clarity-overlay);
  padding: var(--space-3) var(--space-4);
  border-radius: var(--radius-md);
  display: flex;
  gap: var(--space-2);
}

.testimonial-stat .stat-label {
  font-size: var(--text-body-sm);
  color: var(--niyo-gray-500);
}

.testimonial-stat .stat-value {
  font-size: var(--text-body-sm);
  font-weight: var(--weight-semibold);
  color: var(--niyo-success);
}
```

---

## PERFORMANCE OPTIMIZATION

### Image Optimization

```html
<!-- Use responsive images -->
<picture>
  <source
    srcset="hero-desktop.webp"
    media="(min-width: 1024px)"
    type="image/webp"
  >
  <source
    srcset="hero-tablet.webp"
    media="(min-width: 768px)"
    type="image/webp"
  >
  <img
    src="hero-mobile.webp"
    alt="Niyo Dashboard"
    loading="lazy"
    width="1200"
    height="800"
  >
</picture>
```

---

### Critical CSS (Inline in <head>)

```css
/* Only hero section styles inline */
.hero-section{min-height:100vh;display:flex;flex-direction:column;justify-content:center;background:linear-gradient(180deg,#fff 0%,#f1f5f9 100%);padding:5rem 1.5rem}.hero-headline{font-size:clamp(2.25rem,5vw,4.5rem);font-weight:800;color:#0f172a;line-height:1.1;max-width:800px;margin:0 auto}
```

---

### Lazy Loading Animations

```javascript
// Only animate when in viewport (save CPU)
const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -100px 0px'
};

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('animate-on-scroll', 'in-view');
      observer.unobserve(entry.target);
    }
  });
}, observerOptions);

document.querySelectorAll('.animate-on-scroll').forEach(el => {
  observer.observe(el);
});
```

---

## IMPLEMENTATION CHECKLIST

### Phase 1: Foundation (Week 1)
- [ ] Set up design tokens (CSS variables)
- [ ] Implement typography system
- [ ] Create button component library
- [ ] Build hero section (desktop + mobile)
- [ ] Add primary CTA with tracking

### Phase 2: Core Sections (Week 2)
- [ ] Build "The Villain" pain section
- [ ] Build "The Revelation" solution section
- [ ] Implement stat counter animations
- [ ] Add transformation panel visuals
- [ ] Create comparison table component

### Phase 3: Social Proof & Conversion (Week 3)
- [ ] Build testimonial card component
- [ ] Add "Why not ChatGPT" section
- [ ] Implement risk reversal section
- [ ] Add opportunity cost urgency section
- [ ] Build final challenge CTA

### Phase 4: Polish & Optimize (Week 4)
- [ ] Add scroll animations
- [ ] Implement parallax effects
- [ ] Optimize images (WebP, lazy loading)
- [ ] Mobile responsive testing
- [ ] Performance audit (Lighthouse)
- [ ] A/B testing setup (hero variants)

---

**All specs are production-ready. Designers and developers can implement directly from these specifications.**
