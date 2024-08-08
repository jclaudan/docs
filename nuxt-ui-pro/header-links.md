---
title: HeaderLinks
description: A list of links displayed in the Header.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/header/HeaderLinks.vue
---

## Usage

This component is used internally in the `#center` slot of the [Header](/pro/components/header) component.

::component-example
---
component: HeaderLinksExample
componentClass: 'items-center'
extraClass: 'justify-center'
---
::

## Props

:component-props

## Config

```yml
{
  wrapper: 'flex items-center gap-x-8',
  base: 'text-sm/6 font-semibold flex items-center gap-1',
  active: 'text-primary',
  inactive: 'hover:text-primary',
  trailingIcon: {
    name: 'i-heroicons-chevron-down-20-solid',
    base: 'w-5 h-5 transform transition-transform duration-200 flex-shrink-0',
    active: 'rotate-180',
    inactive: ''
  },
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  },
  default: {
    popover: {
      mode: 'hover',
      openDelay: 0,
      ui: {
        width: 'max-w-[16rem]'
      }
    }
  }
}
```
