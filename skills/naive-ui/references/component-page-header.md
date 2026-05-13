# Component Page Header (`n-page-header`)

Standard page header with back button, breadcrumb, title, subtitle, and action areas.

```vue
<n-page-header
  title="Document Title"
  subtitle="Last edited 2 days ago"
  @back="router.go(-1)"
>
  <template #avatar>
    <n-avatar src="/avatar.png" />
  </template>
  <template #extra>
    <n-space>
      <n-button>Edit</n-button>
      <n-button type="primary">Save</n-button>
    </n-space>
  </template>
  <template #footer>
    <n-descriptions>...</n-descriptions>
  </template>
  Main page content here
</n-page-header>
```

## Props

| Prop | Type | Notes |
|------|------|-------|
| `title` | string | Page title |
| `subtitle` | string | Secondary text below title |
| `extra` | string | Extra text (overridden by `#extra` slot) |
| `on-back` | `() => void` | Show back button and handle click |

## Slots

| Slot | Notes |
|------|-------|
| `avatar` | Avatar/image before title |
| `header` | Custom header area |
| `title` | Custom title content |
| `subtitle` | Custom subtitle |
| `extra` | Right-side actions |
| `default` | Main content area |
| `footer` | Footer below content |
| `back` | Custom back icon (since 2.24.2) |
