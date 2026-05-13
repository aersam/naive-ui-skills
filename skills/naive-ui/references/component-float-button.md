# Component Float Button (`n-float-button`, `n-float-button-group`)

Floating action button. Like BackTop but more versatile. Available since 2.38.0.

```vue
<!-- Simple float button -->
<n-float-button :right="24" :bottom="24" @click="scrollToTop">
  <n-icon><ArrowUpOutline /></n-icon>
</n-float-button>

<!-- With description -->
<n-float-button :right="24" :bottom="80" type="primary">
  <n-icon><AddOutline /></n-icon>
  <template #description>New</template>
</n-float-button>

<!-- Group with expandable menu -->
<n-float-button :right="24" :bottom="24" menu-trigger="hover">
  <n-icon><MenuOutline /></n-icon>
  <template #menu>
    <n-float-button @click="action1">
      <n-icon><HomeOutline /></n-icon>
    </n-float-button>
    <n-float-button @click="action2">
      <n-icon><SettingsOutline /></n-icon>
    </n-float-button>
  </template>
</n-float-button>

<!-- Container group -->
<n-float-button-group :right="24" :bottom="100" shape="square">
  <n-float-button><n-icon><HomeOutline /></n-icon></n-float-button>
  <n-float-button><n-icon><SearchOutline /></n-icon></n-float-button>
</n-float-button-group>
```

## `n-float-button` Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `position` | `'fixed' \| 'absolute' \| 'relative'` | `'fixed'` | CSS position |
| `right` / `left` / `top` / `bottom` | `number \| string` | — | Position offsets |
| `width` / `height` | `number \| string` | 40 / 40 | Button dimensions |
| `shape` | `'circle' \| 'square'` | `'circle'` | |
| `type` | `'default' \| 'primary'` | `'default'` | |
| `menu-trigger` | `'click' \| 'hover'` | — | Show submenu trigger |
| `show-menu` | boolean | — | Controlled menu visibility |

## `n-float-button-group` Props
Same positioning props (`position`, `right`, `left`, `top`, `bottom`, `shape`).

## Slots
- `default` — icon content
- `description` — label shown below icon
- `menu` — submenu float buttons

## Events
- `on-update:show-menu(value)` — submenu open/close
