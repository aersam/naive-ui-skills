# Component Affix (`n-affix`)

Makes content stick to a fixed position when scrolling — like `position: sticky` but more configurable.

```vue
<!-- Stick to top after scrolling 64px -->
<n-affix :trigger-top="64" :top="64">
  <n-menu />
</n-affix>

<!-- Stick to bottom -->
<n-affix :trigger-bottom="20" :bottom="20">
  <n-button>Back to top</n-button>
</n-affix>

<!-- Scoped to a scrollable container -->
<div ref="containerRef" style="overflow-y: auto; height: 400px">
  <n-affix
    :trigger-top="0"
    :top="0"
    position="absolute"
    :listen-to="() => containerRef"
  >
    Sticky header inside container
  </n-affix>
  <!-- Content -->
</div>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `trigger-top` | number | — | Distance from top to trigger top-affix; if not set, uses `top` |
| `top` | number | — | CSS `top` after top-affix triggers; if not set, uses `trigger-top` |
| `trigger-bottom` | number | — | Distance from bottom to trigger bottom-affix |
| `bottom` | number | — | CSS `bottom` after bottom-affix triggers |
| `position` | `'fixed' \| 'absolute'` | `'fixed'` | CSS position type |
| `listen-to` | `string \| HTMLElement \| Document \| Window \| (() => HTMLElement)` | `document` | Scroll container |

> **`position="fixed"` (default):** Works for page-level scroll. Most common use case.
>
> **`position="absolute"`:** Use for scrollable inner containers. Pass the container ref to `listen-to`. The affix's parent must have `position: relative`.
