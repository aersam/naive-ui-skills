# Component Scrollbar (`n-scrollbar`)

Custom-styled scrollbar container. Visually consistent with the theme but slightly less reliable than native scrollbars.

```vue
<!-- Vertical scroll -->
<n-scrollbar style="max-height: 300px">
  <div v-for="i in 100" :key="i" style="padding: 8px">Item {{ i }}</div>
</n-scrollbar>

<!-- Horizontal scroll -->
<n-scrollbar x-scrollable style="max-width: 400px">
  <div style="white-space: nowrap; width: 800px">Wide content</div>
</n-scrollbar>

<!-- Always visible scrollbar -->
<n-scrollbar trigger="none" style="height: 200px">
  Content
</n-scrollbar>

<!-- Programmatic scroll -->
<n-scrollbar ref="scrollRef" style="height: 300px">
  Content
</n-scrollbar>
<n-button @click="scrollRef.scrollTo({ top: 0, behavior: 'smooth' })">
  Back to top
</n-button>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `trigger` | `'hover' \| 'none'` | `'hover'` | `'none'` = always visible |
| `x-scrollable` | boolean | false | Enable horizontal scroll |
| `x-placement` | `'top' \| 'bottom'` | `'bottom'` | Horizontal scrollbar position |
| `y-placement` | `'left' \| 'right'` | `'right'` | Vertical scrollbar position |
| `content-style` | `string \| object` | — | Style for inner content div |
| `content-class` | string | — | Class for inner content div |
| `size` | number | — | Scrollbar thickness in px |

## Methods (template ref)

```typescript
scrollTo(options: { left?: number, top?: number, behavior?: ScrollBehavior }): void
scrollTo(x: number, y: number): void
scrollBy(options: { left?: number, top?: number, behavior?: ScrollBehavior }): void
scrollBy(x: number, y: number): void
```

## Events
- `on-scroll(event)`

## Known Issue

When the last child element has `margin-bottom`, mouse-dragging the scrollbar cannot reach the bottom (browser behavior). Fix:

```vue
<n-scrollbar content-style="overflow: hidden;">
  <div style="margin-bottom: 90px">Last item</div>
</n-scrollbar>
```

## Usage in Other Components

Many Naive UI components accept `scrollbar-props` to configure their internal scrollbar:

```vue
<n-select :scrollbar-props="{ trigger: 'none' }" />
<n-data-table :scrollbar-props="{ xScrollable: true }" />
```
