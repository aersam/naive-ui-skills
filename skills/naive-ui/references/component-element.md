# Component Element (`n-element`)

Renders a DOM element with Naive UI theme CSS variables applied as CSS custom properties, making them available for use in plain CSS/styles.

```vue
<!-- Access theme vars via CSS custom properties -->
<n-element tag="div" :style="{ padding: '16px' }">
  <span :style="{ color: 'var(--n-text-color)' }">
    Themed text
  </span>
  <div :style="{ background: 'var(--n-primary-color)' }">
    Primary background
  </div>
</n-element>
```

## Props

| Prop | Type | Default |
|------|------|---------|
| `tag` | string | `'div'` |

## Slot
- `default` — content

## Notes

`n-element` exposes theme tokens as CSS custom properties (like `--n-text-color`, `--n-primary-color`, `--n-border-color`) on the DOM element, so descendants can reference them in CSS.

For accessing theme variables **in JavaScript/TypeScript**, use `useThemeVars()` instead (see `core-theme.md`):

```typescript
import { useThemeVars } from 'naive-ui'
const themeVars = useThemeVars()
// themeVars.value.primaryColor, themeVars.value.textColor1, etc.
```
