# Component Ellipsis (`n-ellipsis`, `n-performant-ellipsis`)

Truncates text with a tooltip showing the full content.

```vue
<!-- Single line with tooltip -->
<n-ellipsis style="max-width: 200px">
  Very long text that will be truncated at the container width
</n-ellipsis>

<!-- Multi-line clamp -->
<n-ellipsis :line-clamp="3">
  Long content spanning multiple lines...
</n-ellipsis>

<!-- Click to expand -->
<n-ellipsis :line-clamp="2" expand-trigger="click">
  Clickable to expand truncated text
</n-ellipsis>

<!-- Custom tooltip content -->
<n-ellipsis style="max-width: 200px">
  Some text
  <template #tooltip>
    <div>Rich tooltip content</div>
  </template>
</n-ellipsis>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `line-clamp` | `number \| string` | — | Max lines (CSS `-webkit-line-clamp`) |
| `expand-trigger` | `'click'` | — | Click to expand |
| `tooltip` | `boolean \| TooltipProps` | true | Control tooltip; pass TooltipProps to customize |

## Slots
- `default` — content to display
- `tooltip` — custom tooltip content

## Performance variant

For rendering large numbers of ellipses (e.g., 1000+ in a list), use `n-performant-ellipsis` (since 2.35.0):

```vue
<n-performant-ellipsis style="max-width: 200px">
  Long text...
</n-performant-ellipsis>
```

> **Warning:** Inner components inside `n-performant-ellipsis` may unmount and remount — use with caution when slots contain stateful components.
