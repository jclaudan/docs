---
title: PageCard
description: A pre-built Card to add links in your pages.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/page/PageCard.vue
---

## Usage

Built on top of the [Card](/components/card) component, the `PageCard` can be used in a [PageGrid](/pro/components/page-grid), [PageColumns](/pro/components/page-columns) or a [LandingGrid](/pro/components/landing-grid).

Use the `title`, `description` and `icon` props to customize the card.

::component-card
---
componentClass: 'w-full'
props:
  title: Tailwind CSS
  description: Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.
  icon: i-simple-icons-tailwindcss
excludedProps:
  - icon
---
::

You can also pass any property from the [NuxtLink](https://nuxt.com/docs/api/components/nuxt-link#props) component such as `to`, `target`, `exact`, etc.

::component-card
---
componentClass: 'w-full'
props:
  title: Tailwind CSS
  description: Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.
  icon: i-simple-icons-tailwindcss
  to: https://nuxt.com/modules/tailwindcss
  target: _blank
excludedProps:
  - target
  - to
  - icon
---
::

::callout{icon="i-heroicons-light-bulb" to="https://nuxt.com/modules" target="_blank"}
Look at the Nuxt.com modules page to see what you can do!
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative group',
  to: 'hover:ring-2 hover:ring-primary-500 dark:hover:ring-primary-400 hover:bg-gray-100/50 dark:hover:bg-gray-800/50',
  icon: {
    wrapper: 'mb-6 flex',
    base: 'w-10 h-10 flex-shrink-0 text-primary'
  },
  body: {
    base: 'flex-1'
  },
  title: 'text-gray-900 dark:text-white text-base font-semibold truncate flex items-center gap-1.5',
  description: 'text-[15px] text-gray-500 dark:text-gray-400 mt-1'
}

```
