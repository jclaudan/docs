---
title: AsideLinks
description: A list of links displayed in the Aside.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/aside/AsideLinks.vue
---

## Usage

This component is used internally in the `#links` slot of the [Aside](/pro/components/aside) component.

::component-example
---
component: AsideLinksExample
componentClass: '!mb-0'
---
::

## Props

:component-props

## Config

```yml
{
  wrapper: 'space-y-3 mb-3 lg:mb-6 -mx-1 lg:mx-0',
  base: 'flex items-center gap-1.5 lg:gap-2 group',
  active: 'text-primary font-semibold',
  inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200 font-medium',
  icon: {
    wrapper: 'rounded-md p-1 inline-flex ring-inset ring-1',
    base: 'w-4 h-4 flex-shrink-0',
    active: 'bg-primary ring-primary text-background',
    inactive: 'bg-gray-100/50 dark:bg-gray-800/50 ring-gray-300 dark:ring-gray-700 group-hover:bg-primary group-hover:ring-primary group-hover:text-background'
  },
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  },
  label: 'text-sm/6 relative'
}
```
