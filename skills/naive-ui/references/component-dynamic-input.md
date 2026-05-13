# Component Dynamic Input (`n-dynamic-input`)

Allows users to add/remove/sort items from a list. Originally designed for key-value pairs like environment variables.

```vue
<!-- Simple list of inputs -->
<n-dynamic-input
  v-model:value="list"
  placeholder="Enter value"
  :min="1"
  :max="10"
/>

<!-- Key-value pairs -->
<n-dynamic-input
  v-model:value="pairs"
  preset="pair"
  key-placeholder="Key"
  value-placeholder="Value"
/>

<!-- Custom content -->
<n-dynamic-input
  v-model:value="items"
  :on-create="() => ({ name: '', age: 18 })"
  show-sort-button
>
  <template #default="{ value, index }">
    <div style="display: flex; gap: 8px; width: 100%">
      <n-input v-model:value="value.name" placeholder="Name" />
      <n-input-number v-model:value="value.age" placeholder="Age" :min="0" />
    </div>
  </template>
</n-dynamic-input>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `unknown[]` | — | |
| `default-value` | `unknown[]` | `[]` | |
| `preset` | `'input' \| 'pair'` | `'input'` | Used when no `#default` slot |
| `min` / `max` | number | 0 / ∞ | Item count limits |
| `show-sort-button` | boolean | false | Drag-to-sort buttons |
| `disabled` | boolean | false | Disable all controls (not custom content) |
| `on-create` | `(index) => value` | — | Return initial value for new items |
| `on-remove` | `(index) => void` | — | Removal callback |
| `key-field` | string | — | Key for list rendering |
| `item-style` / `item-class` | | — | Per-item styling |
| `create-button-props` | ButtonProps | — | Customize add button |

### Input preset extra props
- `placeholder` — input placeholder

### Pair preset extra props
- `key-placeholder` / `value-placeholder`

## Slots

| Slot | Parameters | Notes |
|------|-----------|-------|
| `default` | `{ value, index }` | Custom item content |
| `action` | `{ value, index, create, remove, move }` | Custom action buttons |
| `create-button-default` | — | Add button label |
| `create-button-icon` | — | Add button icon |

> **Validation:** `n-dynamic-input` has no built-in form validation. Use `n-form-item` inside the `#default` slot for validated items, passing `:path` dynamically.
