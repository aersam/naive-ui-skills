# Component Heatmap (`n-heatmap`)

GitHub contribution-style calendar heatmap for activity visualization. Available from 2.43.0.

```vue
<script setup>
import { heatmapMockData } from 'naive-ui'

const data = heatmapMockData('recent')   // or heatmapMockData(2024) for specific year
</script>

<template>
  <n-heatmap
    :data="activityData"
    color-theme="green"
    :tooltip="true"
    show-week-labels
    show-month-labels
    show-color-indicator
    size="medium"
  />
</template>
```

## Data Format

```typescript
type HeatmapData = Array<{
  timestamp: number        // Unix timestamp in ms
  value?: number | null    // null = hidden but takes space; undefined = empty cell
}>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `data` | `HeatmapData` | `[]` | Activity data |
| `color-theme` | `'green' \| 'blue' \| 'orange' \| 'purple' \| 'red'` | — | Built-in themes |
| `active-colors` | `string[]` | — | Custom colors light→dark (overrides `color-theme`) |
| `minimum-color` | string | — | Color for zero value (defaults to first of `active-colors`) |
| `first-day-of-week` | `0–6` | 0 | 0=Monday, 6=Sunday |
| `fill-calendar-leading` | boolean | false | Fill grid start (GitHub recent-year style) |
| `loading` | boolean | false | Loading state |
| `loading-data` | `HeatmapData` | — | Data for loading skeleton (`null` value = hidden) |
| `show-color-indicator` | boolean | true | Bottom color scale |
| `show-week-labels` | boolean | true | Row week labels |
| `show-month-labels` | boolean | true | Column month labels |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `tooltip` | `boolean \| TooltipProps` | false | Hover tooltip |
| `x-gap` / `y-gap` | `number \| string` | — | Cell spacing |

## Slots

| Slot | Parameters | Notes |
|------|-----------|-------|
| `footer` | — | Left footer area |
| `indicator` | — | Right color scale area |
| `indicator-leading-text` | — | "Less" text |
| `indicator-trailing-text` | — | "More" text |
| `tooltip` | `{ timestamp, value }` | Custom tooltip content |

## Color Priority
`active-colors` + `minimum-color` have higher priority than `color-theme`. Don't mix them.

## Helper Function
```typescript
import { heatmapMockData } from 'naive-ui'
// heatmapMockData('recent') — last 12 months
// heatmapMockData(2024)     — full year 2024
```
