# Component Icon (`n-icon`, `n-icon-wrapper`)

Renders SVG icons. Recommended icon library: [xicons](https://www.xicons.org/).

```vue
<script setup>
import { CashOutline, SettingsOutline } from '@vicons/ionicons5'
</script>

<template>
  <!-- Using component prop -->
  <n-icon :component="CashOutline" size="24" color="#18a058" />

  <!-- Using default slot -->
  <n-icon size="24" :depth="3">
    <SettingsOutline />
  </n-icon>

  <!-- Icon with background wrapper -->
  <n-icon-wrapper :size="48" :border-radius="8" color="#18a058" icon-color="white">
    <n-icon size="24">
      <CashOutline />
    </n-icon>
  </n-icon-wrapper>
</template>
```

## `n-icon` Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `component` | Component | — | Icon component to render (alternative to slot) |
| `size` | `number \| string` | — | Number = px |
| `color` | string | — | Icon color |
| `depth` | `1 \| 2 \| 3 \| 4 \| 5` | — | Color depth matching text depth levels |

## `n-icon-wrapper` Props (since 2.25.0)

| Prop | Type | Default |
|------|------|---------|
| `size` | number | 24 |
| `border-radius` | number | 6 |
| `color` | string | — (background color) |
| `icon-color` | string | — |

## Slot
- `default` — SVG icon component

> Make sure the SVG has a `viewBox` attribute set for correct rendering when using custom SVGs.
