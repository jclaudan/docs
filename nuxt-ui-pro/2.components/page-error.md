---
title: PageError
description: A pre-built error component with NuxtError support.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageError.vue
---

## Usage

::component-card
---
componentClass: py-8 min-h-0 w-full
props:
  status: 404
  name: Page not found
  message: The page you are looking for does not exist.
---
::

You'll usually use this component in your `error.vue` file:

```vue [error.vue]
<template>
  <div>
    <UHeader />

    <UContainer>
      <UMain>
        <UPage>
          <UPageError :error="error" />
        </UPage>
      </UMain>
    </UContainer>
  </div>
</template>

<script setup lang="ts">
import type { NuxtError } from '#app'

defineProps<{
  error: NuxtError
}>()
</script>
```

::callout{icon="i-heroicons-light-bulb"}
You might want to replicate the code of your `app.vue` inside your `error.vue` file to have the same layout and features, here is an example: https://github.com/nuxt/ui/blob/dev/docs/error.vue
::

You can read more about how to handle errors in the [Nuxt documentation](https://nuxt.com/docs/getting-started/error-handling#error-page), but when using `nuxt generate` it is recommended to add `fatal: true` inside your `createError` call to make sure the error page is displayed:

```vue [pages/\[...slug\\].vue]
<script setup lang="ts">
const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
if (!page.value) {
  throw createError({ statusCode: 404, statusMessage: 'Page not found', fatal: true })
}
</script>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'min-h-[calc(100vh-var(--header-height))] flex flex-col items-center justify-center',
  status: 'text-base font-semibold text-primary',
  name: 'text-3xl font-bold tracking-tight text-gray-900 dark:text-white sm:text-5xl',
  message: 'mt-6 text-base/7 text-gray-500 dark:text-gray-400 text-center',
  links: 'mt-10 flex items-center justify-center gap-x-6',
  default: {
    clearButton: {
      label: 'Go back home',
      color: 'primary',
      size: 'lg'
    }
  }
}
```
