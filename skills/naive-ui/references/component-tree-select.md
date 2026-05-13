# Component Tree Select (`n-tree-select`)

Select from a tree-structured dropdown. Like Cascader but designed for arbitrary tree hierarchies where parent nodes are also selectable.

```vue
<!-- Single selection -->
<n-tree-select
  v-model:value="selected"
  :options="treeOptions"
  filterable
/>

<!-- Multiple with checkboxes -->
<n-tree-select
  v-model:value="selected"
  :options="treeOptions"
  multiple
  checkable
  cascade
  check-strategy="child"
  filterable
  :max-tag-count="3"
/>

<!-- Async loading -->
<n-tree-select
  v-model:value="selected"
  :options="treeOptions"
  :on-load="loadChildren"
/>

<!-- File picker pattern (folders not selectable) -->
<n-tree-select
  v-model:value="selected"
  :options="fileTree"
  :override-default-node-click-behavior="({ option }) =>
    option.children ? 'toggleExpand' : 'toggleSelect'"
/>
```

## Option Type

```typescript
interface TreeSelectOption {
  key: string | number       // customizable via key-field
  label: string              // customizable via label-field
  children?: TreeSelectOption[]
  disabled?: boolean
  isLeaf?: boolean           // required for async loading
}
```

## Key Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string \| number \| Array<...> \| null` | — | |
| `options` | `TreeSelectOption[]` | `[]` | |
| `multiple` | boolean | false | Multi-select |
| `checkable` | boolean | false | Checkbox UI |
| `cascade` | boolean | false | Link parent/child checkbox |
| `check-strategy` | `'all' \| 'parent' \| 'child'` | `'all'` | |
| `filterable` | boolean | false | Enable search |
| `filter` | `(pattern, option) => boolean` | — | Custom filter |
| `show-path` | boolean | false | Show hierarchy in label |
| `separator` | string | `' / '` | Path separator |
| `on-load` | `(node) => Promise<void>` | — | Async children loader |
| `allow-checking-not-loaded` | boolean | false | |
| `default-expand-all` | boolean | false | |
| `default-expanded-keys` | array | `[]` | |
| `expanded-keys` | array | — | Controlled expansion |
| `max-tag-count` | `number \| 'responsive'` | — | |
| `indent` | number | 24 | Per-level indent (px) |
| `show-line` | boolean | false | Tree connecting lines (2.44.0) |
| `override-default-node-click-behavior` | function | — | `'toggleExpand'\|'toggleSelect'\|'toggleCheck'\|'default'\|'none'` |
| `render-label` / `render-prefix` / `render-suffix` / `render-switcher-icon` / `render-tag` | functions | — | Custom rendering |
| `key-field` / `label-field` / `disabled-field` / `children-field` | string | defaults | Custom field names |
| `virtual-scroll` | boolean | true | Enabled by default |
| `consistent-menu-width` | boolean | true | Match input width (disables virtual scroll) |
| `size` / `status` / `disabled` / `clearable` / `placeholder` | | | Standard |
| `loading` | boolean | false | |

## Slots
- `header` — menu header area
- `action` — menu action area
- `arrow` — trigger arrow icon
- `empty` — empty state

## Methods
- `focus()`, `blur()`, `focusInput()`, `blurInput()`
- `getCheckedData()` — `{ keys, options }`
- `getIndeterminateData()` — `{ keys, options }`

> **TreeSelect vs Cascader:** Use TreeSelect for hierarchies where parent nodes themselves can be selected, or tree depth varies widely. Cascader is better for strict level-by-level path selection (like region selectors).
