# Component Transfer (`n-transfer`)

Dual-list component for moving items between a source list and a target list. Available since 2.32.0.

```vue
<n-transfer
  v-model:value="selectedKeys"
  :options="options"
  source-filterable
  target-filterable
  :virtual-scroll="true"
/>
```

## Option Type

```typescript
interface TransferOption {
  label: string
  value: string | number
  disabled?: boolean
}
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `Array<string \| number> \| null` | — | Selected (target) keys |
| `default-value` | array | null | |
| `options` | `TransferOption[]` | `[]` | All available items |
| `source-filterable` | boolean | false | Search in source list |
| `target-filterable` | boolean | false | Search in target list |
| `source-filter-placeholder` | string | — | |
| `target-filter-placeholder` | string | — | |
| `source-title` | `string \| () => VNodeChild` | — | Source panel title |
| `target-title` | `string \| () => VNodeChild` | — | Target panel title |
| `filter` | `(pattern, option, from) => boolean` | label match | Custom filter |
| `render-source-label` | `(props) => VNodeChild` | — | Custom source item label |
| `render-target-label` | `(props) => VNodeChild` | — | Custom target item label |
| `render-source-list` | `(props) => VNodeChild` | — | Full custom source list |
| `render-target-list` | `(props) => VNodeChild` | — | Full custom target list |
| `show-selected` | boolean | true | Show selected items in source |
| `virtual-scroll` | boolean | false | Enable for large datasets |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `disabled` | boolean | true | |
| `select-all-text` / `clear-text` | string | — | Button labels |

## Events
- `on-update:value(value[])`

> **Note:** Use `n-transfer` (2.32.0+). Legacy `n-legacy-transfer` will be removed in the next major version.

> For large datasets, always enable `virtual-scroll` — the component renders all items by default.
