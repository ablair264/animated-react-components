# React Bits Components

**Documentation:** https://reactbits.dev

135+ animated React components with 4 variants per component (JS-CSS, JS-TW, TS-CSS, TS-TW).

## Table of Contents
- [Backgrounds](#backgrounds)
- [Animations](#animations)
- [Text Animations](#text-animations)
- [Buttons](#buttons)
- [Components](#components)

---

## Backgrounds

Production-ready WebGL and CSS background effects.

| Component | Description | Best For |
|-----------|-------------|----------|
| **Aurora** | Northern lights effect | Hero sections |
| **Ballpit** | Interactive ball physics | Playful sites |
| **Beams** | Light beam animations | Tech products |
| **Dots** | Animated dot pattern | Minimal backgrounds |
| **Gradient** | Animated gradient mesh | Modern SaaS |
| **Grid** | Animated grid pattern | Tech themes |
| **Hyperspeed** | Warp speed effect | Futuristic themes |
| **Iridescent** | Color-shifting surface | Premium sites |
| **Lightning** | Lightning strikes | Dramatic effects |
| **Liquid** | Liquid simulation | Organic themes |
| **Nebula** | Space nebula effect | Space themes |
| **Particles** | Particle system | Versatile |
| **Ripples** | Ripple animations | Calm, water themes |
| **Squares** | Animated squares | Geometric |
| **Threads** | Threading lines | Abstract |
| **Waves** | Wave animations | Fluid themes |

## Animations

Professional cursor and interaction animations.

| Component | Description | Best For |
|-----------|-------------|----------|
| **BlobCursor** | Blob following cursor | Creative sites |
| **ClickSpark** | Spark on click | Micro-interactions |
| **Crosshair** | Crosshair cursor | Gaming, precision |
| **Elastic** | Elastic cursor effect | Playful interactions |
| **Flashlight** | Flashlight reveal | Dark themes |
| **FollowCursor** | Element follows cursor | Interactive elements |
| **GlitchText** | Glitch text effect | Tech, hacker themes |
| **Magnetic** | Magnetic hover effect | Button emphasis |
| **Magnet** | Elements attracted to cursor | Interactive |
| **Morphing** | Shape morphing | Creative transitions |
| **Pixelate** | Pixelation effect | Retro, artistic |
| **Spotlight** | Spotlight on cursor | Focus effects |
| **SplashCursor** | Splash effect cursor | Artistic sites |
| **SpringCursor** | Springy cursor follower | Playful |
| **Tilt** | 3D tilt on hover | Cards, images |
| **Trail** | Cursor trail effect | Creative |

## Text Animations

Complete Framer Motion text effects.

| Component | Description | Best For |
|-----------|-------------|----------|
| **BlurText** | Blur reveal animation | Intros |
| **CircularText** | Text in circle | Badges, stamps |
| **CountUp** | Number counting | Statistics |
| **DecryptText** | Decryption effect | Tech, security |
| **FadeText** | Fade in animation | Subtle reveals |
| **FlipText** | Flip animation | Headlines |
| **GlitchText** | Glitch effect | Tech themes |
| **GradientText** | Gradient coloring | Headlines |
| **RotatingText** | Rotating words | Taglines |
| **ScrambleText** | Scramble reveal | Tech themes |
| **ShinyText** | Shimmer effect | Highlights |
| **SplitText** | Split animation | Creative headlines |
| **TextMarquee** | Scrolling text | Announcements |
| **TypeText** | Typewriter | Commands, intros |
| **WaveText** | Wave animation | Playful text |

## Buttons

Note: Currently return placeholder code in some cases. Check reactbits.dev for updates.

| Component | Description | Best For |
|-----------|-------------|----------|
| **GlowButton** | Glowing effect | Primary CTAs |
| **MagneticButton** | Magnetic hover | Interactive CTAs |
| **NeonButton** | Neon glow | Dark themes |
| **OutlineButton** | Animated outline | Secondary actions |
| **PulseButton** | Pulse animation | Urgent CTAs |
| **RippleButton** | Ripple on click | Material style |
| **ShineButton** | Shine sweep | Premium buttons |
| **SlideButton** | Slide animation | Interactive |

## Components

General interactive components.

| Component | Description | Best For |
|-----------|-------------|----------|
| **AnimatedCard** | Animated card component | Feature cards |
| **AnimatedList** | List with animations | Notifications |
| **Carousel** | Animated carousel | Galleries |
| **Dock** | macOS-style dock | Navigation |
| **Drawer** | Animated drawer | Mobile menus |
| **Modal** | Animated modal | Dialogs |
| **ProgressBar** | Animated progress | Loading, stats |
| **ScrollReveal** | Reveal on scroll | Page sections |
| **Tabs** | Animated tabs | Content switching |
| **Toast** | Animated toasts | Notifications |
| **Tooltip** | Animated tooltip | Help text |

## Installation

```bash
# Via jsrepo CLI
npx jsrepo add github/davidhdev/react-bits/[component-name]

# Example
npx jsrepo add github/davidhdev/react-bits/backgrounds/aurora
```

## Variants

Each component comes in 4 variants:
- **JS-CSS**: JavaScript + CSS modules
- **JS-TW**: JavaScript + Tailwind CSS
- **TS-CSS**: TypeScript + CSS modules
- **TS-TW**: TypeScript + Tailwind CSS

## Animation Engines

React Bits supports multiple animation libraries:
- **Framer Motion** (default for most)
- **GSAP** (for complex sequences)
- **React Spring** (for physics-based)

## Usage Pattern

```tsx
// Example: Aurora Background
import Aurora from '@/components/backgrounds/Aurora';

export function Hero() {
  return (
    <div className="relative h-screen">
      <Aurora
        colorStops={["#3A29FF", "#FF94B4", "#FF3232"]}
        blend={0.5}
        amplitude={1.0}
        speed={0.5}
      />
      <div className="relative z-10">
        {/* Content */}
      </div>
    </div>
  );
}
```

Visit reactbits.dev for full component code and customization props.
