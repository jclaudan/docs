---
title: PageHero
description: A responsive hero for your pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageHero.vue
---

## Usage

Use the `PageHero` component above a [Page](/pro/components/page).

```vue
<template>
  <UContainer>
    <UPageHero />

    <UPage>
      <UPageHeader />

      <UPageBody />
    </UPage>
  </UContainer>
</template>
```

Use the `title` and `description` props to customize the hero.

::component-card
---
componentClass: 'w-full'
props:
  title: Official Support
  description: Through NuxtLabs experts and agency networks, we have a solution for every need.
---
::

Use the `icon` prop to add an icon on top of the title.

::component-card
---
props:
  icon: i-heroicons-lifebuoy
  title: Official Support
  description: Through NuxtLabs experts and agency networks, we have a solution for every need.
excludedProps:
  - icon
---
::

You can add anything you want in the default slot, an image or a code-block using the [`MDC`](https://github.com/nuxt-modules/mdc/blob/main/src/runtime/components/MDC.vue) component (when using `@nuxt/content`) for example.

You can change the `align` prop from `left` to `center` or `right` to position the slot differently.

::component-card
---
componentClass: 'w-full'
props:
  title: Official Support
  description: Through NuxtLabs experts and agency networks, we have a solution for every need.
  align: left
code: |

  <img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

Use the `links` prop to add some [Buttons](/components/button) below the description. Those will be rendered below the default slot when the `align` prop is set to `center`.

::component-card
---
componentClass: 'w-full'
props:
  title: Official Support
  description: Through NuxtLabs experts and agency networks, we have a solution for every need.
  align: left
  links:
  - label: 'Get started'
    color: black
    size: lg
  - label: 'Learn more'
    color: 'gray'
    size: lg
    trailingIcon: 'i-heroicons-arrow-right-20-solid'
excludedProps:
  - links
code: |

  <img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

You can also use the `#title`, `#description` and `#links` slots to customize the content of the hero. This can be quite useful when using `@nuxt/content` if your content has HTML for example:

```yml [content/newsletter.yml]
title: The Nuxt Newsletter
head.title: Nuxt Newsletter
description: 'Get the latest releases and news about Nuxt and its ecosystem with our newsletter.'
navigation: false
hero:
  title: The <span class="text-primary">Nuxt</span> Newsletter
  align: 'center'
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/newsletter.vue]
<script setup lang="ts">
const route = useRoute()

const { data: page } = await useAsyncData(route.path, () => queryContent(route.path).findOne())
</script>

<template>
  <UContainer>
    <UPageHero :description="page.description" :align="page.hero.align">
      <template #title>
        <span v-html="page.hero.title" />
      </template>
    </UPageHero>

    <UPage>
      <UPageBody>
        <ULandingCTA />
      </UPageBody>
    </UPage>
  </UContainer>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'py-8 sm:py-16',
  container: 'gap-8 sm:gap-y-16',
  base: '',
  icon: {
    wrapper: 'flex mb-4',
    base: 'w-10 h-10 flex-shrink-0 text-primary'
  },
  title: 'text-3xl font-bold tracking-tight text-gray-900 dark:text-white sm:text-4xl lg:text-5xl',
  description: 'mt-4 text-lg text-gray-500 dark:text-gray-400',
  links: 'mt-8 flex flex-wrap gap-x-3 gap-y-1.5'
}
```
