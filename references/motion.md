# Motion (React Animation Library)

**Documentation:** https://motion.dev/docs/react

The successor to Framer Motion. Industry-standard React animation library with 12M+ monthly downloads.

## Table of Contents
- [Core Concepts](#core-concepts)
- [Animation Props](#animation-props)
- [Transitions](#transitions)
- [Gestures](#gestures)
- [Layout Animations](#layout-animations)
- [Scroll Animations](#scroll-animations)
- [Variants](#variants)
- [Orchestration](#orchestration)
- [Common Patterns](#common-patterns)

---

## Core Concepts

### Installation

```bash
npm install motion
```

### Import

```tsx
// Standard React
import { motion } from "motion/react"

// React Server Components (Next.js App Router)
import * as motion from "motion/react-client"
```

### Basic Usage

```tsx
// Animate any HTML/SVG element
<motion.div
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
/>
```

## Animation Props

### initial
Starting state before animation.

```tsx
<motion.div initial={{ opacity: 0, y: 20 }} />
```

### animate
Target state to animate to.

```tsx
<motion.div animate={{ opacity: 1, y: 0 }} />
```

### exit
State when component unmounts (requires AnimatePresence).

```tsx
<AnimatePresence>
  {isVisible && (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
    />
  )}
</AnimatePresence>
```

### Animatable Properties

| Property | Example |
|----------|---------|
| opacity | `{ opacity: 0.5 }` |
| x, y, z | `{ x: 100, y: -50 }` |
| scale | `{ scale: 1.2 }` |
| rotate | `{ rotate: 90 }` |
| skew | `{ skewX: 10 }` |
| backgroundColor | `{ backgroundColor: "#ff0000" }` |
| borderRadius | `{ borderRadius: "50%" }` |
| width, height | `{ width: "100%" }` |

## Transitions

Control how animations play.

```tsx
<motion.div
  animate={{ x: 100 }}
  transition={{
    duration: 0.8,
    ease: "easeInOut",
    delay: 0.2
  }}
/>
```

### Spring Physics

```tsx
<motion.div
  animate={{ scale: 1.2 }}
  transition={{
    type: "spring",
    stiffness: 300,
    damping: 20
  }}
/>
```

### Easing Options

| Easing | Description |
|--------|-------------|
| `"linear"` | Constant speed |
| `"easeIn"` | Slow start |
| `"easeOut"` | Slow end |
| `"easeInOut"` | Slow start and end |
| `"circIn/Out"` | Circular easing |
| `"backIn/Out"` | Overshoot easing |
| `[0.42, 0, 0.58, 1]` | Custom bezier |

## Gestures

### Hover

```tsx
<motion.div
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.95 }}
/>
```

### Drag

```tsx
<motion.div
  drag
  dragConstraints={{ left: 0, right: 300 }}
  dragElastic={0.2}
/>
```

### Focus & Press

```tsx
<motion.button
  whileFocus={{ outline: "2px solid blue" }}
  whileTap={{ scale: 0.95 }}
/>
```

## Layout Animations

Animate between different layouts automatically.

```tsx
<motion.div layout>
  {/* Content that changes size/position */}
</motion.div>
```

### Shared Layout

```tsx
<motion.div layoutId="shared-element">
  {/* Animates between components with same layoutId */}
</motion.div>
```

## Scroll Animations

### Scroll-Triggered

```tsx
import { useInView } from "motion/react"

function Component() {
  const ref = useRef(null)
  const isInView = useInView(ref, { once: true })

  return (
    <motion.div
      ref={ref}
      initial={{ opacity: 0 }}
      animate={isInView ? { opacity: 1 } : {}}
    />
  )
}
```

### Scroll-Linked

```tsx
import { useScroll, useTransform } from "motion/react"

function Parallax() {
  const { scrollYProgress } = useScroll()
  const y = useTransform(scrollYProgress, [0, 1], [0, -200])

  return <motion.div style={{ y }} />
}
```

## Variants

Define animation states and orchestrate children.

```tsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 0.1
    }
  }
}

const item = {
  hidden: { y: 20, opacity: 0 },
  show: { y: 0, opacity: 1 }
}

<motion.ul variants={container} initial="hidden" animate="show">
  <motion.li variants={item} />
  <motion.li variants={item} />
  <motion.li variants={item} />
</motion.ul>
```

## Orchestration

### Stagger Children

```tsx
const container = {
  show: {
    transition: {
      staggerChildren: 0.1,
      delayChildren: 0.3
    }
  }
}
```

### AnimatePresence

Required for exit animations.

```tsx
import { AnimatePresence } from "motion/react"

<AnimatePresence mode="wait">
  {isOpen && (
    <motion.div
      key="modal"
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
    />
  )}
</AnimatePresence>
```

### mode Options
- `"sync"` (default): All animations run simultaneously
- `"wait"`: Wait for exit before enter
- `"popLayout"`: Remove exiting elements from layout flow

## Common Patterns

### Page Transition

```tsx
// In layout.tsx or _app.tsx
<AnimatePresence mode="wait">
  <motion.div
    key={pathname}
    initial={{ opacity: 0, x: -20 }}
    animate={{ opacity: 1, x: 0 }}
    exit={{ opacity: 0, x: 20 }}
    transition={{ duration: 0.3 }}
  >
    {children}
  </motion.div>
</AnimatePresence>
```

### Staggered List

```tsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: { staggerChildren: 0.05 }
  }
}

const item = {
  hidden: { opacity: 0, y: 10 },
  show: { opacity: 1, y: 0 }
}

<motion.ul variants={container} initial="hidden" animate="show">
  {items.map(i => <motion.li key={i} variants={item} />)}
</motion.ul>
```

### Hover Card

```tsx
<motion.div
  whileHover={{ y: -5, boxShadow: "0 10px 30px rgba(0,0,0,0.2)" }}
  transition={{ type: "spring", stiffness: 400 }}
/>
```

### Magnetic Button

```tsx
function MagneticButton({ children }) {
  const [position, setPosition] = useState({ x: 0, y: 0 })

  const handleMouse = (e) => {
    const rect = e.currentTarget.getBoundingClientRect()
    setPosition({
      x: e.clientX - rect.left - rect.width / 2,
      y: e.clientY - rect.top - rect.height / 2
    })
  }

  return (
    <motion.button
      onMouseMove={handleMouse}
      onMouseLeave={() => setPosition({ x: 0, y: 0 })}
      animate={{ x: position.x * 0.3, y: position.y * 0.3 }}
      transition={{ type: "spring", stiffness: 150 }}
    >
      {children}
    </motion.button>
  )
}
```

### Scroll Progress Bar

```tsx
function ScrollProgress() {
  const { scrollYProgress } = useScroll()

  return (
    <motion.div
      className="fixed top-0 left-0 right-0 h-1 bg-blue-500 origin-left"
      style={{ scaleX: scrollYProgress }}
    />
  )
}
```

### Reduced Motion

Always respect user preferences:

```tsx
import { useReducedMotion } from "motion/react"

function Component() {
  const shouldReduceMotion = useReducedMotion()

  return (
    <motion.div
      animate={{ x: shouldReduceMotion ? 0 : 100 }}
    />
  )
}
```

## Implementation Checklist

- Respect `prefers-reduced-motion` with `useReducedMotion` and disable non-essential motion
- Prefer transform/opacity animations; avoid layout and paint-heavy properties
- Gate heavy effects with `useInView` or viewport-based triggers
- Use lazy loading (`LazyMotion` with feature bundles) for large pages when possible
- Keep focus/keyboard interactions intact; do not rely on motion alone
- Validate performance on low-end devices if they are in scope

## Performance Tips

1. **Use transform properties** (x, y, scale, rotate) over layout properties (width, height, top, left)
2. **Use `will-change`** sparingly and remove after animation
3. **Avoid animating many elements** simultaneously
4. **Use `layout` prop** for layout changes instead of animating width/height
5. **Use `layoutId`** for shared element transitions
