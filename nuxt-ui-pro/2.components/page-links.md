---
title: PageLinks
description: A list of links to display in your pages.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageLinks.vue
---

## Usage

Use the `title` and `links` props to display a list of links.

::component-card
---
props:
  links:
    - icon: 'i-heroicons-pencil-square'
      label: 'Edit this page'
    - icon: 'i-heroicons-star'
      label: 'Star on GitHub'
      to: 'https://github.com/nuxt/ui'
      target: '_blank'
    - icon: 'i-heroicons-book-open'
      label: 'Nuxt documentation'
      to: 'https://nuxt.com'
      target: '_blank'
  title: 'Discover'
excludedProps:
  - links
---
::

You'll usually use this component in the `#bottom` slot of an [Aside](/pro/components/aside) or [ContentToc](/pro/components/content-toc) component. This will match the design of the links from `ContentToc` and `NavigationTree`.

```vue [pages/\[...slug\\].vue]
<script setup lang="ts">
const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
if (!page.value) {
  throw createError({ statusCode: 404, statusMessage: 'Page not found', fatal: true })
}

const links = computed(() => [{
  icon: 'i-ph-pen-duotone',
  label: 'Edit this page',
  to: `https://github.com/nuxt/nuxt/edit/main/docs/${page?.value?._file?.split('/').slice(1).join('/')}`,
  target: '_blank'
}, {
  icon: 'i-ph-shooting-star-duotone',
  label: 'Star on GitHub',
  to: 'https://github.com/nuxt/nuxt',
  target: '_blank'
}, {
  icon: 'i-ph-chat-centered-text-duotone',
  label: 'Chat on Discord',
  to: 'https://discord.com/invite/ps2h6QT',
  target: '_blank'
}, {
  icon: 'i-ph-hand-heart-duotone',
  label: 'Become a Sponsor',
  to: 'https://github.com/sponsors/nuxt',
  target: '_blank'
}])
</script>

<template>
  <UPage>
    <UPageHeader v-bind="page" />

    <UPageBody prose>
      <ContentRenderer v-if="page && page.body" :value="page" />
    </UPageBody>

    <template v-if="page.toc !== false" #right>
      <UContentToc :links="page.body?.toc?.links">
        <template #bottom>
          <div class="hidden lg:block space-y-6" :class="{ '!mt-6': page.body?.toc?.links?.length }">
            <UDivider v-if="page.body?.toc?.links?.length" type="dashed" />

            <UPageLinks title="Community" :links="links" />
          </div>
        </template>
      </UContentToc>
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
  wrapper: 'space-y-3',
  title: 'text-sm/6 font-semibold flex items-center gap-1.5',
  container: 'space-y-3 lg:space-y-1.5',
  base: 'flex items-center gap-1.5',
  active: 'text-primary',
  inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200',
  icon: {
    base: 'w-5 h-5 flex-shrink-0'
  },
  avatar: {
    base: 'self-center',
    size: '2xs'
  },
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  },
  label: 'text-sm/6 font-medium relative'
}
```
