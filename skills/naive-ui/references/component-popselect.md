# Component Popselect (`n-popselect`)

Selection options inside a popover — like a lightweight Select without a picker input field.

```vue
<!-- Single selection -->
<n-popselect v-model:value="selected" :options="options" trigger="click">
  <n-button>{{ selected || 'Select option' }}</n-button>
</n-popselect>

<!-- Multiple selection -->
<n-popselect
  v-model:value="multiSelected"
  :options="options"
  multiple
  scrollable
  trigger="hover"
>
  <n-tag>{{ multiSelected.length }} selected</n-tag>
</n-popselect>

<!-- With custom slots -->
<n-popselect :options="options">
  <n-button>Select</n-button>
  <template #header>Choose an option</template>
  <template #empty>No options available</template>
</n-popselect>
```

## Props (extends Popover)

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string \| number \| Array<...> \| null` | null | |
| `options` | `SelectOption[] \| SelectGroupOption[]` | `[]` | See Select for option format |
| `multiple` | boolean | false | |
| `scrollable` | boolean | false | Scrollable option list |
| `virtual-scroll` | boolean | false | For large option lists |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `render-label` | `(option, selected) => VNodeChild` | — | Custom option label |
| `node-props` | `(option) => object` | — | DOM attrs per option |
| `scrollbar-props` | ScrollbarProps | — | |

All Popover props also apply (trigger, placement, delay, etc.).

## Slots
- `default` — trigger element (the element that opens the popselect)
- `header` — menu header (since 2.36.0)
- `action` — menu action area
- `empty` — empty state

## Events
- `on-update:value(value, option)`
