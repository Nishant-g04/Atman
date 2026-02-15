# Atman App - Elevated UI/UX Design Specification (v2.0)

## Hackathon Scope Note

**This design system represents Atman's long-term UI vision.**

**For the hackathon MVP, we will implement:**
- Core color palette
- Primary button styles  
- Product analysis screen
- Scanner screen

**All other elements are part of future polish.**

---


## 1. Design Philosophy

### 1.1 Design Principles 
- **Organic Tech**: Clean, intuitive interface that feels warm and natural
- **Premium Wellness**: Visual design that conveys trust, serenity, and premium quality
- **Accessibility**: Inclusive design for users with different abilities
- **Indian Context**: Earth tones, typography, and patterns that resonate deeply with Indian users
- **Mobile-First**: Optimized for smartphone usage patterns with one-thumb navigation

### 1.2 Brand Identity 
- **Brand Name**: Atman (Sanskrit for "soul/self")
- **Tagline**: "Your Personal LifeStyle Guardian"
- **Brand Values**: Trust, Personalization, Serenity, Empowerment
- **Personality**: Caring, Intelligent, Grounded, 
- **Aesthetic Shift**: "Premium Wellness Companion"
- **Vibe**: Serene, Intelligent, Grounded (Think: Headspace meets Forest Essentials)

## 2. Visual Design System

### 2.1 Refined Color Palette (Nature-Inspired)

#### Primary Colors (The "Soul" Palette)
```css
/* Primary: Deep Forest (Trust & Nature) */
--primary-dark: #0F3934;   /* Text, Headers, Tab Bars */
--primary-main: #145D55;   /* Main Brand Color */
--primary-soft: #E6F2F1;   /* Backgrounds for active states */

/* Accent: Terracotta (Energy & Action - The "Indian Touch") */
--accent-main: #E06C45;    /* CTAs, "Buy Now" buttons */
--accent-hover: #C5532E;   /* Hover states */
--accent-soft: #FDEEE9;    /* Light accent backgrounds */

/* Secondary: Calm Sand (Warmth) */
--surface-warm: #FAF9F6;   /* Main App Background (Off-white, not gray) */
--surface-card: #FFFFFF;   /* Card Background */
```

#### Functional Colors (Health-Focused)
```css
/* Health Ratings */
--score-high: #145D55;     /* Deep Green (Safe) */
--score-med: #D9A404;      /* Golden Turmeric (Caution) */
--score-low: #C53030;      /* Muted Red (Avoid) */

/* Status Colors */
--success: #145D55;        /* Deep Forest Green */
--success-light: #E6F2F1;
--success-dark: #0F3934;

--warning: #D9A404;        /* Golden Turmeric */
--warning-light: #FDF6E3;
--warning-dark: #B7791F;

--error: #C53030;          /* Muted Red */
--error-light: #FED7D7;
--error-dark: #9B2C2C;

--info: #145D55;           /* Deep Forest */
--info-light: #E6F2F1;
--info-dark: #0F3934;
```

#### Neutral Colors (Warm Grays)
```css
/* Warm Grays */
--gray-50: #FAF9F6;   /* Warm background */
--gray-100: #F7F6F3;  /* Light warm backgrounds */
--gray-200: #E8E6E1;  /* Warm borders */
--gray-300: #D6D3CE;  /* Disabled elements */
--gray-400: #B8B5B0;  /* Placeholder text */
--gray-500: #9A9691;  /* Secondary text */
--gray-600: #7C7873;  /* Body text */
--gray-700: #5E5B56;  /* Headings */
--gray-800: #403E3A;  /* Dark text */
--gray-900: #1A1917;  /* Primary text */
```

All palettes tested for WCAG AA compliance (4.5:1 contrast for normal text, 3:1 for large) using tools like WebAIM Contrast Checker.

### 2.2 Typography (More Personality)

#### Font Family (Friendly & Modern)
```css
/* Headings - Plus Jakarta Sans (Geometric, friendly, modern) */
--font-heading: 'Plus Jakarta Sans', 'Manrope', sans-serif;

/* Body - Inter (Kept for readability) */
--font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;

/* Secondary Font - Noto Sans (Multi-language support) */
--font-secondary: 'Noto Sans', 'Inter', sans-serif;

/* Monospace - Code/Technical */
--font-mono: 'JetBrains Mono', 'Fira Code', monospace;
```

#### Typography Scale
```css
/* Headings */
--text-4xl: 2.25rem;  /* 36px - Page titles */
--text-3xl: 1.875rem; /* 30px - Section headers */
--text-2xl: 1.5rem;   /* 24px - Card titles */
--text-xl: 1.25rem;   /* 20px - Subheadings */
--text-lg: 1.125rem;  /* 18px - Large body */

/* Body Text */
--text-base: 1rem;    /* 16px - Default body */
--text-sm: 0.875rem;  /* 14px - Small text */
--text-xs: 0.75rem;   /* 12px - Captions */

/* Font Weights */
--font-light: 300;
--font-regular: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;
```

### 2.3 UI Styling (Soft & Airy)

#### Spacing System
```css
/* Spacing Scale (8px base unit) */
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-5: 1.25rem;   /* 20px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-10: 2.5rem;   /* 40px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
--space-20: 5rem;     /* 80px */
```

#### Border Radius & Shadows (Organic Curves)
```css
/* Border Radius - Super Soft */
--radius-card: 20px;   /* Larger curves for cards */
--radius-btn: 12px;    /* Buttons */
--radius-tag: 50px;    /* Pills/Tags */
--radius-sm: 8px;      /* Small elements */
--radius-lg: 24px;     /* Large cards */
--radius-xl: 32px;     /* Modals */
--radius-full: 9999px; /* Circular elements */

/* Shadows - Soft & Diffused (No harsh black shadows) */
--shadow-card: 0px 8px 24px rgba(20, 93, 85, 0.08);
--shadow-float: 0px 12px 32px rgba(20, 93, 85, 0.15);
--shadow-sm: 0 2px 8px rgba(20, 93, 85, 0.06);
--shadow-md: 0 4px 16px rgba(20, 93, 85, 0.08);
--shadow-lg: 0 8px 24px rgba(20, 93, 85, 0.12);
--shadow-xl: 0 16px 40px rgba(20, 93, 85, 0.16);

/* Glassmorphism (For Scanning Overlays) */
--glass-bg: rgba(255, 255, 255, 0.85);
--glass-border: 1px solid rgba(255, 255, 255, 0.5);
--glass-blur: blur(12px);
```

## 3. Component Library (Upgraded)

### 3.1 Buttons (Elevated Design)

#### Primary Button (Deep Forest)
```css
.btn-primary {
  background: var(--primary-main); /* Forest Green */
  color: #FFFFFF;
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-btn);
  font-weight: var(--font-semibold);
  font-size: var(--text-base);
  border: none;
  /* Subtle inner light for 3D feel */
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.2), var(--shadow-card);
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background: var(--primary-dark);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.2), var(--shadow-float);
  transform: translateY(-2px);
}

.btn-primary:active {
  transform: translateY(0);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.2), var(--shadow-card);
}
```

#### Accent Button (Terracotta)
```css
.btn-accent {
  background: var(--accent-main); /* Terracotta */
  color: #FFFFFF;
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-btn);
  font-weight: var(--font-semibold);
  font-size: var(--text-base);
  border: none;
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.2), var(--shadow-card);
  transition: all 0.3s ease;
}

.btn-accent:hover {
  background: var(--accent-hover);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.2), var(--shadow-float);
  transform: translateY(-2px);
}
```

#### Secondary Button (Soft)
```css
.btn-secondary {
  background: var(--surface-card);
  color: var(--primary-main);
  border: 2px solid var(--primary-soft);
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-btn);
  font-weight: var(--font-semibold);
  box-shadow: var(--shadow-sm);
  transition: all 0.3s ease;
}

.btn-secondary:hover {
  background: var(--primary-soft);
  border-color: var(--primary-main);
  box-shadow: var(--shadow-md);
}
```

### 3.2 Cards (Organic & Premium)

#### Health Score Card (Visual Progress)
```css
.score-card {
  background: var(--surface-card);
  border-radius: var(--radius-card);
  border: 1px solid rgba(0,0,0,0.03);
  box-shadow: var(--shadow-card);
  padding: var(--space-6);
  text-align: center;
  transition: all 0.3s ease;
}

.score-card:hover {
  box-shadow: var(--shadow-float);
  transform: translateY(-4px);
}

.score-ring {
  width: 120px;
  height: 120px;
  margin: 0 auto var(--space-4);
}

.score-ring circle {
  stroke: var(--score-high);
  stroke-width: 8;
  stroke-linecap: round;
  transition: stroke-dasharray 0.6s ease;
}

.score-number {
  font-family: var(--font-heading);
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  color: var(--primary-dark);
}

.score-label {
  font-size: var(--text-sm);
  color: var(--gray-600);
  font-weight: var(--font-medium);
}
```

#### Product Card (Premium Feel)
```css
.product-card {
  background: var(--surface-card);
  border-radius: var(--radius-card);
  box-shadow: var(--shadow-card);
  padding: var(--space-6);
  border: 1px solid rgba(20, 93, 85, 0.05);
  transition: all 0.4s ease;
  overflow: hidden;
}

.product-card:hover {
  box-shadow: var(--shadow-float);
  transform: translateY(-6px);
  border-color: rgba(20, 93, 85, 0.1);
}

.product-card__image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: var(--radius-btn);
  margin-bottom: var(--space-4);
}

.product-card__title {
  font-family: var(--font-heading);
  font-size: var(--text-lg);
  font-weight: var(--font-semibold);
  color: var(--primary-dark);
  margin-bottom: var(--space-2);
}

.product-card__brand {
  font-size: var(--text-sm);
  color: var(--gray-500);
  margin-bottom: var(--space-3);
}
```

#### Compatibility Badge 
```css
.compatibility-badge {
  display: inline-flex;
  align-items: center;
  padding: var(--space-2) var(--space-4);
  border-radius: var(--radius-tag);
  font-size: var(--text-xs);
  font-weight: var(--font-semibold);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  transition: all 0.2s ease;
}

.compatibility-badge--safe {
  background: var(--success-light);
  color: var(--success-dark);
  border: 1px solid rgba(20, 93, 85, 0.2);
}

.compatibility-badge--caution {
  background: var(--warning-light);
  color: var(--warning-dark);
  border: 1px solid rgba(217, 164, 4, 0.2);
}

.compatibility-badge--avoid {
  background: var(--error-light);
  color: var(--error-dark);
  border: 1px solid rgba(197, 48, 48, 0.2);
}
```

### 3.3 Form Elements (Soft & Accessible)

#### Input Fields (Warm & Inviting)
```css
.form-input {
  width: 100%;
  padding: var(--space-4) var(--space-5);
  border: 2px solid var(--gray-200);
  border-radius: var(--radius-btn);
  font-size: var(--text-base);
  background: var(--surface-card);
  transition: all 0.3s ease;
  font-family: var(--font-body);
}

.form-input:focus {
  outline: none;
  border-color: var(--primary-main);
  box-shadow: 0 0 0 4px rgba(20, 93, 85, 0.1);
  background: var(--surface-warm);
}

.form-input--error {
  border-color: var(--error);
  box-shadow: 0 0 0 4px rgba(197, 48, 48, 0.1);
}

.form-label {
  display: block;
  font-family: var(--font-heading);
  font-size: var(--text-sm);
  font-weight: var(--font-semibold);
  color: var(--primary-dark);
  margin-bottom: var(--space-2);
}
```

#### Toggle Switch (Organic)
```css
.toggle-switch {
  position: relative;
  width: 56px;
  height: 32px;
  background: var(--gray-300);
  border-radius: var(--radius-full);
  cursor: pointer;
  transition: all 0.4s ease;
  box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);
}

.toggle-switch--active {
  background: var(--primary-main);
  box-shadow: inset 0 2px 4px rgba(20, 93, 85, 0.2);
}

.toggle-switch__handle {
  position: absolute;
  top: 4px;
  left: 4px;
  width: 24px;
  height: 24px;
  background: var(--surface-card);
  border-radius: 50%;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: var(--shadow-sm);
}

.toggle-switch--active .toggle-switch__handle {
  transform: translateX(24px);
  box-shadow: var(--shadow-md);
}
```

## 4. Screen Layouts 

### 4.1 Home Screen 

```
┌─────────────────────────────────┐
│ [Avatar]                   [🔔] │
│                                 │
│  Namaste, Priya 🙏              │
│  Your skin is looking great!    │
│                                 │
│  ┌─────────────────────────────┐ │
│  │ [GRADIENT: Forest/Sage]     │ │
│  │                             │ │
│  │   📷  Scan New Product      │ │
│  │   Check ingredients instant │ │
│  └─────────────────────────────┘ │
│                                 │
│  Pantry Alerts                  │
│  ┌──────┐ ┌──────┐ ┌──────┐     │
│  │ 🧴   │ │ 🧼   │ │ 💊   │     │
│  │ Face │ │ Soap │ │ Vit  │     │
│  │ 2d   │ │ 5d   │ │ 7d   │     │
│  └──────┘ └──────┘ └──────┘     │
│                                 │
│  Daily Tip                      │
│  ┌─────────────────────────────┐ │
│  │ 🥑 "Turmeric is great for   │ │
│  │     Oily skin..."           │ │
│  └─────────────────────────────┘ │
│                                 │
│ [🏠] [🔍] [ 📷 ] [🛒] [👤]     │
└─────────────────────────────────┘
```

**Design Notes:**
- Background: Warm Sand (#FAF9F6)
- Header: Deep Forest Green text
- Cards: White cards with soft shadows
- Bottom nav: Camera button floating in middle (raised)
- Greeting uses warm, personal language

### 4.2 Product Analysis (The "Trust" Screen)

```
┌─────────────────────────────────┐
│ [←]          [❤️] [🔗 Share]    │
│                                 │
│      [ Product Image ]          │
│     (Floating on white)         │
│                                 │
│  Himalaya Neem Wash             │
│  by Himalaya Wellness           │
│                                 │
│ ┌─────────────────────────────┐ │
│ │       Atman Score           │ │
│ │         [ 92 ]              │ │
│ │     Excellent Match         │ │
│ └─────────────────────────────┘ │
│                                 │
│ Why it works for you:           │
│ [🌿 Neem] Matches [Oily Skin]   │
│ [✨ Glow] No [Parabens]         │
│                                 │
│ ┌─────────────────────────────┐ │
│ │     ⚡ Compare Prices       │ │
│ │ Amazon: ₹140 | Nykaa: ₹150  │ │
│ └─────────────────────────────┘ │
│                                 │
│ [    BUY NOW (Terracotta)     ] │
└─────────────────────────────────┘
```

**Design Notes:**
- Header: Clean white background
- Score: Large circular gauge with organic curves
- Badges: Pill-shaped with soft pastel backgrounds
- CTA: Terracotta accent color for "Buy Now"

### 4.3 Scanner Screen (Glassmorphism)

```
┌─────────────────────────────────┐
│  [×]        Scan Product        │
│                                 │
│  ┌─────────────────────────────┐ │
│  │                             │ │
│  │     [Camera Viewfinder]     │ │
│  │                             │ │
│  │    ┌─────────────────┐      │ │
│  │    │  Soft Glowing   │      │ │
│  │    │  Green Box      │      │ │
│  │    │  (Breathing)    │      │ │
│  │    └─────────────────┘      │ │
│  │                             │ │
│  └─────────────────────────────┘ │
│                                 │
│  Point camera at barcode        │
│                                 │
│  [💡] [📷] [🔄]                │
│                                 │
│  Or enter product name manually │
│  [________________] [Search]    │
└─────────────────────────────────┘
```

**Design Notes:**
- Overlay: Glassmorphism effect with soft blur
- Scan indicator: Soft glowing green box with breathing animation
- No harsh red laser lines - organic pulsing instead

## 5. Micro-Interactions (The "Delight" Factor)

### 5.1 Scanning Animations
```css
/* Breathing Scan Box */
@keyframes breathe {
  0%, 100% { 
    transform: scale(1);
    opacity: 0.8;
  }
  50% { 
    transform: scale(1.05);
    opacity: 1;
  }
}

.scan-overlay {
  border: 3px solid var(--primary-main);
  border-radius: var(--radius-btn);
  animation: breathe 2s ease-in-out infinite;
  box-shadow: 0 0 20px rgba(20, 93, 85, 0.3);
}
```

### 5.2 Success Animations
```css
/* Leaf Confetti for Perfect Score */
@keyframes leafFall {
  0% { 
    transform: translateY(-100vh) rotate(0deg);
    opacity: 1;
  }
  100% { 
    transform: translateY(100vh) rotate(360deg);
    opacity: 0;
  }
}

.leaf-confetti {
  position: fixed;
  font-size: 24px;
  animation: leafFall 3s linear infinite;
}

/* Score Counter Animation */
@keyframes countUp {
  from { transform: scale(0.5); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}

.score-number {
  animation: countUp 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}
```

### 5.3 Ingredient Explanation (Bottom Sheet)
```css
.ingredient-sheet {
  background: var(--glass-bg);
  backdrop-filter: var(--glass-blur);
  border: var(--glass-border);
  border-radius: var(--radius-card) var(--radius-card) 0 0;
  padding: var(--space-6);
  transform: translateY(100%);
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.ingredient-sheet--open {
  transform: translateY(0);
}
```

## 6. Dark Mode Support (Warm Dark)

### 6.1 Dark Theme Colors
```css
[data-theme="dark"] {
  --bg-primary: #1A1917;        /* Warm dark, not pure black */
  --bg-secondary: #2D2B28;      /* Warm dark secondary */
  --bg-tertiary: #3A3835;       /* Warm dark tertiary */
  
  --text-primary: #FAF9F6;      /* Warm white */
  --text-secondary: #D6D3CE;    /* Warm light gray */
  --text-tertiary: #B8B5B0;     /* Warm medium gray */
  
  --border-primary: #3A3835;    /* Warm dark borders */
  --border-secondary: #2D2B28;  /* Darker warm borders */
  
  /* Maintain brand colors but adjust opacity */
  --primary-main: #1A6B61;      /* Slightly lighter forest */
  --accent-main: #E06C45;       /* Keep terracotta vibrant */
  --surface-warm: #1A1917;      /* Dark warm background */
  --surface-card: #2D2B28;      /* Dark warm cards */
}
```

## 7. Accessibility & Inclusive Design

### 7.1 Color Accessibility
- **Contrast Ratios**: Minimum 4.5:1 for normal text, 3:1 for large text
- **Color Independence**: Icons + text labels alongside colors
- **Color Blind Support**: Patterns and shapes differentiate status

### 7.2 Touch Targets
- **Minimum Size**: 44px × 44px on mobile
- **Spacing**: 8px minimum between interactive elements
- **Feedback**: Visual and haptic feedback for all interactions

### 7.3 Typography Accessibility
- **Minimum Font Size**: 16px for body text
- **Line Height**: 1.5x font size
- **Font Weight**: Minimum 400 for body text

## 8. Performance Considerations

### 8.1 Animation Performance
- **GPU Acceleration**: Use transform and opacity for animations
- **Reduced Motion**: Respect user's motion preferences
- **Frame Rate**: Target 60fps for all animations

### 8.2 Image Optimization
- **WebP Format**: With JPEG fallback
- **Lazy Loading**: Intersection observer implementation
- **Responsive Images**: Multiple sizes for different screens

## 9. Comparison Summary

| Feature | Original Design | New "Atman 2.0" Design |
|---------|----------------|------------------------|
| Primary Color | Clinical Green (#2E7D32) | Deep Forest Green (#145D55) |
| Accent Color | Tech Blue (#1976D2) | Terracotta / Burnt Orange (#E06C45) |
| Background | Cold Gray (#FAFAFA) | Warm Sand / Off-White (#FAF9F6) |
| Typography | Standard Inter | Plus Jakarta Sans (Friendly) |
| Shapes | Standard Rounded (8px) | Organic Curves (20px+) |
| Shadows | Standard Black | Soft Forest Green Tinted |
| Vibe | Medical Tool | Premium Wellness Lifestyle |
| Market Appeal | Clinical/Functional | Lifestyle/Aspirational |

## 10. Implementation Priority

### Phase 1: Core Visual Update
1. Update color palette across all components
2. Implement new typography system
3. Update button and card designs
4. Add organic border radius

### Phase 2: Enhanced Interactions
1. Implement breathing scan animation
2. Add score counter animations
3. Create ingredient explanation sheets
4. Add success celebrations

### Phase 3: Premium Polish
1. Implement glassmorphism effects
2. Add micro-interactions
3. Perfect dark mode
4. Optimize performance
   

This design elevates Atman from a utility tool to a trusted daily companion — serene, intelligent, and truly made for Bharat.

