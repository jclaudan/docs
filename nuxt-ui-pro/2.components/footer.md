---
title: Footer
description: A responsive <footer> component.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/footer/Footer.vue
---

## Usage

Use the `links` prop to display a list of links in the center of the footer. You can also use the `#left`, `#center` and `#right` slots to customize it further.

::component-example
---
padding: false
component: FooterExample
componentClass: 'w-full'
---
::

::callout{icon="i-heroicons-light-bulb"}
There is also a `#top` slot available, check out the [FooterColumns](/pro/components/footer-columns) component.
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative',
  top: {
    wrapper: '',
    container: 'py-8 lg:py-12'
  },
  bottom: {
    wrapper: '',
    container: 'py-8 lg:py-4 lg:flex lg:items-center lg:justify-between lg:gap-x-3',
    left: 'flex items-center justify-center lg:justify-start lg:flex-1 gap-x-1.5 mt-3 lg:mt-0 lg:order-1',
    center: 'mt-3 lg:mt-0 lg:order-2 flex items-center justify-center',
    right: 'lg:flex-1 flex items-center justify-center lg:justify-end gap-x-1.5 lg:order-3'
  }
}
```
