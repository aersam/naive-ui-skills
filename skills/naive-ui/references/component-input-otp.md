# Component Input OTP (`n-input-otp`)

One-time password input with individual character boxes. Available since 2.41.1.

```vue
<!-- Basic OTP input -->
<n-input-otp v-model:value="code" :length="6" @finish="handleVerify" />

<!-- Masked (password mode) -->
<n-input-otp v-model:value="code" :length="4" mask />

<!-- Restrict to digits only -->
<n-input-otp
  v-model:value="code"
  :allow-input="(char) => /\d/.test(char)"
/>

<!-- Use in form -->
<n-form ref="formRef" :model="model">
  <n-form-item label="Pass Code" path="code">
    <n-input-otp v-model:value="model.code" block />
  </n-form-item>
</n-form>

<!-- Custom rendering -->
<n-input-otp v-model:value="code" :length="6">
  <template #default="{ index, ref: inputRef, ...inputProps }">
    <n-input v-bind="inputProps" :ref="inputRef" style="width: 40px" />
    <span v-if="index === 2" style="margin: 0 4px">-</span>
  </template>
</n-input-otp>
```

## Props

| Prop | Type | Default | Notes |
|------|------|---------|-------|
| `value` | `string[] \| null` | — | Array of individual chars |
| `default-value` | `string[]` | `[]` | |
| `length` | number | 6 | Number of input boxes |
| `mask` | boolean | false | Password masking |
| `block` | boolean | false | Fit parent width (since 2.42.0) |
| `gap` | `string \| number` | — | Space between boxes |
| `placeholder` | string | `''` | |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | |
| `status` | `'success' \| 'warning' \| 'error'` | — | Validation status |
| `disabled` / `readonly` | boolean | false | |
| `allow-input` | `(char, index, currentValue) => boolean` | — | Restrict accepted characters |

## Events

| Event | Parameters | Notes |
|-------|-----------|-------|
| `on-update:value` | `(value[], meta)` | `meta.diff`, `meta.index`, `meta.source` (`'input'\|'delete'\|'paste'`) |
| `on-finish` | `(value[])` | All boxes filled |
| `on-focus` | `(event, index)` | |
| `on-blur` | `(event, index)` | |

## Slot
- `default({ index, ref, ...inputProps })` — custom input for each box

## Method
- `focusOnChar(charIndex)` — focus a specific box (since 2.43.0)
