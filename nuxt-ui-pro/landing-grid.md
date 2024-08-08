---
title: LandingGrid
description: A customizable grid to display cards as a masonry layout.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingGrid.vue
---

## Usage

Use some [LandingCard](/pro/components/landing-card), [PageCard](/pro/components/page-card) or anything really in the default slot to display a **masonry** grid.

::component-example
---
component: LandingGridExample
componentClass: 'w-full'
---
::

This component can be put directly inside a [LandingSection](/pro/components/landing-section) with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
features:
  title: Everything you expect from a<br class="hidden lg:block"> <span class="text-primary">UI component library</span>
  cards:
    - title: Color Palette
      description: 'Choose a primary and a gray color from your Tailwind CSS color palette. Components will be styled accordingly.'
      icon: i-heroicons-swatch
      to: /getting-started/theming#colors
      class: 'col-span-7 row-span-3'
    - title: Fully Customizable
      description: 'Change the style of any component in your App Config or customize them specifically through the ui prop.'
      icon: i-heroicons-wrench-screwdriver
      to: /getting-started/theming#components
      class: 'col-span-5 row-span-5 lg:mb-10'
    - title: Icons
      description: 'Choose any of the 100k+ icons from the most popular icon libraries with the Icon component or the icon prop.'
      icon: i-heroicons-face-smile
      to: /getting-started/theming#icons
      class: 'col-span-7 row-span-3'
    - title: Light & Dark
      description: 'Every component is designed with dark mode in mind. Works out of the box with @nuxtjs/color-mode.'
      to: /getting-started/theming#dark-mode
      icon: i-heroicons-moon
      class: 'col-span-5 row-span-5 lg:-mt-10 lg:mb-20'
    - title: Keyboard Shortcuts
      description: 'Nuxt UI comes with a set of Vue composables to easily handle keyboard shortcuts in your app.'
      icon: i-heroicons-computer-desktop
      to: /getting-started/shortcuts
      class: 'col-span-7 row-span-3'
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection :title="page.features.title">
    <ULandingGrid>
      <ULandingCard
        v-for="(card, index) of section.cards"
        :key="index"
        v-bind="card"
      />
    </ULandingGrid>
  </ULandingSection>
</template>
```

## Props

:component-props

## Slots

:component-slots

## Config

```yml
{
  wrapper: 'flex flex-col lg:grid gap-8 lg:grid-cols-12 relative'
}
```
