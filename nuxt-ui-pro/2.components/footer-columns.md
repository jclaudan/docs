---
title: FooterColumns
description: A list of links as columns to display in your Footer.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/footer/FooterColumns.vue
---

## Usage

Use the `links` prop to display a list of links. Each link will be a column with its children underneath.

::component-example
---
extraClass: '!p-8'
componentClass: 'flex-1'
component: FooterColumnsExample
---
::

The `FooterColumns` component is meant to be used in the `#top` slot of the `Footer`.

```vue [AppFooter.vue]
<template>
  <UFooter>
    <template #top>
      <UFooterColumns :links="links" />
    </template>
  </UFooter>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'xl:grid xl:grid-cols-3 xl:gap-8',
  left: 'mb-10 xl:mb-0',
  center: 'flex flex-col lg:grid grid-flow-col auto-cols-fr gap-8 xl:col-span-2',
  right: 'mt-10 xl:mt-0',
  label: 'text-sm/6 font-semibold text-gray-900 dark:text-white',
  list: 'mt-6 space-y-4',
  base: 'text-sm relative',
  active: 'text-gray-900 dark:text-white font-medium',
  inactive: 'text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white',
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  }
}
```
