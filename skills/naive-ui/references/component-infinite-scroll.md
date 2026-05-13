# Component Infinite Scroll (`n-infinite-scroll`)

Scroll container that triggers a load callback when approaching the bottom. Available since 2.38.2.

```vue
<script setup>
const items = ref<Item[]>([])
let page = 1

async function loadMore() {
  const newItems = await fetchPage(page++)
  items.value.push(...newItems)
}
</script>

<template>
  <n-infinite-scroll
    style="height: 400px"
    :distance="10"
    @load="loadMore"
  >
    <n-list>
      <n-list-item v-for="item in items" :key="item.id">
        {{ item.title }}
      </n-list-item>
    </n-list>
  </n-infinite-scroll>
</template>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `distance` | number | 0 | px from bottom to trigger load |
| `on-load` | `() => Promise<void> \| void` | — | Async load callback |
| `scrollbar-props` | Object | — | See Scrollbar props |

## Notes

- Uses `n-scrollbar` internally — set `style="height: ..."` on the component to define scroll area.
- The `on-load` promise must resolve before the next trigger fires.
- For a complex pattern (e.g., loading with a spinner and done state):

```vue
<n-infinite-scroll @load="handleLoad">
  <template v-for="item in items">...</template>
  <div v-if="loading">Loading...</div>
  <div v-if="done">No more items</div>
</n-infinite-scroll>
```
