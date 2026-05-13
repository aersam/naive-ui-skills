# Component Drawer (`n-drawer`, `n-drawer-content`)

Side panel that slides in from a screen edge. Similar to Modal but positioned at an edge.

```vue
<n-button @click="show = true">Open Drawer</n-button>

<n-drawer v-model:show="show" :width="400" placement="right">
  <n-drawer-content title="Settings" closable>
    <p>Drawer body content</p>
    <template #footer>
      <n-space justify="end">
        <n-button @click="show = false">Cancel</n-button>
        <n-button type="primary" @click="save">Save</n-button>
      </n-space>
    </template>
  </n-drawer-content>
</n-drawer>
```

## `n-drawer` Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `show` | boolean | false | v-model |
| `placement` | `'top' \| 'right' \| 'bottom' \| 'left'` | `'right'` | |
| `width` | `number \| string` | — | For left/right placement |
| `height` | `number \| string` | — | For top/bottom placement |
| `default-width` | `number \| string` | 251 | Used with `resizable` |
| `default-height` | `number \| string` | 251 | Used with `resizable` |
| `resizable` | boolean | false | Drag-to-resize; set `default-width`/`default-height` |
| `min-width` / `max-width` | number | — | Resize constraints |
| `min-height` / `max-height` | number | — | Resize constraints |
| `mask-closable` | boolean | true | Close on mask click |
| `close-on-esc` | boolean | true | Close on Esc |
| `native-scrollbar` | boolean | true | **Keep true** when using `n-drawer-content` |
| `display-directive` | `'if' \| 'show'` | `'if'` | DOM retention |
| `show-mask` | `boolean \| 'transparent'` | true | `false` disables focus trap |
| `trap-focus` | boolean | true | |
| `block-scroll` | boolean | true | |
| `auto-focus` | boolean | true | |
| `to` | `string \| HTMLElement` | `'body'` | Container; for scoped drawers also set `:trap-focus="false" :block-scroll="false"` |
| `content-style` / `content-class` | | — | Scroll container styling |
| `z-index` | number | — | |

## `n-drawer-content` Props

| Prop | Type | Default |
|------|------|---------|
| `title` | string | — |
| `closable` | boolean | false |
| `native-scrollbar` | boolean | true |
| `header-style` / `header-class` | | — |
| `body-style` / `body-class` | | — |
| `body-content-style` / `body-content-class` | | — |
| `footer-style` / `footer-class` | | — |
| `scrollbar-props` | ScrollbarProps | — |

## Slots

`n-drawer`: `default`

`n-drawer-content`: `default` (body), `header`, `footer`

## Events

| Event | Notes |
|-------|-------|
| `on-update:show` | |
| `on-after-enter` | After open animation |
| `on-after-leave` | After close animation |
| `on-esc` | Esc pressed while focused |
| `on-mask-click` | Mask clicked |
| `on-update:width` / `on-update:height` | Resizable drawer |

> **Critical:** Always keep `n-drawer`'s `native-scrollbar="true"` (the default) when using `n-drawer-content`.
