# Component Carousel (`n-carousel`)

Slideshow for displaying a sequence of content panels.

```vue
<n-carousel autoplay :interval="3000" show-arrow dot-type="line">
  <img v-for="src in images" :key="src" :src="src" style="width: 100%; height: 200px; object-fit: cover" />
</n-carousel>
```

## Key Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `autoplay` | boolean | false | Auto-advance slides |
| `interval` | number | 5000 | Autoplay interval ms |
| `direction` | `'horizontal' \| 'vertical'` | `'horizontal'` | |
| `effect` | `'slide' \| 'fade' \| 'card' \| 'custom'` | `'slide'` | |
| `slides-per-view` | `'auto' \| number` | 1 | > 1 disables `loop` |
| `space-between` | number | 0 | Gap between slides |
| `loop` | boolean | true | Wrap around; disabled when `slides-per-view` > 1 |
| `show-arrow` | boolean | false | Prev/next buttons |
| `show-dots` | boolean | true | Dot navigation |
| `dot-type` | `'dot' \| 'line'` | `'dot'` | |
| `dot-placement` | `'top' \| 'bottom' \| 'left' \| 'right'` | `'bottom'` | |
| `draggable` | boolean | false | Mouse drag switching |
| `touchable` | boolean | true | Touch drag switching |
| `keyboard` | boolean | false | Keyboard switching (only when dots focused) |
| `mousewheel` | boolean | false | Mousewheel switching |
| `centered-slides` | boolean | false | Center current slide (slide/card effect only) |
| `current-index` | number | — | Controlled current slide |
| `default-index` | number | 0 | Default slide |
| `trigger` | `'click' \| 'hover'` | `'click'` | Dot switching method |
| `transition-style` | object | `{ transitionDuration: '300ms' }` | |
| `transition-props` | TransitionProps | — | Used with `effect="custom"` |
| `next-slide-style` / `prev-slide-style` | object \| string | — | Adjacent card sizes in card mode |

## Events
- `on-update:current-index(currentIndex, lastIndex)`

## Slots
- `default` — slide content
- `arrow({ total, currentIndex, to, prev, next })` — custom arrows
- `dots({ total, currentIndex, to })` — custom dots

## Methods (template ref)
- `to(index)`, `prev()`, `next()`, `getCurrentIndex()`
