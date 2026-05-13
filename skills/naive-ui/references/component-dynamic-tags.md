# Component Dynamic Tags (`n-dynamic-tags`)

Editable tag list — users can add and remove tags inline.

```vue
<!-- String tags -->
<n-dynamic-tags v-model:value="tags" :max="5" />

<!-- Object tags -->
<n-dynamic-tags
  v-model:value="tags"
  :on-create="(label) => ({ label, value: label.toLowerCase() })"
  :render-tag="(tag, index) => h(NTag, { closable: true, onClose: () => handleClose(index) }, () => tag.label)"
/>

<!-- Custom input trigger -->
<n-dynamic-tags v-model:value="tags">
  <template #trigger="{ activate, disabled }">
    <n-button size="small" :disabled="disabled" @click="activate">+ Add Tag</n-button>
  </template>
</n-dynamic-tags>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string[] \| DynamicTagsOption[]` | — | |
| `default-value` | array | `[]` | |
| `max` | number | — | Max tag count |
| `closable` | boolean | true | Tags have close button |
| `disabled` | boolean | false | |
| `round` | boolean | false | Rounded tags |
| `type` | `'default' \| 'primary' \| 'info' \| 'success' \| 'warning' \| 'error'` | `'default'` | |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `color` | `{ color?, borderColor?, textColor? }` | — | Custom colors |
| `on-create` | `(label) => string \| DynamicTagsOption` | `label => label` | Custom tag factory |
| `render-tag` | `(tag, index) => VNodeChild` | — | Custom tag render |
| `input-props` | InputProps | — | Inner input props |
| `input-class` / `input-style` | | — | Input styling |
| `tag-class` / `tag-style` | | — | Tag styling |

```typescript
interface DynamicTagsOption {
  label: string
  value: string
}
```

## Slots

| Slot | Parameters | Notes |
|------|-----------|-------|
| `input` | `{ submit, deactivate }` | Replace default text input |
| `trigger` | `{ activate, disabled }` | Replace the "add tag" trigger button |
