# Component QR Code (`n-qr-code`)

Generates QR codes as canvas or SVG. Available since 2.36.0.

```vue
<!-- Basic -->
<n-qr-code value="https://example.com" :size="150" />

<!-- With center icon -->
<n-qr-code
  value="https://example.com"
  :size="200"
  :icon-src="logoUrl"
  :icon-size="40"
  error-correction-level="H"
/>

<!-- Custom colors -->
<n-qr-code
  value="https://example.com"
  color="#1a1a2e"
  background-color="#ffffff"
/>

<!-- SVG for download -->
<n-qr-code ref="qrRef" value="..." type="svg" />
<n-button @click="download">Download</n-button>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | string | `''` | Text/URL to encode |
| `size` | number | 100 | QR code size in px |
| `color` | string | `'#000'` | Foreground color (hex) |
| `background-color` | string | `'#FFF'` | Background color (hex) |
| `error-correction-level` | `'L' \| 'M' \| 'Q' \| 'H'` | `'M'` | |
| `type` | `'canvas' \| 'svg'` | `'canvas'` | Output format |
| `padding` | `number \| string` | 12 | Padding around QR |
| `icon-src` | string | — | Center icon URL |
| `icon-size` | number | 40 | Center icon size |
| `icon-background-color` | string | `'#FFF'` | Icon background |
| `icon-border-radius` | number | 4 | Icon bg border-radius |

## Error Correction Levels

| Level | Recovery |
|-------|---------|
| `L` | ~7% |
| `M` | ~15% (default) |
| `Q` | ~25% |
| `H` | ~30% |

Higher levels = more tolerant to damage/obstruction (e.g., center icons) but denser QR code. Use `H` when placing an icon overlay.
