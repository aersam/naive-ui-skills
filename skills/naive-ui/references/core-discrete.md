# Core Discrete API (`createDiscreteApi`)

Use `useDialog`, `useMessage`, `useNotification`, `useLoadingBar`, `useModal` **outside of Vue component setup** — e.g. in Pinia stores, router guards, axios interceptors, or utility files. Available since 2.29.0.

```typescript
// discrete.ts — create once, export for reuse
import { createDiscreteApi, darkTheme } from 'naive-ui'
import type { ConfigProviderProps } from 'naive-ui'
import { computed, ref } from 'vue'

const isDark = ref(false)

const configProviderProps = computed<ConfigProviderProps>(() => ({
  theme: isDark.value ? darkTheme : null
}))

export const { message, dialog, notification, loadingBar } = createDiscreteApi(
  ['message', 'dialog', 'notification', 'loadingBar'],
  { configProviderProps }
)

// Toggle theme to keep discrete API in sync:
export function setDark(dark: boolean) { isDark.value = dark }
```

```typescript
// router/index.ts — use in a route guard
import { message, loadingBar } from './discrete'

router.beforeEach(() => { loadingBar.start() })
router.afterEach(() => { loadingBar.finish() })

// axios interceptor
axios.interceptors.response.use(
  res => res,
  err => {
    message.error(err.message)
    return Promise.reject(err)
  }
)
```

## API

```typescript
function createDiscreteApi(
  includes: Array<'message' | 'dialog' | 'notification' | 'loadingBar' | 'modal'>,
  options?: {
    configProviderProps?: Ref<ConfigProviderProps> | ConfigProviderProps
    messageProviderProps?: Ref<MessageProviderProps> | MessageProviderProps
    dialogProviderProps?: Ref<DialogProviderProps> | DialogProviderProps
    notificationProviderProps?: Ref<NotificationProviderProps> | NotificationProviderProps
    modalProviderProps?: Ref<ModalProviderProps> | ModalProviderProps
    loadingBarProviderProps?: Ref<LoadingBarProviderProps> | LoadingBarProviderProps
  }
): {
  message: MessageApi       // only created if included
  dialog: DialogApi
  notification: NotificationApi
  loadingBar: LoadingBarApi
  modal: ModalApi
  app: App                  // the internal Vue app instance
  unmount: () => void       // cleanup
}
```

## Caveats

1. **Isolated context:** Discrete API runs in its own Vue app — it does NOT inherit theme/locale/namespace from `n-config-provider` in your main app. Sync manually via `configProviderProps`.
2. **Don't mix:** Do not use both discrete `message` API and a `n-message-provider`-based `useMessage()` for the same purpose in the same app.
3. **Not in setup:** Do not call `createDiscreteApi` inside a component's `setup()` — create it at module level.
