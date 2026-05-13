# Component Cascader (`n-cascader`)

Multi-level selection from tree-structured data. Use for hierarchical categories (country/province/city, department/team, etc.).

```vue
<!-- Single selection -->
<n-cascader
  v-model:value="selected"
  :options="options"
  show-path
  filterable
/>

<!-- Multiple with async loading -->
<n-cascader
  v-model:value="selected"
  :options="options"
  multiple
  cascade
  check-strategy="child"
  remote
  :on-load="loadChildren"
  filterable
/>
```

## Option Type

```typescript
interface CascaderOption {
  label: string
  value: string | number
  disabled?: boolean
  children?: CascaderOption[]
}
```

## Key Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string \| number \| Array<...> \| null` | — | |
| `options` | `CascaderOption[]` | `[]` | |
| `multiple` | boolean | false | Multi-select |
| `cascade` | boolean | true | Link parent/child checkbox state |
| `check-strategy` | `'all' \| 'parent' \| 'child'` | `'all'` | How to display checked nodes |
| `filterable` | boolean | false | Enable search |
| `filter` | function | string match | Custom filter `(pattern, option, path) => boolean` |
| `expand-trigger` | `'click' \| 'hover'` | `'click'` | (hover doesn't work with `remote`) |
| `remote` | boolean | false | Async loading mode |
| `on-load` | `(option) => Promise<void>` | — | Set `option.children` in promise |
| `show-path` | boolean | true | Show selected as full path |
| `separator` | string | `' / '` | Path separator |
| `max-tag-count` | `number \| 'responsive'` | — | Multiple mode tag limit |
| `allow-checking-not-loaded` | boolean | false | Check before load (value may be incomplete) |
| `virtual-scroll` | boolean | true | For large datasets |
| `clearable` / `disabled` / `size` / `status` | | | Standard |
| `label-field` / `value-field` / `children-field` / `disabled-field` | string | defaults | Custom field names |
| `render-label` | `(option, checked) => VNodeChild` | — | Custom label |
| `render-prefix` / `render-suffix` | function | — | Custom option prefix/suffix |
| `placement` | string | `'bottom-start'` | |
| `clear-filter-after-select` | boolean | true | Clear search after select in multiple mode |

## Slots
- `action` — action area in menu
- `arrow` — custom arrow icon
- `empty` — empty state
- `not-found` — no search results

## Methods
- `focus()`, `blur()`
- `getCheckedData()` — `{ keys, options }`
- `getIndeterminateData()` — `{ keys, options }`
