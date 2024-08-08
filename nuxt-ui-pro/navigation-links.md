---
title: NavigationLinks
description: A list of links displayed in the NavigationTree.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/navigation/NavigationLinks.vue
---

## Usage

This component is used internally by the [NavigationTree](/pro/components/navigation-tree).

::component-example
---
component: NavigationLinksExample
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'space-y-3',
  wrapperLevel: 'space-y-1.5',
  base: 'flex items-center gap-1.5 group',
  active: 'text-primary font-medium border-current',
  inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200 border-transparent hover:border-gray-500 dark:hover:border-gray-400',
  level: 'border-l -ml-px pl-4',
  icon: {
    base: 'w-5 h-5 flex-shrink-0'
  },
  badge: {
    base: 'rounded-full'
  },
  label: 'text-sm/6 truncate'
}
```
