# Component Mention (`n-mention`)

`@mention` component that triggers suggestion panels in text input.

```vue
<script setup>
const options = ref<MentionOption[]>([])

async function handleSearch(pattern: string, prefix: string) {
  options.value = await searchUsers(pattern)
}
</script>

<template>
  <n-mention
    v-model:value="text"
    :options="options"
    prefix="@"
    @search="handleSearch"
    @select="(option) => console.log('selected:', option.value)"
  />
</template>
```

```vue
<!-- Textarea mode with async load -->
<n-mention
  v-model:value="text"
  :options="options"
  type="textarea"
  :autosize="{ minRows: 3, maxRows: 8 }"
  :loading="isLoading"
  @search="handleSearch"
/>
```

## Option Type

```typescript
interface MentionOption {
  value: string        // Must be unique; used for matching if label is not a string
  label: string | ((option: MentionOption) => VNodeChild)
  disabled?: boolean
  class?: string
  style?: string
  render?: (option: MentionOption) => VNodeChild
}
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string \| null` | — | |
| `options` | `MentionOption[]` | `[]` | |
| `prefix` | `string \| string[]` | `'@'` | Trigger character(s), each exactly 1 char |
| `type` | `'text' \| 'textarea'` | `'text'` | |
| `separator` | string | `' '` | Split character (exactly 1 char) |
| `loading` | boolean | false | Loading state in panel |
| `filter` | `(pattern, option) => boolean` | default | Custom filter |
| `autosize` | `boolean \| { minRows?, maxRows? }` | false | Textarea autosize |
| `render-label` | `(option) => VNodeChild` | — | Custom option label |
| `bordered` | boolean | true | |
| `disabled` / `placeholder` / `size` | | | Standard |
| `status` | `'success' \| 'warning' \| 'error'` | — | |
| `placement` | string | `'bottom-start'` | |

## Events

| Event | Parameters |
|-------|-----------|
| `on-search` | `(pattern, prefix)` |
| `on-select` | `(option, prefix)` |
| `on-update:value` | `(value)` |
| `on-update:show` | `(show)` |
| `on-focus` / `on-blur` | `(FocusEvent)` |

## Slot
- `empty` — no options state

## Methods
- `focus()`, `blur()`
