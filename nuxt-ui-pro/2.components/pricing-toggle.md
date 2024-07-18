---
title: PricingToggle
description: A customizable Toggle to switch the payment frequency.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/pricing/PricingToggle.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/pricing) to see how you can build your own pricing page! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/pricing.vue))
::

## Usage

Built on top of the Headless UI [Switch](https://headlessui.com/vue/switch) component, use a `v-model` to bind the value of the toggle.

::component-example
---
component: PricingToggleExample
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'ring-1 ring-gray-300 dark:ring-gray-700 flex items-center relative h-8 w-auto flex-shrink-0 cursor-pointer rounded-full p-1 w-full focus:outline-none',
  marker: 'w-1/2 text-white dark:text-gray-900 pointer-events-none inline-block h-6 transform rounded-full bg-gray-900 dark:bg-white shadow transition duration-200 ease-in-out z-0 relative',
  active: 'text-white dark:text-gray-900',
  inactive: 'text-gray-500 dark:text-gray-400',
  base: 'absolute inset-y-0 w-1/2 flex items-center justify-center pointer-events-none z-[1] transition-colors duration-200 select-none text-xs font-semibold flex-shrink-0',
  left: 'left-0',
  right: 'right-0'
}
```
