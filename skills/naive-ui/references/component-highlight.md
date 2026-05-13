# Component Highlight (`n-highlight`)

Highlights matching substrings within text — like search result highlighting. Available since 2.40.0.

```vue
<!-- Basic -->
<n-highlight
  text="Naive UI is a Vue3 component library"
  :patterns="[searchTerm]"
/>

<!-- Case-sensitive -->
<n-highlight
  text="TypeScript and typescript are different"
  :patterns="['TypeScript']"
  case-sensitive
/>

<!-- Custom highlight style -->
<n-highlight
  :text="content"
  :patterns="keywords"
  :highlight-style="{ backgroundColor: 'yellow', color: 'black' }"
  highlight-class="my-highlight"
/>

<!-- Custom HTML tag -->
<n-highlight
  text="Find the match"
  :patterns="['match']"
  highlight-tag="strong"
/>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `text` | string | — | Full text to display |
| `patterns` | `string[]` | — | Substrings to highlight |
| `case-sensitive` | boolean | false | Case-sensitive matching |
| `auto-escape` | boolean | true | Auto-escape regex special chars in patterns; set `false` to use patterns as raw regex |
| `highlight-tag` | string | `'mark'` | HTML tag for highlighted text |
| `highlight-class` | string | — | CSS class for highlighted spans |
| `highlight-style` | `Object \| string` | — | Inline style for highlighted spans |

> When `auto-escape=true` (default), a pattern like `(foo)` matches the literal string `(foo)`. When `auto-escape=false`, it's treated as a regex capturing group. Leave the default unless you specifically need regex patterns.
