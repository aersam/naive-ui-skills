# Component Marquee (`n-marquee`)

Horizontally scrolling content container. Available since 2.40.2.

```vue
<!-- Text marquee -->
<n-marquee :speed="60">
  Breaking news: Naive UI ships a marquee component!
</n-marquee>

<!-- Auto-fill blank space -->
<n-marquee auto-fill :speed="40">
  <span style="padding: 0 32px">Item A</span>
  <span style="padding: 0 32px">Item B</span>
  <span style="padding: 0 32px">Item C</span>
</n-marquee>

<!-- Image/logo strip -->
<n-marquee auto-fill>
  <img v-for="logo in logos" :key="logo.id" :src="logo.url" style="height: 40px; margin: 0 24px" />
</n-marquee>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `speed` | number | 48 | Scroll speed in pixels/second |
| `auto-fill` | boolean | false | Repeat content to fill container width |

## Slot
- `default` — any content (text, images, components)

> The component scrolls content indefinitely. Use `auto-fill` to prevent empty gaps when content is shorter than the container width.
