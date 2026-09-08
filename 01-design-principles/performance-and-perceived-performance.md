# Performance and Perceived Performance

Fast interfaces feel better, convert more, and retain users longer. But actual speed is only half the story. Perceived performance — how fast a product feels — is equally important.

---

## 1. Speed Targets

| Duration | Perception | Design response |
|----------|------------|-----------------|
| **0–100ms** | Instant. | No separate feedback needed. |
| **100–300ms** | Noticeable, but acceptable. | Button press, immediate state change. |
| **300ms–1s** | User perceives a delay. | Loading spinner or progress. |
| **1–10s** | User is waiting. | Skeleton, progress bar, explanation. |
| **10s+** | User may abandon. | Background processing, progress, cancellation. |

---

## 2. Improving Actual Performance

### Reduce requests

- Combine assets.
- Use lazy loading for images and code.
- Preload critical resources.
- Cache aggressively.

### Optimize assets

- Compress images and video.
- Use modern formats (WebP, AVIF).
- Serve responsive images with `srcset`.
- Minimize and bundle CSS and JavaScript.

### Prioritize visible content

- Inline critical CSS.
- Defer non-critical scripts.
- Use server-side rendering for first paint.
- Preconnect to required origins.

### Efficient code

- Avoid long-running main-thread tasks.
- Use `requestAnimationFrame` for animations.
- Debounce and throttle event handlers.
- Virtualize long lists.

---

## 3. Improving Perceived Performance

### Skeleton screens

Show placeholder layout while content loads. Skeletons make waits feel shorter than spinners when the layout is predictable.

### Optimistic UI

Update the interface immediately, then sync in the background. Roll back on failure.

### Progressive loading

Show low-resolution or partial content first, then enhance.

### Staged content

Load critical content first, then secondary. Let users start reading before everything is ready.

### Keep UI responsive

- Never block the main thread for more than 50ms.
- Use loading states for async operations.
- Give users something to do while waiting.

---

## 4. Feedback During Waits

- For 100–300ms: button state or small spinner.
- For 1–10s: skeleton or determinate progress.
- For 10s+: background task, progress, and cancellation.
- Always: avoid blank screens and silent failures.

---

## 5. Perceived Performance Patterns

| Pattern | Use case |
|---------|----------|
| **Skeleton screens** | Content layout known, data loading. |
| **Progressive image loading** | Images appear blurry, then sharpen. |
| **Optimistic updates** | Like, toggle, send with fast apparent response. |
| **Staged content** | Show text before images, critical before secondary. |
| **Predictive prefetch** | Load likely next pages in the background. |
| **Activity indicators** | Long tasks with uncertain duration. |

---

## 6. Mobile Performance

- Reduce image and video weight.
- Minimize JavaScript on first load.
- Use native controls where possible.
- Test on real devices and slow networks.
- Use device memory and battery efficiently.

---

## 7. Accessibility

- Honor `prefers-reduced-motion`.
- Avoid auto-playing media.
- Keep loading indicators accessible to screen readers.
- Do not rely on animation to convey essential meaning.

---

## 8. Metrics

- **Largest Contentful Paint (LCP)**: main content loads.
- **First Input Delay (FID) / Interaction to Next Paint (INP)**: responsiveness.
- **Cumulative Layout Shift (CLS)**: visual stability.
- **Time to First Byte (TTFB)**: server response.
- **Speed Index**: how quickly content is visible.

---

## 9. Common Mistakes

- Showing spinners for fast operations.
- Leaving blank screens during loading.
- Loading everything before showing anything.
- Heavy images and unoptimized assets.
- Blocking interactions during loading.
- Not testing on slow devices or networks.
- Ignoring layout shift.

---

## 10. Checklist

- [ ] Critical content loads quickly.
- [ ] Images and assets are optimized.
- [ ] Loading states match the wait time.
- [ ] Skeletons are used for predictable layouts.
- [ ] Optimistic UI is used for reversible actions.
- [ ] Layout is stable while loading.
- [ ] Mobile and slow networks are tested.
- [ ] Performance metrics are monitored.
- [ ] Animations respect reduced motion.
- [ ] No blank or silent loading states.
