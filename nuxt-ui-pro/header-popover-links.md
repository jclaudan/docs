---
title: HeaderPopoverLinks
description: A list of links displayed in a header Popover.
links:
  - label: Popover
    icon: i-simple-icons-nuxtdotjs
    to: /components/popover
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/header/HeaderPopoverLinks.vue
---

## Usage

This component is used internally in the `#panel` slot of the [HeaderLinks](/pro/components/header-links) component.

::component-example
---
component: HeaderPopoverLinksExample
---
::

## Props

:component-props

## Config

```yml
{
  wrapper: 'p-2 space-y-1',
  base: 'block px-2 py-1.5 rounded-md flex items-start gap-1.5',
  active: 'bg-gray-100/50 dark:bg-gray-800/50 text-primary',
  inactive: 'hover:bg-gray-100/50 dark:hover:bg-gray-800/50',
  label: 'font-semibold text-sm/6 inline-block relative',
  description: 'text-sm leading-snug text-gray-500 dark:text-gray-400 line-clamp-2',
  icon: {
    base: 'w-4 h-4 flex-shrink-0 mt-1'
  },
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  }
}
```
