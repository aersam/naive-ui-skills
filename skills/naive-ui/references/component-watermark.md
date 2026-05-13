# Component Watermark (`n-watermark`)

Overlays text or image watermarks on content.

```vue
<!-- Text watermark -->
<n-watermark
  content="Confidential"
  :font-size="14"
  font-color="rgba(128,128,128,.3)"
  :rotate="-15"
  :x-gap="80"
  :y-gap="80"
  cross
>
  <div>Protected content here</div>
</n-watermark>

<!-- Multiline text (since 2.38.2) -->
<n-watermark :content="'Line 1\nLine 2'" />

<!-- Image watermark -->
<n-watermark :image="logoUrl" :image-width="120" :image-height="40" />

<!-- Fullscreen -->
<n-watermark content="Draft" fullscreen />
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `content` | string | — | Text; `\n` for multiline (2.38.2+) |
| `image` | string | — | Image URL (mind CORS) |
| `image-width` / `image-height` | number | — | |
| `image-opacity` | number | 1 | |
| `rotate` | number | 0 | Per-tile rotation degrees |
| `global-rotate` | number | 0 | Global rotation (2.32.0) |
| `cross` | boolean | false | Fill at cross positions |
| `fullscreen` | boolean | false | Cover entire viewport |
| `font-size` | number | 14 | |
| `font-color` | string | `rgba(128,128,128,.3)` | |
| `font-weight` | number | 400 | |
| `font-style` | string | `'normal'` | `'italic'`, `oblique Ndeg` |
| `font-family` | string | — | |
| `font-variant` | string | `''` | |
| `line-height` | number | 14 | |
| `width` / `height` | number | 32 | Tile dimensions |
| `x-gap` / `y-gap` | number | 0 | Spacing between tiles |
| `x-offset` / `y-offset` | number | 0 | Position offset |
| `text-align` | `'left' \| 'center' \| 'right'` | `'left'` | Multiline text alignment |
| `selectable` | boolean | true | Whether covered content is selectable |
| `z-index` | number | 10 | |
| `debug` | boolean | false | Show debug grid |

## Slot
- `default` — the content to watermark over
