---
title: Page
description: A dynamic grid layout for your pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/Page.vue
---

## Usage

The `Page` component will allow you to structure your pages as a grid with a left or right column. When no slots are provided, the page will be a single column.

```vue
<template>
  <UPage>
    <template #left>
      <!-- <UAside /> -->
    </template>

    <template #right>
      <!-- <UContentToc /> -->
    </template>
  </UPage>
</template>
```

You'll usually use this component in a layout or parent `.vue` page with its `#left` slot:

```vue [pages/docs.vue]
<script setup lang="ts">
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))
</script>

<template>
  <UContainer>
    <UPage>
      <template #left>
        <UAside>
          <UNavigationTree :links="mapContentNavigation(navigation)" />
        </UAside>
      </template>

      <!-- Change this to `<slot />` when in a layout. -->
      <NuxtPage />
    </UPage>
  </UContainer>
</template>
```

But you can also use it in a `[...slug].vue` page with its `#right` slot:

```vue [pages/\[...slug\\].vue]
<script setup lang="ts">
const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
</script>

<template>
  <UPage>
    <UPageHeader :title="page.title" :description="page.description" :links="page.links" />

    <UPageBody prose>
      <ContentRenderer v-if="page.body" :value="page" />
    </UPageBody>

    <template #right>
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
  wrapper: 'flex flex-col lg:grid lg:grid-cols-10 lg:gap-8',
  left: 'lg:col-span-2',
  center: {
    narrow: 'lg:col-span-6',
    base: 'lg:col-span-8',
    full: 'lg:col-span-10'
  },
  right: 'lg:col-span-2 order-first lg:order-last'
}
```
