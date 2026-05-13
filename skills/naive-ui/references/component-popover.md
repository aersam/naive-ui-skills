# Component Popover (`n-popover`)

Pop-up panel anchored to a trigger element. Minimal built-in styles — style it yourself.

```vue
<!-- Hover popover -->
<n-popover trigger="hover" placement="top">
  <template #trigger>
    <n-button>Hover me</n-button>
  </template>
  Popover content goes here
</n-popover>

<!-- Click with header/footer -->
<n-popover trigger="click" :width="280" scrollable>
  <template #trigger><n-button>Click</n-button></template>
  <template #header>Title</template>
  Long scrollable content...
  <template #footer>
    <n-button size="small" @click="popoverRef.setShow(false)">Close</n-button>
  </template>
</n-popover>

<!-- Match trigger width -->
<n-popover trigger="click" width="trigger">
  <template #trigger><n-input /></template>
  Same width as input
</n-popover>

<!-- Manually positioned (no trigger) -->
<n-popover
  ref="pop"
  trigger="manual"
  :show="showPop"
  :x="mouseX"
  :y="mouseY"
>
  <template #trigger><div @contextmenu="onContextMenu" /></template>
  Context menu
</n-popover>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `trigger` | `'hover' \| 'click' \| 'focus' \| 'manual'` | `'hover'` | |
| `show` | boolean | — | Controlled visibility |
| `placement` | 12 positions | `'top'` | top/bottom/left/right + start/end |
| `delay` / `duration` | number | 100 | Hover show/hide delay (ms) |
| `keep-alive-on-hover` | boolean | true | Keep open when hovering popover itself |
| `raw` | boolean | false | No built-in styles |
| `width` | `number \| 'trigger'` | — | Fixed width or match trigger |
| `scrollable` | boolean | false | Scrollable content area |
| `content-style` | | — | Content area style (e.g., `max-height`) |
| `show-arrow` | boolean | true | |
| `arrow-point-to-center` | boolean | false | |
| `overlap` | boolean | false | Overlap trigger element |
| `flip` | boolean | true | Auto-flip when no space |
| `display-directive` | `'if' \| 'show'` | `'if'` | |
| `animated` | boolean | true | Transition animation |
| `to` | `string \| HTMLElement \| false` | `'body'` | Container; `false` = no detach |
| `x` / `y` | number | — | Manual position (requires `trigger="manual"`) |
| `z-index` | number | — | |
| `disabled` | boolean | false | |
| `header-style` / `header-class` | | — | |
| `footer-style` / `footer-class` | | — | |
| `arrow-class` / `arrow-style` / `arrow-wrapper-class` / `arrow-wrapper-style` | | — | |

## Slots
- `trigger` — trigger element
- `header` — popover header
- `default` — popover body
- `footer` — popover footer

## Methods
- `setShow(bool)` — programmatic show/hide in uncontrolled mode
- `syncPosition()` — update position after content changes

## Events
- `on-update:show(value)`
- `on-clickoutside(MouseEvent)`
