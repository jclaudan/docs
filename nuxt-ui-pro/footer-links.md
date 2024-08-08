---
title: FooterLinks
description: A list of links displayed in the Footer.
links:
  - label: Link
    icon: i-simple-icons-nuxtdotjs
    to: /components/link
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/footer/FooterLinks.vue
---

## Usage

This component is used internally in the `#center` slot of the [Footer](/pro/components/footer) component.

::component-example
---
component: FooterLinksExample
componentClass: 'items-center'
extraClass: 'justify-center'
---
::

## Props

:component-props

## Config

```yml
{
  wrapper: 'flex flex-col md:flex-row items-center justify-center gap-4 lg:gap-6',
  base: 'text-sm',
  active: 'text-gray-900 dark:text-white font-medium',
  inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-600 dark:hover:text-gray-300',
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-3 h-3 absolute top-0.5 -right-3.5 text-gray-400 dark:text-gray-500'
  }
}
```
