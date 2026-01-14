# Magic UI Components

**Documentation:** https://magicui.design/docs/components

150+ free animated React components built with TypeScript, Tailwind CSS, and Motion.

## Table of Contents
- [Text Effects](#text-effects)
- [Buttons](#buttons)
- [Backgrounds & Patterns](#backgrounds--patterns)
- [Animation Effects](#animation-effects)
- [Device Mockups](#device-mockups)
- [Data Visualization](#data-visualization)
- [Other Components](#other-components)

---

## Text Effects

| Component | Description | Best For |
|-----------|-------------|----------|
| **Animated Gradient Text** | Text with animated gradient colors | Headlines, CTAs |
| **Animated Shiny Text** | Shimmering text effect | Highlights |
| **Aurora Text** | Northern lights text effect | Hero text |
| **Comic Text** | Comic book style text | Playful designs |
| **Hyper Text** | Hyperactive scrambling text | Tech, hacker themes |
| **Line Shadow Text** | Text with line shadow effect | Editorial |
| **Morphing Text** | Text morphing between words | Dynamic headlines |
| **Sparkles Text** | Text with sparkle effects | Premium, magical |
| **Spinning Text** | Rotating text animation | Badges, highlights |
| **Text Animate** | Various text animations | General text |
| **Text Highlighter** | Highlight effect on text | Emphasis |
| **Text Reveal** | Text revealing animation | Intros |
| **Typing Animation** | Typewriter effect | Commands, intros |
| **Video Text** | Text with video fill | Creative headlines |
| **Word Rotate** | Rotating through words | Taglines |

## Buttons

| Component | Description | Best For |
|-----------|-------------|----------|
| **Interactive Hover Button** | Responsive hover effects | Primary actions |
| **Neon Gradient Card** | Neon glow gradient effect | CTAs, features |
| **Pulsating Button** | Pulse animation | Urgent CTAs |
| **Rainbow Button** | Rainbow gradient effect | Standout actions |
| **Ripple Button** | Material-style ripple | Standard buttons |
| **Shimmer Button** | Shimmer sweep effect | Premium CTAs |
| **Shine Border** | Animated shine border | Emphasis |
| **Shiny Button** | Shiny surface effect | Primary buttons |

## Backgrounds & Patterns

| Component | Description | Best For |
|-----------|-------------|----------|
| **Animated Grid Pattern** | Animated grid background | Tech themes |
| **Dot Pattern** | Dotted pattern background | Minimal designs |
| **Dotted Map** | Map with dot markers | Geographic data |
| **Flickering Grid** | Grid with flickering effect | Glitch aesthetics |
| **Grid Pattern** | Basic grid pattern | Backgrounds |
| **Interactive Grid Pattern** | Grid responding to mouse | Interactive BGs |
| **Retro Grid** | 80s-style retro grid | Retro themes |
| **Striped Pattern** | Striped background | Minimal accents |
| **Warp Background** | Warping background effect | Hero sections |

## Animation Effects

| Component | Description | Best For |
|-----------|-------------|----------|
| **Animated Beam** | Beam animation between elements | Connections |
| **Animated Circular Progress Bar** | Circular progress animation | Stats, loading |
| **Animated List** | List items animating in | Notifications |
| **Blur Fade** | Blur with fade animation | Page transitions |
| **Border Beam** | Animated border beam | Card emphasis |
| **Confetti** | Confetti celebration | Success states |
| **Cool Mode** | Particle effects on click | Micro-interactions |
| **Light Rays** | Light ray effects | Dramatic reveals |
| **Magic Card** | Card with magic effect | Feature cards |
| **Marquee** | Infinite scrolling marquee | Logos, testimonials |
| **Meteors** | Meteor shower effect | Space themes |
| **Orbiting Circles** | Circles orbiting center | Tech diagrams |
| **Particles** | Particle system | Backgrounds |
| **Pixel Image** | Pixelation effect | Artistic reveals |
| **Progressive Blur** | Progressive blur effect | Focus effects |
| **Ripple** | Ripple animation | Interactive BGs |
| **Sparkles Text** | Sparkle overlay | Highlights |

## Device Mockups

| Component | Description | Best For |
|-----------|-------------|----------|
| **Android** | Android phone mockup | App showcases |
| **iPhone** | iPhone mockup | App showcases |
| **Safari** | Safari browser mockup | Web showcases |
| **Terminal** | Terminal window mockup | CLI showcases |
| **Dock** | macOS-style dock | App launchers |

## Data Visualization

| Component | Description | Best For |
|-----------|-------------|----------|
| **Avatar Circles** | Overlapping avatar circles | Team displays |
| **Bento Grid** | Bento box layout | Feature grids |
| **File Tree** | Animated file tree | Documentation |
| **Globe** | 3D globe visualization | Global presence |
| **Icon Cloud** | Floating icon cloud | Tech stacks |
| **Number Ticker** | Animated number counter | Statistics |
| **Scroll Based Velocity** | Velocity-based scroll | Parallax text |
| **Scroll Progress** | Scroll progress indicator | Reading progress |
| **Tweet Card** | Twitter card embed | Social proof |

## Other Components

| Component | Description | Best For |
|-----------|-------------|----------|
| **Code Comparison** | Side-by-side code diff | Documentation |
| **Hero Video Dialog** | Video dialog for hero | Product videos |
| **Lens** | Magnifying lens effect | Product details |
| **Pointer** | Custom cursor pointer | Creative sites |
| **Smooth Cursor** | Smooth following cursor | Premium feel |

## Installation

```bash
# Via CLI (recommended)
npx magicui-cli add [component-name]

# Or manual installation with dependencies
npm install framer-motion clsx tailwind-merge
```

## Usage Pattern

```tsx
// Example: Shimmer Button
import { ShimmerButton } from "@/components/magicui/shimmer-button";

export function Example() {
  return (
    <ShimmerButton className="shadow-2xl">
      <span className="whitespace-pre-wrap text-center">
        Get Started
      </span>
    </ShimmerButton>
  );
}
```

Visit individual component pages for specific code and customization options.
