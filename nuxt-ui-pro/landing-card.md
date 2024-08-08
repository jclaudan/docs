---
title: LandingCard
description: A pre-built Card with slot support and hover effect.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingCard.vue
---

## Usage

Built on top of the [Card](/components/card) component, the `LandingCard` can be used in a [LandingGrid](/pro/components/landing-grid) or a [PageGrid](/pro/components/page-grid).

Use the `title`, `description`, `icon` and `color` props to customize the card.

You can also pass any property from the [NuxtLink](https://nuxt.com/docs/api/components/nuxt-link#props) component such as `to`, `target`, `exact`, etc.

::component-card
---
props:
  title: Color Palette
  description: 'Choose a primary and a gray color from your Tailwind CSS color palette. Components will be styled accordingly.'
  icon: i-heroicons-swatch
  color: primary
excludedProps:
  - icon
---
::

You can add anything you want in the default slot, an image for example.

You can change the `orientation` prop from `vertical` to `horizontal` to position the slot on the right side of the content.

::component-card
---
props:
  title: Portfolio
  description: Veniam minim ipsum anim. Irure voluptate magna dolore id dolore ex quis sint sint et duis dolor enim fugiat.
  icon: i-heroicons-photo
  color: primary
  orientation: horizontal
excludedProps:
  - icon
code: |

  <img src="https://picsum.photos/640/360?grayscale" class="w-full rounded-md">
---

<img src="https://picsum.photos/640/360?grayscale" class="w-full rounded-md">
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative group isolate rounded-xl background-gradient ring-1 ring-gray-200 dark:ring-gray-800 before:hidden before:lg:block before:absolute before:-inset-[2px] before:h-[calc(100%+4px)] before:w-[calc(100%+4px)] before:z-[-1] before:rounded-[13px] flex-1 flex flex-col shadow',
  to: 'hover:ring-primary-500 dark:hover:ring-primary-400 transition-shadow duration-200',
  base: 'flex-1 flex flex-col overflow-hidden',
  container: '',
  body: {
    base: 'gap-x-8 gap-y-4 rounded-xl flex-1 flex flex-col'
  },
  background: 'bg-white dark:bg-gray-900 hover:bg-opacity-90 dark:hover:bg-opacity-90 transition-[background-opacity]',
  ring: '',
  rounded: 'rounded-xl',
  shadow: '',
  icon: {
    wrapper: 'mb-2 pointer-events-none',
    base: 'w-8 h-8 flex-shrink-0 text-gray-900 dark:text-white'
  },
  title: 'text-gray-900 dark:text-white text-base font-bold truncate',
  description: 'text-[15px] text-gray-500 dark:text-gray-400 mt-1'
}
```
