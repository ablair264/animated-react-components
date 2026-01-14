---
name: animated-react-components
description: Expert UI consultant for analyzing React components and recommending/implementing premium animated enhancements. Use when (1) analyzing existing React components for animation opportunities, (2) recommending specific components from ReactBits, Aceternity UI, or Magic UI libraries, (3) creating custom animations with Motion.dev, (4) implementing production-grade animated components, or (5) user mentions animations, interactions, micro-interactions, or wants to enhance UI with motion. Guides creation of visually striking, memorable interfaces at high production standards.
---

# Animated React Components

Expert guidance for analyzing and enhancing React components with premium animations.

## Component Libraries

Four libraries available for implementation:

| Library | Best For | Docs |
|---------|----------|------|
| **React Bits** | 135+ animated components (cursors, text effects, backgrounds) | reactbits.dev |
| **Aceternity UI** | 120+ components (3D effects, scroll animations, cards) | ui.aceternity.com |
| **Magic UI** | 150+ components (device mockups, text effects, patterns) | magicui.design |
| **Motion** | Custom animations (transitions, gestures, layout) | motion.dev |

See `references/react-bits.md`, `references/aceternity-ui.md`,
`references/magic-ui.md`, and `references/motion.md` for catalogs and patterns.

## Inputs Needed

Ask for these if missing:
- Component code or file paths
- Framework and styling setup (Next.js, Vite, Tailwind, CSS-in-JS)
- Design system constraints (fonts, colors, spacing, tokens)
- Performance budget or device targets
- Interaction goals (what should feel "alive")
- Accessibility requirements beyond defaults

## Library Selection (Decision Tree)

- 3D, scroll-driven, or hero interactions: Aceternity UI
- Text, cursor, or background effects: React Bits
- Device mockups, patterns, shimmer/glow: Magic UI
- Custom choreography or brand-specific motion: Motion

## Workflow

### 1. Analyze Context

Before any implementation, understand:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Existing patterns**: What animations/transitions already exist?
- **Technical constraints**: Framework, performance budget, accessibility requirements
- **Differentiation**: What's the ONE thing someone will remember?

### 2. Commit to Aesthetic Direction

Choose a BOLD direction. Examples live in `references/aesthetic-directions.md`.

**Every detail must serve ONE cohesive vision.**

If a design system exists, preserve its typography, colors, and spacing. Express
the direction through motion, layout, and component choice.

### 3. Select Components Strategically

**DO NOT** sloppily scatter animations. Instead:
- Identify 2-3 high-impact moments (page load, key interactions, CTAs)
- Match component complexity to aesthetic vision
- Prioritize one well-orchestrated sequence over many scattered effects

**Selection criteria:**
- Does it enhance understanding or engagement?
- Does it align with the committed aesthetic?
- Is it performant for the use case?

### 4. Implementation Standards

Every component must be:
- Production-grade and functional
- Responsive across devices
- Accessible (respects `prefers-reduced-motion`)
- Performant (prefer CSS/GPU-accelerated)
- Follow the implementation checklist in `references/motion.md`
- Follow production standards in `references/production-quality.md`
- Use production patterns from `references/production-patterns.md`

## Production Quality Bar

- Keep motion consistent with shared tokens (duration, easing, stagger)
- Prefer variants and declarative motion over ad-hoc animations
- Avoid non-deterministic render output (SSR-safe defaults)
- Provide reduced-motion fallbacks for every effect
- Validate performance on low-end devices and mobile

See `references/production-quality.md` and `references/production-patterns.md`
for detailed standards, patterns, and QA checks.

## Design Principles

### Typography

Typography carries the design's singular voice.

**DO:**
- Choose fonts with interesting personality
- Use display type expressively, even riskily
- Work the full range: size, weight, case, spacing
- Pair fonts like actors in a scene

**DO NOT:**
- Default fonts signal default thinking
- Skip: Arial, Inter, Roboto, Space Grotesk, system fonts

### Color & Theme

Commit to a cohesive palette that takes a clear position.

**Approaches:**
- Bold and saturated
- Moody and restrained
- High-contrast minimal

**Structure:**
- Lead with dominant color
- Punctuate with sharp accents
- Avoid timid, non-committal distributions
- Use CSS variables for consistency

### Motion

**High-impact focus:**
- One well-orchestrated page load beats scattered micro-interactions
- Use `animation-delay` for staggered reveals
- Scroll-triggered and hover states that surprise

**Technical priority:**
1. CSS-only for simple effects
2. Motion library for React when complex
3. Always respect `prefers-reduced-motion`

### Spatial Composition

Break expectations with:
- Asymmetry and overlap
- Z-depth and diagonal flow
- Grid-breaking elements
- Dramatic scale jumps
- Full-bleed moments
- Generous negative space OR controlled density

### Backgrounds & Visual Details

Create atmosphere, not solid colors:
- Gradient meshes
- Noise and grain overlays
- Geometric patterns
- Glassmorphism with layered transparencies
- Dramatic shadows and glows
- Parallax depth
- Custom clip-path shapes
- Print-inspired textures (halftone, duotone, stipple)

## Anti-Patterns

**NEVER produce generic AI aesthetics:**

| Avoid | Instead |
|-------|---------|
| Inter, Roboto, Arial, system fonts | Distinctive fonts with personality |
| Purple gradients on white | Bold, committed palettes |
| Predictable component patterns | Layouts that surprise |
| Cookie-cutter designs | Bespoke, context-specific details |
| Animations everywhere | Strategic high-impact moments |

## Implementation Complexity

Match code complexity to vision:

- **Maximalist designs**: Elaborate code, extensive animations, layered effects
- **Minimalist designs**: Restraint, elegance, precision
- **All designs**: Careful spacing, typography, subtle details

## Quick Reference

### When to use each library:

**React Bits** → Cursor effects, text animations, animated backgrounds, interactive elements

**Aceternity UI** → 3D cards, scroll animations, hero sections, modals, navigation

**Magic UI** → Device mockups, text effects, patterns, buttons with shimmer/glow

**Motion** → Custom transitions, gestures, layout animations, orchestrated sequences

### Component selection by use case:

| Use Case | Recommended |
|----------|-------------|
| Hero section | Aceternity Hero Parallax, Magic UI Warp Background |
| Page transitions | Motion layout animations |
| Text reveal | React Bits BlurText, Aceternity Text Generate |
| Cards | Aceternity 3D Card, Wobble Card |
| Backgrounds | React Bits Aurora/Particles, Magic UI Grid Pattern |
| Navigation | Aceternity Floating Dock, Resizable Navbar |
| CTAs | Magic UI Shimmer Button, Aceternity Moving Border |
| Cursors | React Bits BlobCursor, SplashCursor |

See `references/react-bits.md`, `references/aceternity-ui.md`,
`references/magic-ui.md`, and `references/motion.md` for complete catalogs.

## Output Template

Deliver responses in this shape:
- Aesthetic direction (1-2 options) and rationale
- 2-3 high-impact moments with intent
- Component/library picks with reasons
- Implementation notes (reduced motion, perf guardrails)
- Motion tokens (duration, easing, stagger)
- QA checks (reduced motion, keyboard, perf)
- Integration plan (where changes land in the code)
