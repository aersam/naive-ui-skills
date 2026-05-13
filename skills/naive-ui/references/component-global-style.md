# Component Global Style (`n-global-style`)

Syncs Naive UI theme variables to `document.body` so global styles (background color, text color, font) respond to theme changes.

```vue
<n-config-provider :theme="isDark ? darkTheme : null">
  <n-global-style />
  <App />
</n-config-provider>
```

No props, no slots. Just place it inside `n-config-provider`.

## Why Use It

Without `n-global-style`, two issues occur:

1. **Unresponsive global styles:** Naive UI mounts some global CSS (e.g., `font-family`) once that doesn't react to theme changes.
2. **Body background:** `n-config-provider` styles its own subtree, but `document.body` background stays the browser default — visible as a flash or mismatched border when the page is smaller than the viewport.

`n-global-style` bridges both gaps by applying theme styles to `document.body` reactively.

> **Recommendation:** Always include `<n-global-style />` as a direct child of your root `n-config-provider`.
