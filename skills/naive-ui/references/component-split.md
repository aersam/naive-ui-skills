# Component Split (`n-split`)

Resizable split-pane layout. Available since 2.36.0.

```vue
<!-- Horizontal split (default) -->
<n-split :default-size="0.3" style="height: 500px; border: 1px solid #e0e0e0">
  <template #1>
    <div style="padding: 16px">Left pane (30%)</div>
  </template>
  <template #2>
    <div style="padding: 16px">Right pane (70%)</div>
  </template>
</n-split>

<!-- Vertical split -->
<n-split direction="vertical" :default-size="0.5" :min="0.2" :max="0.8" style="height: 400px">
  <template #1>Top</template>
  <template #2>Bottom</template>
</n-split>

<!-- Pixel-based sizes -->
<n-split default-size="200px" min="100px" max="400px">
  <template #1>Fixed-ish pane</template>
  <template #2>Flexible pane</template>
</n-split>

<!-- Controlled -->
<n-split :size="splitRatio" @update:size="splitRatio = $event">
  <template #1>Left</template>
  <template #2>Right</template>
</n-split>

<!-- Custom drag handle -->
<n-split :default-size="0.5">
  <template #1>Left</template>
  <template #2>Right</template>
  <template #resize-trigger>
    <div style="width: 8px; background: #e0e0e0; cursor: col-resize" />
  </template>
</n-split>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `direction` | `'horizontal' \| 'vertical'` | `'horizontal'` | |
| `default-size` | `number \| string` | 0.5 | Ratio (0–1) or `'${n}px'` |
| `size` | `number \| string` | — | Controlled size |
| `min` | `number \| string` | 0 | Min ratio or px |
| `max` | `number \| string` | 1 | Max ratio or px |
| `disabled` | boolean | false | |
| `resize-trigger-size` | number | 3 | Drag handle size in px |
| `pane1-class` / `pane1-style` | | — | |
| `pane2-class` / `pane2-style` | | — | |
| `watch-props` | `['defaultSize']` | — | Watch for `defaultSize` changes |

## Slots

| Slot | Notes |
|------|-------|
| `1` | First pane content |
| `2` | Second pane content |
| `resize-trigger` | Custom drag handle |

## Events
- `on-drag-start(e)` / `on-drag-move(e)` / `on-drag-end(e)`
- `on-update:size(value)` — value is string if size was set as string
