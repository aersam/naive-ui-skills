# Component Collapse (`n-collapse`, `n-collapse-item`)

Accordion-style collapsible panels.

```vue
<n-collapse v-model:expanded-names="expanded" accordion>
  <n-collapse-item title="Panel 1" name="1">
    Content of panel 1
  </n-collapse-item>
  <n-collapse-item title="Panel 2" name="2">
    <template #header-extra>Extra info</template>
    Content of panel 2
  </n-collapse-item>
  <n-collapse-item title="Disabled" name="3" :disabled="true">
    Disabled panel
  </n-collapse-item>
</n-collapse>
```

## `n-collapse` Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `accordion` | boolean | false | Only one panel open at a time |
| `expanded-names` | `string \| number \| Array<...> \| null` | — | Controlled expanded panels |
| `default-expanded-names` | same | null | Uncontrolled default |
| `arrow-placement` | `'left' \| 'right'` | `'left'` | |
| `display-directive` | `'if' \| 'show'` | `'if'` | DOM retention when inactive |
| `trigger-areas` | `Array<'main' \| 'arrow' \| 'extra'>` | all | Which areas toggle expand |

> **Note:** `default-expanded-names` must always be an array, even for a single panel — unless `accordion` is true.

## `n-collapse-item` Props

| Prop | Type | Default |
|------|------|---------|
| `name` | `string \| number` | random |
| `title` | string | — |
| `disabled` | boolean | false |
| `display-directive` | `'if' \| 'show'` | inherits from collapse |

## Slots

`n-collapse`: `arrow({ collapsed })`

`n-collapse-item`: `default` (content), `header({ collapsed })`, `header-extra({ collapsed })`, `arrow({ collapsed })`

## Events
- `on-update:expanded-names(names)` on `n-collapse`
- `on-item-header-click({ name, expanded, event })` on `n-collapse`
