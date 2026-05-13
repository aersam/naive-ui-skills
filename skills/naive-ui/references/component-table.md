# Component Table (`n-table`)

Simple styled HTML table. For complex tables with sorting, filtering, row selection, and virtual scroll — use `n-data-table` instead.

```vue
<n-table :bordered="false" :single-line="false" size="small" striped>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="row in data" :key="row.id">
      <td>{{ row.name }}</td>
      <td>{{ row.age }}</td>
      <td>{{ row.status }}</td>
    </tr>
  </tbody>
</n-table>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `bordered` | boolean | true | Outer border |
| `bottom-bordered` | boolean | true | Bottom border (ignored when `bordered=true`) |
| `single-line` | boolean | true | No column dividers (no right-border on cells) |
| `single-column` | boolean | false | No row dividers (no bottom-border on cells) |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `striped` | boolean | false | Alternating row colors |

## Fine-grained Sub-components

For large tables where you want to reduce Vue's reactivity overhead:

```vue
<n-table>
  <n-thead>
    <n-tr><n-th>Col 1</n-th><n-th>Col 2</n-th></n-tr>
  </n-thead>
  <n-tbody>
    <n-tr v-for="row in data" :key="row.id">
      <n-td>{{ row.a }}</n-td>
      <n-td>{{ row.b }}</n-td>
    </n-tr>
  </n-tbody>
</n-table>
```

Components: `n-thead`, `n-tbody`, `n-tr`, `n-th`, `n-td`
