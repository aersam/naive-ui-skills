# Component Gradient Text (`n-gradient-text`)

Displays text with a gradient color effect.

```vue
<!-- Using built-in types -->
<n-gradient-text type="primary">Primary Gradient</n-gradient-text>
<n-gradient-text type="success" :size="32">Success Large</n-gradient-text>

<!-- Custom gradient -->
<n-gradient-text :gradient="{ from: '#FF6B6B', to: '#4ECDC4', deg: 135 }">
  Custom Colors
</n-gradient-text>

<!-- CSS gradient string -->
<n-gradient-text gradient="linear-gradient(90deg, #f093fb, #f5576c)">
  CSS Gradient
</n-gradient-text>
```

## Props

| Prop | Type | Default |
|------|------|---------|
| `type` | `'primary' \| 'info' \| 'success' \| 'warning' \| 'error'` | `'primary'` |
| `gradient` | `string \| { from: string, to: string, deg: number \| string }` | — |
| `size` | `number \| string` | — |

- `size` as a number is treated as pixels
- `gradient` overrides `type` when set
- `font-size` CSS on the parent also works but may be overridden by `size`

## Slot
- `default` — text content
