---
title: ContentSurround
description: A pair of prev and next links to navigate between pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/content/ContentSurround.vue
---

::callout{icon="i-heroicons-exclamation-triangle" to="/pro/getting-started/content"}
This component is only available when the `@nuxt/content` module is installed.
::

## Usage

::component-example
---
component: ContentSurroundExample
---

#code
```vue
<script setup lang="ts">
const { data: surround } = await useAsyncData(`${route.path}-surround`, () => {
  return queryContent()
    .where({ _extension: 'md', navigation: { $ne: false } })
    .only(['title', 'description', '_path'])
    .findSurround(withoutTrailingSlash(route.path))
}, { default: () => [] })
</script>

<template>
  <UContentSurround :surround="surround" />
</template>
```
::

You'll usually use this component in a `[...slug].vue` page:

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

## Props

:component-props

## Config

```yml
{
  wrapper: 'grid gap-8 sm:grid-cols-2',
  icon: {
    prev: 'i-heroicons-arrow-left-20-solid',
    next: 'i-heroicons-arrow-right-20-solid'
  },
  link: {}
}
```
