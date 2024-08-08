---
title: NavigationAccordion
description: A pre-styled Accordion displayed in the NavigationTree.
links:
  - label: Accordion
    icon: i-simple-icons-nuxtdotjs
    to: /components/accordion
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/navigation/NavigationAccordion.vue
---

## Usage

This component is used internally by the [NavigationTree](/pro/components/navigation-tree).

::component-example
---
component: NavigationAccordionExample
---
::

## Props

:component-props

## Config

```yml
{
  wrapper: 'space-y-3',
  container: 'space-y-3',
  item: {
    padding: '',
    color: 'text-inherit dark:text-inherit'
  },
  button: {
    base: 'flex items-center gap-1.5 group w-full focus-visible:outline-primary',
    active: 'text-primary border-current',
    inactive: 'border-transparent',
    level: 'border-l -ml-px pl-3.5',
    icon: {
      base: 'w-5 h-5 flex-shrink-0'
    },
    trailingIcon: {
      name: 'i-heroicons-chevron-down-20-solid',
      base: 'w-5 h-5 ms-auto transform transition-transform duration-200 flex-shrink-0 mr-1.5',
      active: 'text-gray-700 dark:text-gray-200',
      inactive: 'text-gray-500 dark:text-gray-400 group-hover:text-gray-700 dark:group-hover:text-gray-200 -rotate-90'
    },
    label: 'text-sm/6 font-semibold truncate'
  },
  tree: 'border-l border-gray-200 dark:border-gray-800',
  links: {}
}
```
