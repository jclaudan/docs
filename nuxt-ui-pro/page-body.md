---
title: PageBody
description: A wrapper around your pages content.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageBody.vue
---

## Usage

Use the `PageBody` component in the default slot of a [Page](/pro/components/page).

This wrapper will add some spacing to your content.

```vue
<template>
  <UPage>
    <UPageBody>
      <UPageGrid>
        <UPageCard />
      </UPageGrid>
    </UPageBody>
  </UPage>
</template>
```

You can use the `prose` prop to automatically add `prose prose-primary dark:prose-invert max-w-none` classes to your content.

```vue
<template>
  <UPage>
    <UPageBody prose>
      <ContentRenderer :value="page" />
    </UPageBody>
  </UPage>
</template>
```

You'll usually use this component in a `[...slug].vue` page:

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
  wrapper: 'mt-8 pb-24',
  prose: 'prose prose-primary dark:prose-invert max-w-none'
}
```
