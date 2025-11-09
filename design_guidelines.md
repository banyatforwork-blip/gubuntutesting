# Gubuntu Website Design Guidelines

## Design Approach

**Reference-Based Approach**: Drawing inspiration from modern glassmorphism design trends (Apple's macOS interfaces, Windows 11 Fluent Design) combined with gaming/tech aesthetic (Discord, Razer) for the glowy interactive elements.

**Core Philosophy**: Create a premium, cutting-edge dark interface that emphasizes Gubuntu's pure, unbloated GNOME experience through clean glassmorphism and strategic use of luminous accents.

## Typography

**Font Families**:
- Primary: Inter (headers, UI elements) - modern, clean sans-serif via Google Fonts
- Secondary: JetBrains Mono (code snippets, version numbers) - technical monospace

**Hierarchy**:
- Hero Headline: Bold, 4xl-6xl, tight leading
- Section Headers: Semibold, 3xl-4xl
- Feature Titles: Semibold, xl-2xl
- Body Text: Regular, base-lg, increased line-height (1.7) for readability on dark backgrounds
- Accent Text: Medium weight with subtle glow effect

## Layout System

**Spacing Primitives**: Use Tailwind units of 4, 8, 12, 16, 20, 24 for consistent rhythm
- Component padding: p-8 to p-12
- Section spacing: py-20 to py-32
- Element gaps: gap-4, gap-8, gap-12

**Container Strategy**:
- Max width: max-w-7xl for content sections
- Full-width sections with inner containers for glassmorphic panels
- Responsive grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 for features

## Visual Design Language

### Glassmorphism Implementation

**Glass Panels**:
- Background: Semi-transparent dark backgrounds (bg-black/20 to bg-black/40)
- Backdrop blur: backdrop-blur-xl for frosted effect
- Borders: 1px borders with gradient opacity (border-white/10 to border-white/20)
- Subtle inner glow using box-shadow with color values

**Layering**:
- Multiple depth levels using varying blur and opacity
- Foreground elements: More opaque (bg-black/60)
- Background elements: More transparent (bg-black/20)

### Glow Effects

**Interactive Glows**:
- Primary accent color: Cyan/blue glow (#00d4ff, #0ea5e9) - matches GNOME blue
- Secondary: Purple/magenta (#a855f7, #d946ef) - complements the logo
- Hover states: Increase glow intensity and spread
- Active elements: Pulsing glow animation (subtle, 2-3s duration)

**Application**:
- Download buttons: Strong cyan glow on hover
- Feature cards: Border glow on hover
- Navigation links: Underline glow effect
- Logo: Ambient rainbow glow reflecting icon colors

## Component Library

### Navigation
- Sticky glassmorphic header with backdrop-blur-xl
- Logo on left, navigation links center, CTA button right
- Smooth scroll anchors to sections
- Mobile: Hamburger menu with slide-in glass panel

### Hero Section
- Full viewport height with gradient dark background
- Gubuntu logo (provided icon) with ambient glow
- Bold headline: "Ubuntu Without Canonical Bullshit"
- Subheadline: "Pure Stock GNOME Experience"
- Prominent glowing download button linking to SourceForge
- Floating glass particles or orbs animation in background (subtle)
- Scroll indicator with glow effect

### Features Grid
- 3-column layout (1 column mobile, 2 tablet, 3 desktop)
- Glass cards with:
  - Icon with cyan glow
  - Feature title
  - Brief description
  - Hover: Card lifts, border glow intensifies
- Features to highlight:
  - Stock GNOME (emphasize purity)
  - No Ubuntu Themes
  - Canonical Free
  - Actively Developing (Beta status badge)

### Download Section
- Large glassmorphic card center-aligned
- Latest version number with glow effect
- File size and download count from SourceForge
- Primary CTA: "Download Gubuntu" with strong glow
- System requirements in smaller glass panel below
- Link directly to SourceForge download

### Why Gubuntu Section
- Two-column layout with content + visual
- Bullet points in glass containers
- Screenshot placeholder or graphic element
- Emphasize: Pure GNOME, No bloat, Community-driven

### Footer
- Dark glassmorphic panel
- Links: GitHub, SourceForge, Community
- Social links with glow on hover
- Copyright and beta disclaimer
- Minimal, clean layout

## Animations

**Entrance Animations**:
- Fade-in with slight upward movement on scroll
- Stagger delay for grid items (0.1s increments)

**Interactive Animations**:
- Glow intensity transition: 300ms ease-out
- Card hover lift: transform translate-y with 200ms
- Button glow pulse on hover: 2s infinite for primary CTA
- Glassmorphic blur transitions on state changes

**Scroll Effects**:
- Parallax background gradient movement (subtle)
- Progressive blur on scroll-past elements (optional depth)

**Performance**: Use CSS transitions and transforms, avoid heavy JavaScript animations

## Color Palette

**Base**:
- Background gradient: Deep navy to black (#0a0e1a to #000000)
- Glass backgrounds: Black with 20-60% opacity
- Text: White (#ffffff) with varying opacities (90% primary, 70% secondary, 50% tertiary)

**Accents**:
- Primary Glow: Cyan (#00d4ff, #0ea5e9)
- Secondary Glow: Purple/Magenta (#a855f7)
- Success/Download: Bright cyan with glow
- Warning/Beta: Amber with subtle glow (#fbbf24)

**Borders & Dividers**:
- White with 10-20% opacity
- Gradient borders where appropriate (cyan to purple)

## Images

**Hero Background**: Optional subtle tech pattern or gradient mesh (dark, low opacity)
**Logo**: Use provided Gubuntu icon prominently in hero with glow effect
**Screenshots**: Show stock GNOME desktop in glassmorphic frames if available
**Icons**: Use line-style icons (Heroicons) for features with glow effects

## Accessibility

- Ensure text contrast ratios meet WCAG AA on glass backgrounds (use higher opacity backgrounds for text sections)
- Glow effects should enhance, not impair readability
- Focus states: Visible glow outline for keyboard navigation
- Reduced motion: Disable animations for users with prefers-reduced-motion

## Technical Notes

- Implement glassmorphism using backdrop-filter (webkit prefix for Safari)
- Glow effects using box-shadow with color and blur
- Gradient overlays for depth
- Responsive breakpoints: mobile (< 768px), tablet (768-1024px), desktop (> 1024px)
- Optimize for npm hosting on Ubuntu server (static build, minimal dependencies)