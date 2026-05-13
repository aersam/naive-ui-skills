# Component Collapse Transition (`n-collapse-transition`)

Animated height transition for showing/hiding content — the animation primitive used by `n-collapse`.

```vue
<script setup>
const show = ref(false)
</script>

<template>
  <n-button @click="show = !show">
    {{ show ? 'Hide' : 'Show' }}
  </n-button>
  <n-collapse-transition :show="show">
    <div style="padding: 16px; background: #f5f5f5">
      Content that slides in and out with a smooth height animation.
    </div>
  </n-collapse-transition>
</template>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `show` | boolean | true | Whether to show content |
| `appear` | boolean | false | Play animation on first mount |

## Slot
- `default` — content to animate

> Use when you need the collapse/expand animation without the full `n-collapse` panel structure — e.g., custom accordions, collapsible filter panels, or expandable form sections.
