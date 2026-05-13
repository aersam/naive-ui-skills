# Component Thing (`n-thing`)

Flexible layout for describing an entity — like a rich list item with avatar, title, description, content, and action areas.

```vue
<n-thing content-indented>
  <template #avatar>
    <n-avatar round :src="user.avatar" />
  </template>
  <template #header>{{ user.name }}</template>
  <template #header-extra>
    <n-tag size="small">Admin</n-tag>
  </template>
  <template #description>Software Engineer</template>

  Main content or biography text here.

  <template #footer>
    <n-space>
      <n-button size="small">Message</n-button>
      <n-button size="small" type="primary">Follow</n-button>
    </n-space>
  </template>
  <template #action>
    <n-button text>···</n-button>
  </template>
</n-thing>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `content-indented` | boolean | false | Indent content to align with avatar |
| `title` | string | — | Overridden by `#header` slot |
| `title-extra` | string | — | Overridden by `#header-extra` slot |
| `description` | string | — | Overridden by `#description` slot |
| `content` | string | — | Overridden by `#default` slot |
| `content-style` / `content-class` | | — | Style the content area |
| `description-style` / `description-class` | | — | Style the description area |

## Slots

| Slot | Notes |
|------|-------|
| `avatar` | Left avatar/icon area |
| `header` | Title text |
| `header-extra` | Right of title (e.g., badge, tag) |
| `description` | Subtitle below title |
| `default` | Main content body |
| `footer` | Below content (actions, metadata) |
| `action` | Top-right actions (e.g., menu button) |
