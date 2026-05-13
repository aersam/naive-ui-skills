# Core Config Provider (`n-config-provider`)

Sets global theme, locale, namespace, and component defaults for all child components. Typically placed at the app root.

```vue
<script setup>
import { darkTheme, zhCN, dateZhCN } from 'naive-ui'
const isDark = ref(false)
</script>

<template>
  <n-config-provider
    :theme="isDark ? darkTheme : null"
    :locale="zhCN"
    :date-locale="dateZhCN"
    :component-options="{ Button: { size: 'small' }, DataTable: { size: 'small' } }"
  >
    <n-global-style />
    <App />
  </n-config-provider>
</template>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `theme` | `Theme \| null \| undefined` | — | `null`=light, `undefined`=inherit from parent |
| `theme-overrides` | `ThemeOverrides \| null \| undefined` | — | Partial token overrides; `null`=clear, `undefined`=inherit |
| `locale` | `Locale \| null \| undefined` | — | Language; `null`=en-US, `undefined`=inherit |
| `date-locale` | `DateLocale \| null \| undefined` | — | Date language |
| `namespace` | string | — | Class added to detached DOM (dropdowns, modals) |
| `cls-prefix` | string | — | Component class prefix (non-reactive; 2.40.0) |
| `abstract` | boolean | false | No wrapper DOM element |
| `tag` | string | `'div'` | Wrapper element tag |
| `inline-theme-disabled` | boolean | false | Disable inline CSS vars (good for SSR/devtools); non-reactive; avoid if you change `theme-overrides` frequently |
| `preflight-style-disabled` | boolean | false | Disable global CSS resets |
| `component-options` | `GlobalComponentConfig` | — | Default props per component |
| `breakpoints` | object | standard | Grid responsive breakpoints (non-reactive) |
| `style-mount-target` | ParentNode | — | Where `<style>` elements mount (non-reactive) |
| `katex` | object | — | katex instance for `n-equation` |

## GlobalComponentConfig

Set default `size` and other props for all instances of a component:

```typescript
<n-config-provider :component-options="{
  Button: { size: 'small' },
  Input: { size: 'small' },
  Select: { size: 'small', renderEmpty: () => h('div', 'No data') },
  DataTable: { size: 'small', renderFilter: myFilterRenderer },
  DatePicker: { size: 'small', timePickerSize: 'small' },
  Pagination: { size: 'small', inputSize: 'small', selectSize: 'small' },
  Form: { size: 'small' },
  // ... most interactive components supported
}" />
```

## Nested Config Providers

Config providers can be nested — inner provider overrides outer for its subtree:

```vue
<n-config-provider :theme="darkTheme">
  <!-- Dark by default -->
  <n-config-provider :theme="null">
    <!-- This subtree is light -->
    <LightSection />
  </n-config-provider>
</n-config-provider>
```

## OS Theme Detection

```vue
<script setup>
import { useOsTheme, darkTheme } from 'naive-ui'
const osTheme = useOsTheme()  // Ref<'light' | 'dark' | null>
</script>

<template>
  <n-config-provider :theme="osTheme === 'dark' ? darkTheme : null">
    <App />
  </n-config-provider>
</template>
```
