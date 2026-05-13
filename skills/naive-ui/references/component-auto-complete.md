# Component Auto Complete (`n-auto-complete`)

Input with suggestion dropdown for search/autocomplete.

```vue
<script setup>
const value = ref('')
const options = computed(() =>
  ['gmail.com', 'yahoo.com', 'outlook.com'].map(suffix => ({
    label: `${value.value}@${suffix}`,
    value: `${value.value}@${suffix}`
  }))
)
</script>

<template>
  <n-auto-complete
    v-model:value="value"
    :options="options"
    placeholder="Enter email"
    clearable
  />
</template>
```

## Options Format

```typescript
// Simple strings
options: string[]

// Option objects
interface AutoCompleteOption {
  label: string
  value: string
  disabled?: boolean
}

// Grouped options
interface AutoCompleteGroupOption {
  type: 'group'
  label: string
  key: string | number
  children: Array<string | AutoCompleteOption>
}
```

## Key Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | string | — | v-model |
| `options` | array | `[]` | Suggestion list |
| `clearable` | boolean | false | |
| `disabled` | boolean | false | |
| `loading` | boolean | false | Show loading spinner |
| `placeholder` | string | `'Please Input'` | |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `status` | `'success' \| 'warning' \| 'error'` | — | Validation status |
| `blur-after-select` | boolean | false | Blur after selecting option |
| `clear-after-select` | boolean | false | Clear input after selecting |
| `get-show` | `(value) => boolean` | — | Control menu visibility on focus |
| `append` | boolean | false | Append selected to input instead of replace |
| `show-empty` | boolean | false | Show menu when no options |
| `placement` | string | `'bottom-start'` | |
| `render-label` | `(option, selected) => VNodeChild` | — | Custom option label |
| `render-option` | `(info) => VNodeChild` | — | Custom option wrapper |
| `input-props` | InputHTMLAttributes | — | Attrs for inner input element |

## Slots
- `default({ handleInput, handleFocus, handleBlur, value, theme })` — custom input element
- `prefix` / `suffix` — input prefix/suffix
- `empty` — empty state content

## Methods
- `focus()`, `blur()`
