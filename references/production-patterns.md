# Production Patterns

Short, production-ready Motion patterns for consistent results.

## Tokens + Variants

Use shared tokens and variants to keep motion consistent.

```tsx
import { motion } from "motion/react"
import { motionTokens } from "./motionTokens"

const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      duration: motionTokens.duration.base,
      ease: motionTokens.ease.standard,
      staggerChildren: motionTokens.stagger.md
    }
  }
}

const item = {
  hidden: { opacity: 0, y: 12 },
  show: { opacity: 1, y: 0 }
}

export function StaggeredList({ children }) {
  return (
    <motion.ul variants={container} initial="hidden" animate="show">
      {children}
    </motion.ul>
  )
}
```

## Reduced Motion Fallback

Disable non-essential motion when users prefer reduced motion.

```tsx
import { motion, useReducedMotion } from "motion/react"

export function Reveal({ children }) {
  const reduce = useReducedMotion()

  return (
    <motion.div
      initial={{ opacity: 0, y: reduce ? 0 : 16 }}
      animate={{ opacity: 1, y: 0 }}
      transition={{ duration: reduce ? 0 : 0.3 }}
    >
      {children}
    </motion.div>
  )
}
```

## In-View Gating

Only animate once when the element enters the viewport.

```tsx
import { motion, useInView } from "motion/react"
import { useRef } from "react"

export function InViewReveal({ children }) {
  const ref = useRef(null)
  const inView = useInView(ref, { once: true, margin: "0px 0px -10% 0px" })

  return (
    <motion.section
      ref={ref}
      initial={{ opacity: 0, y: 16 }}
      animate={inView ? { opacity: 1, y: 0 } : {}}
      transition={{ duration: 0.3 }}
    >
      {children}
    </motion.section>
  )
}
```

## LazyMotion Wrapper

Defer Motion features on large pages.

```tsx
import { LazyMotion, domAnimation, m } from "motion/react"

export function MotionRoot({ children }) {
  return <LazyMotion features={domAnimation}>{children}</LazyMotion>
}

export function FadeIn({ children }) {
  return <m.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>{children}</m.div>
}
```
