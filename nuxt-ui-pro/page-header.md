---
title: PageHeader
description: A responsive header for your pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageHeader.vue
---

## Usage

Use the `PageHeader` component in the default slot of a [Page](/pro/components/page).

```vue
<template>
  <UPage>
    <UPageHeader />

    <UPageBody />
  </UPage>
</template>
```

Use the `title`, `description` and `headline` props to customize the header.

::component-card
---
componentClass: 'w-full'
props:
  headline: Page
  title: PageHeader
  description: A responsive header for your pages.
---
::

Use the `links` prop to add some [Buttons](/components/button) at the right of the header.

::component-card
---
componentClass: 'w-full'
props:
  headline: Page
  title: PageHeader
  description: A responsive header for your pages.
  links:
    - label: GitHub
      color: white
      to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageHeader.vue
      target: _blank
      icon: i-simple-icons-github
excludedProps:
 - links
---
::

Use the `icon` prop to add an icon to the left of the title.

::component-card
---
componentClass: 'w-full'
props:
  title: tailwindcss
  description: Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.
  icon: i-simple-icons-tailwindcss
---
::

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

::callout{icon="i-heroicons-light-bulb"}
When using `@nuxt/content`, you can use the [`findPageHeadline`](/pro/getting-started/content#findpageheadline) or [`findPageBreadcrumb`](/pro/getting-started/content#findpagebreadcrumb) utils to set the `headline` prop or slot.
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative border-b border-gray-200 dark:border-gray-800 py-8',
  container: 'flex flex-col lg:flex-row lg:items-center lg:justify-between',
  headline: 'mb-3 text-sm/6 font-semibold text-primary flex items-center gap-1.5',
  title: 'text-3xl sm:text-4xl font-bold text-gray-900 dark:text-white tracking-tight',
  description: 'mt-4 text-lg text-gray-500 dark:text-gray-400',
  icon: {
    wrapper: 'flex',
    base: 'w-10 h-10 flex-shrink-0 text-primary'
  },
  links: 'flex flex-wrap items-center gap-1.5 mt-4 lg:mt-0'
}
```
