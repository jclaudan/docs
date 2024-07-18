---
title: PricingCard
description: A pre-built Card with all you need to display a pricing plan.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/pricing/PricingCard.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/pricing) to see how you can build your own pricing page! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/pricing.vue))
::

## Usage

Built on top of the [Card](/components/card) component, the `PricingCard` can be used in a [PricingGrid](/pro/components/pricing-grid).

Use the `title`, `description`, `price`, `discount` and `cycle` props to customize the card.

::component-card
---
props:
  title: Solo
  description: 'For bootstrappers and indie hackers.'
  price: $199
  discount: ''
  cycle: '/month'
  highlight: false
  badge:
    label: 'Most popular'
  button:
    label: 'Buy now'
  orientation: 'vertical'
  align: 'bottom'
  features:
    - 'One developer'
    - 'Unlimited projects'
    - 'Unlimited minor & patch updates'
    - 'Lifetime access'
excludedProps:
  - badge
  - button
  - features
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative flex flex-col self-stretch w-full',
  highlight: 'ring-2 ring-primary dark:ring-primary',
  scale: 'lg:scale-[1.1] lg:z-10',
  rounded: 'rounded-xl',
  body: {
    base: 'flex-1 gap-6 lg:gap-x-8 xl:gap-x-10 flex flex-col',
    padding: 'p-6 lg:p-8 xl:p-10'
  },
  inner: 'flex items-center gap-3',
  title: 'text-2xl text-gray-900 dark:text-white sm:text-3xl font-semibold truncate',
  description: 'text-sm sm:text-base text-gray-500 dark:text-gray-400 mt-2',
  amount: {
    base: 'flex flex-row items-baseline gap-x-1',
    discount: 'text-gray-500 dark:text-gray-400 line-through text-xl sm:text-2xl font-medium',
    price: 'text-gray-900 dark:text-white text-2xl sm:text-4xl font-semibold',
    cycle: 'text-gray-500 dark:text-gray-400 text-sm/6 font-medium truncate'
  },
  features: {
    vertical: 'space-y-3 text-sm',
    horizontal: 'grid lg:grid-cols-2 text-sm gap-3',
    item: {
      base: 'flex items-center gap-x-3 min-w-0',
      label: 'text-gray-600 dark:text-gray-400 truncate',
      icon: {
        base: 'w-5 h-5 flex-shrink-0 text-primary',
        name: 'i-heroicons-check-circle-20-solid'
      }
    }
  },
  divider: 'my-6 lg:my-8',
  left: '',
  right: ''
}
```
