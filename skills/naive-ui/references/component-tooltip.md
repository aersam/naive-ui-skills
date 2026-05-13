# Component Tooltip (`n-tooltip`)

Simple text hint that appears near a trigger element on hover/click. Like Popover but with built-in dark styling for short text.

```vue
<!-- Basic hover tooltip -->
<n-tooltip trigger="hover">
  <template #trigger>
    <n-button>Hover me</n-button>
  </template>
  Tooltip text here
</n-tooltip>

<!-- Different placements -->
<n-tooltip placement="right" trigger="hover">
  <template #trigger><n-icon /></template>
  Right-side tooltip
</n-tooltip>

<!-- No arrow -->
<n-tooltip :show-arrow="false" trigger="hover">
  <template #trigger><span>Text</span></template>
  Clean tooltip
</n-tooltip>

<!-- Controlled -->
<n-tooltip :show="showTip" trigger="manual">
  <template #trigger><div @mouseenter="showTip = true" @mouseleave="showTip = false" /></template>
  Manual tooltip
</n-tooltip>
```

## Notes

Tooltip inherits all **Popover** props and slots — see `component-popover.md` for the full prop reference.

Key differences from Popover:
- Pre-styled with themed dark background and white text
- No built-in `#header` / `#footer` slots in practice (though they exist via inheritance)
- Best for short, simple text hints; use Popover for rich content

Common props:
- `trigger` — `'hover' | 'click' | 'focus' | 'manual'`
- `placement` — any of 12 positions
- `delay` / `duration` — hover show/hide delay
- `show-arrow` — default true
- `disabled` — prevent tooltip from showing
