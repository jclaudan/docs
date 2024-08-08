---
title: LandingHero
description: A responsive hero for your landing pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingHero.vue
---

## Usage

The `LandingHero` component will wrap your content in a [Container](/components/container) but the wrapper takes the full width of the screen so you can easily change the background.

Use the `title` and `description` props to customize the content of the hero.

::component-card
---
padding: false
props:
  title: Turn Your Vision into Reality
  description: Watch your dreams materialize before your eyes with us.
---
::

Use the `links` prop to add some [Buttons](/components/button) below the description.

::component-card
---
padding: false
props:
  title: Turn Your Vision into Reality
  description: Watch your dreams materialize before your eyes with us.
  links:
    - label: Get Started
      icon: i-heroicons-rocket-launch
      size: lg
    - label: Learn more
      trailing-icon: 'i-heroicons-arrow-small-right'
      color: gray
      size: lg
excludedProps:
  - links
---
::

You can add anything you want in the default slot, an image or a code-block using the [`MDC`](https://github.com/nuxt-modules/mdc/blob/main/src/runtime/components/MDC.vue) component (when using `@nuxt/content`) for example.

You can change the `orientation` prop from `vertical` to `horizontal` to position the slot on the right side of the hero (this will render better on full-screen).

You can use the `#headline` slot to add a [Badge](/components/badge), a [Button](/components/button) or anything you want above the title.

::component-card
---
padding: false
props:
  title: Supercharged GitHub experience
  description: Work in real-time with your team on open-source and private repositories, all in one place. Working on GitHub issues and notifications has never been that fun.
  orientation: vertical
  links:
    - label: Continue with GitHub
      icon: i-simple-icons-github
      color: gray
      size: lg
excludedProps:
  - links
slots:
  headline: <UButton color="gray" to="https://volta.net/changelog" label="See what's new in v1.17.0" trailing-icon="i-heroicons-arrow-right" size="xs" class="rounded-full" />
  default: <img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---
#headline
:u-button{color="gray" to="https://volta.net/changelog" label="See what's new in v1.17.0" trailing-icon="i-heroicons-arrow-right" size="xs" class="rounded-full"}

#default
<img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

You can also use the `#title`, `#description` and `#links` slots to customize the content of the hero. This can be quite useful when using `@nuxt/content` if your content has HTML for example:

```yml [content/index.yml]
navigation: false
hero:
  title: The <span class="text-primary">Building Blocks</span> for<br>Modern Web Apps
  description: 'Nuxt UI Pro is a collection of premium Vue components built on top of Nuxt UI to create beautiful & responsive Nuxt applications in minutes.<br>It includes all primitives to build landing pages, documentation, blogs, changelog, dashboards or entire SaaS products.'
  links:
    - label: Get Started
      to: /pro/getting-starated
      size: lg
      icon: i-heroicons-rocket-launch
    - label: Buy now
      to: /pro/pricing
      color: gray
      icon: i-heroicons-ticket
      size: lg
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingHero :links="page.hero.links">
    <template #title>
      <span v-html="page.hero.title" />
    </template>

    <template #description>
      <span v-html="page.hero.description" />
    </template>
  </ULandingHero>
</template>
```

You can use the `#top` and `#bottom` slots to add content above and below the container, this can be useful when adding some absolute positioned svgs for example.

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'py-24 sm:py-32 md:py-40 relative',
  container: 'gap-16 sm:gap-y-24 flex flex-col',
  base: 'text-center',
  headline: 'mb-10',
  title: 'text-5xl font-bold tracking-tight text-gray-900 dark:text-white sm:text-7xl',
  description: 'mt-6 text-lg tracking-tight text-gray-600 dark:text-gray-300',
  links: 'mt-10 flex flex-wrap justify-center gap-x-6 gap-y-3'
}
```
