# Production Quality Standards

Use this checklist to keep Motion components stable, accessible, and fast.

## Component Architecture

- Export variants and transitions as named constants
- Accept `className`, `style`, and `...props` for composition
- Keep motion props close to the animated node to avoid prop drilling
- Avoid non-deterministic values on first render (SSR-safe defaults)

## Motion Tokens

Centralize timing and easing to keep the UI coherent:

```ts
export const motionTokens = {
  duration: { fast: 0.15, base: 0.3, slow: 0.6 },
  ease: {
    standard: [0.22, 1, 0.36, 1],
    enter: [0.16, 1, 0.3, 1],
    exit: [0.4, 0, 1, 1]
  },
  stagger: { sm: 0.04, md: 0.08, lg: 0.12 }
}
```

## Accessibility

- Use `useReducedMotion` to disable non-essential motion
- Never rely on motion alone to convey meaning
- Preserve keyboard focus and visible focus styles

## Performance

- Prefer transform/opacity over layout/paint properties
- Avoid heavy filters or large animated shadows
- Gate heavy effects with `useInView` and `once: true`
- Use `LazyMotion` for large pages or many components

## Responsiveness

- Reduce travel distances and duration on small screens
- Avoid parallax or large scroll effects on mobile

## QA Checklist

- Reduced-motion mode behaves correctly
- Keyboard navigation remains intact
- Motion stays smooth under CPU throttle
- Layout does not shift during animation
