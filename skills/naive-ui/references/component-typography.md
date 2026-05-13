# Component Typography

Themed text components: `n-text`, `n-p`, `n-h1`–`n-h6`, `n-ul`, `n-ol`, `n-li`, `n-a`, `n-blockquote`, `n-hr`

```vue
<n-h1 prefix="bar">Section Heading</n-h1>
<n-h2>Subheading</n-h2>

<n-p>Regular paragraph text.</n-p>
<n-p depth="3">De-emphasized paragraph.</n-p>

<n-text type="success" strong>Bold success text</n-text>
<n-text italic underline>Italic underlined</n-text>
<n-text delete>Strikethrough</n-text>
<n-text code>inline code</n-text>
<n-text depth="2">Secondary depth</n-text>

<n-ul>
  <li>Item 1</li>
  <li>Item 2</li>
</n-ul>

<n-blockquote>A quoted passage.</n-blockquote>

<!-- Router link via n-a -->
<n-a :href="href" @click.prevent="router.push(href)">Link text</n-a>
```

## `n-text` Props

| Prop | Type | Default |
|------|------|---------|
| `type` | `'default' \| 'success' \| 'info' \| 'warning' \| 'error'` | `'default'` |
| `strong` | boolean | false |
| `italic` | boolean | false |
| `underline` | boolean | false |
| `delete` | boolean | false |
| `code` | boolean | false |
| `depth` | `1 \| 2 \| 3` | — |
| `tag` | string | — (overridden by `code`/`delete`) |

## `n-h1`–`n-h6` Props

| Prop | Type | Notes |
|------|------|-------|
| `type` | same as n-text | |
| `prefix` | `'bar'` | Left bar decoration |
| `align-text` | boolean | |

## `n-p` Props
- `depth` — `1 | 2 | 3`

## `n-ul` / `n-ol` Props
- `align-text` — boolean

## All Slots
- `default` — text/content
