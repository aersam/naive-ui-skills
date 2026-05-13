# Component Time Picker (`n-time-picker`)

Select time (hours, minutes, seconds) from a scrollable panel.

```vue
<!-- Basic (timestamp value) -->
<n-time-picker v-model:value="timestamp" format="HH:mm:ss" clearable />

<!-- String-based value -->
<n-time-picker
  v-model:formatted-value="timeStr"
  value-format="HH:mm"
  format="HH:mm"
/>

<!-- 12-hour with restrictions -->
<n-time-picker
  v-model:value="ts"
  use-12-hours
  :is-hour-disabled="h => h < 8 || h > 18"
  :actions="['clear', 'now', 'confirm']"
/>

<!-- Step increments -->
<n-time-picker
  v-model:value="ts"
  :hours="1"
  :minutes="15"
  :seconds="0"
/>

<!-- With timezone -->
<n-time-picker v-model:value="ts" time-zone="America/New_York" />
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `number \| null` | — | Unix timestamp (ms) |
| `default-value` | `number \| null` | null | |
| `formatted-value` | `string \| null` | — | String-based control |
| `default-formatted-value` | `string \| null` | — | |
| `value-format` | string | follows `format` | Format for `formatted-value` |
| `format` | string | `'HH:mm:ss'` | Display format (date-fns tokens) |
| `use-12-hours` | boolean | false | 12-hour clock panel |
| `hours` | `number \| number[]` | — | Selectable hours or step |
| `minutes` | `number \| number[]` | — | Selectable minutes or step |
| `seconds` | `number \| number[]` | — | Selectable seconds or step |
| `is-hour-disabled` | `(h) => boolean` | — | Disable specific hours |
| `is-minute-disabled` | `(m, h) => boolean` | — | Disable specific minutes |
| `is-second-disabled` | `(s, m, h) => boolean` | — | Disable specific seconds |
| `actions` | `Array<'clear' \| 'now' \| 'confirm'> \| null` | `['now','confirm']` | Panel actions |
| `time-zone` | string | — | IANA timezone |
| `clearable` / `disabled` | boolean | false | |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `status` | `'success' \| 'warning' \| 'error'` | — | |
| `input-readonly` | boolean | false | Disable keyboard input |
| `placeholder` | string | `'Select Time'` | |
| `placement` | string | `'bottom-start'` | |
| `show` | boolean | — | Controlled panel visibility |

## Events

| Event | Parameters |
|-------|-----------|
| `on-update:value` | `(value, formattedValue)` |
| `on-update:formatted-value` | `(value, timestampValue)` |
| `on-confirm` | `(value, formattedValue)` |
| `on-clear` | `()` |
| `on-update:show` | `(show)` |
| `on-focus` / `on-blur` | `()` |

## Slot
- `icon` — custom clock icon

## Methods
- `focus()`, `blur()`
