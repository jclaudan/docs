---
title: ContentSearch
description: A ready to use CommandPalette to add to your documentation.
links:
  - label: CommandPalette
    icon: i-simple-icons-nuxtdotjs
    to: /components/command-palette
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/content/ContentSearch.vue
---

::callout{icon="i-heroicons-exclamation-triangle" to="/pro/getting-started/content"}
This component is only available when the `@nuxt/content` module is installed.
::

## Usage

Use the `files` and `navigation` props to provide the content to search through.

You can open the CommandPalette by pressing :shortcut{value="meta"} :shortcut{value="K"} or using the [ContentSearchButton](/pro/components/docs-search-button) component. You can also do this manually with `const { toggleContentSearch } = useUIState()`{lang="ts"}.

::component-example
---
extraClass: 'overflow-hidden'
padding: false
component: ContentSearchExample
iframe: true
iframeProps:
  height: 500
hiddenCode: true
---
::

You'll usually use this component in your `app.vue`:

```vue [app.vue]
<script setup lang="ts">
const { data: navigation } = await useAsyncData('navigation', () => fetchContentNavigation())
const { data: files } = useLazyFetch<ParsedContent[]>('/api/search.json', { default: () => [], server: false })

const links = [{
  label: 'Docs',
  icon: 'i-heroicons-book-open',
  to: '/getting-started'
}, {
  label: 'Pro',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro'
}, {
  label: 'Pricing',
  to: '/pro/pricing',
  icon: 'i-heroicons-ticket'
}, {
  label: 'Templates',
  icon: 'i-heroicons-computer-desktop',
  to: '/pro/templates'
}, {
  label: 'Releases',
  icon: 'i-heroicons-rocket-launch',
  to: '/releases'
}]

provide('navigation', navigation)
provide('files', files)
</script>

<template>
  <Header :links="links" />

  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>

  <Footer />

  <ClientOnly>
    <LazyUContentSearch :files="files" :navigation="navigation" :links="links" />
  </ClientOnly>

  <UNotifications />
</template>
```

It is recommended to wrap the `ContentSearch` component in a [ClientOnly](https://nuxt.com/docs/api/components/client-only) component so it's not rendered on the server.

The `files` are fetched from the `/api/search.json` endpoint, to achieve the same thing you'll need to create a server route:

```ts [server/api/search.json.get.ts]
import { serverQueryContent } from '#content/server'

export default eventHandler(async (event) => {
  return serverQueryContent(event).where({ _type: 'markdown', navigation: { $ne: false } }).find()
})
```

We recommend using this method instead of fetching the files directly, the performances will be better.

### Color Mode

By default, a group of commands will be added to the command palette so you can switch between light and dark mode. This will only take effect if the `colorMode` is not forced in a specific page which can be achieved through `definePageMeta`:

```ts [pages/index.vue]
<script setup lang="ts">
definePageMeta({
  colorMode: 'dark'
})
</script>
```

You can also disable this behavior manually by setting the `hide-color-mode` prop: `<UContentSearch hide-color-mode />`. This can be quite useful when forcing the color mode for the entire app in your `nuxt.config.ts`:

```ts [nuxt.config.ts]
export default defineNuxtConfig({
  colorMode: {
    preference: 'light'
  }
})
```

## Props

:component-props

## Config

```yml
{
  padding: 'p-0 sm:p-4',
  rounded: 'rounded-none sm:rounded-lg',
  width: 'sm:max-w-3xl',
  height: 'h-dvh sm:h-[28rem]',
  commandPalette: {
    input: {
      height: 'h-[--header-height] sm:h-12',
      icon: {
        size: 'h-5 w-5',
        padding: 'ps-11'
      }
    },
    group: {
      command: {
        prefix: `!text-foreground after:content-['_>']`
      }
    },
    container: 'scroll-py-10'
  },
  fileIcon: {
    name: 'i-heroicons-document-text'
  },
  default: {
    closeButton: {
      icon: 'i-heroicons-document-text',
      color: 'gray',
      variant: 'ghost',
      size: 'sm'
    }
  }
}
```
