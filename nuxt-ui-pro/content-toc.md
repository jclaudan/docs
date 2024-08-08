---
title: ContentToc
description: A sticky Table of Contents with customizable slots.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/content/ContentToc.vue
---

::callout{icon="i-heroicons-exclamation-triangle" to="/pro/getting-started/content"}
This component is only available when the `@nuxt/content` module is installed.
::

## Usage

::component-example
---
component: ContentTocExample
componentClass: '[&>div]:!py-0'
---

#code
```vue
<script setup lang="ts">
const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
</script>

<template>
  <UContentToc :links="page.body.toc.links" />
</template>
```
::

You'll usually use this component in the `#right` slot of a [Page](/pro/components/page):

```vue [pages/\[...slug\\].vue]
<script setup lang="ts">
import { withoutTrailingSlash } from 'ufo'

const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
if (!page.value) {
  throw createError({ statusCode: 404, statusMessage: 'Page not found', fatal: true })
}

const { data: surround } = await useAsyncData(`${route.path}-surround`, () => {
  return queryContent()
    .where({ _extension: 'md', navigation: { $ne: false } })
    .only(['title', 'description', '_path'])
    .findSurround(withoutTrailingSlash(route.path))
}, { default: () => [] })
</script>

<template>
  <UPage>
    <UPageHeader :title="page.title" :description="page.description" :links="page.links" />

    <UPageBody prose>
      <ContentRenderer v-if="page.body" :value="page" />

      <hr v-if="surround?.length">

      <UContentSurround :surround="surround" />
    </UPageBody>

    <template v-if="page.body?.toc?.links?.length" #right>
      <UContentToc :links="page.body.toc.links" />
    </template>
  </UPage>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'sticky top-[--header-height] bg-background/75 backdrop-blur -mx-4 sm:-mx-6 px-4 sm:px-6 lg:px-4 lg:-mx-4 overflow-y-auto max-h-[calc(100vh-var(--header-height))]',
  container: {
    base: 'py-3 lg:py-8 border-b border-dashed border-gray-200 dark:border-gray-800 lg:border-0 space-y-3',
    empty: 'lg:py-8 space-y-3'
  },
  button: {
    base: 'flex items-center gap-1.5 lg:cursor-text lg:select-text w-full group',
    label: 'font-semibold text-sm/6 truncate',
    trailingIcon: {
      name: 'i-heroicons-chevron-down-20-solid',
      base: 'w-5 h-5 ms-auto transform transition-transform duration-200 flex-shrink-0 mr-1.5',
      active: 'text-gray-700 dark:text-gray-200',
      inactive: 'text-gray-500 dark:text-gray-400 group-hover:text-gray-700 dark:group-hover:text-gray-200 -rotate-90'
    }
  },
  links: {}
}
```
