---
title: DashboardSlideover
description: A pre-built Slideover with consistent styling for your dashboard.
links:
  - label: Slideover
    icon: i-simple-icons-nuxtdotjs
    to: /components/slideover
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSlideover.vue
---

## Usage

Built on top of the [Slideover](/components/slideover) component, the `DashboardSlideover` contains a header, body and footer.

Its header matches exactly the [DashboardNavbar](/pro/components/dashboard-navbar) and contains a close button matching the [DashboardModal](/pro/components/dashboard-modal) and [DashboardSearch](/pro/components/dashboard-search).

Its body is a scrollable container with some padding to display your content and its footer is placed at the bottom of the slideover.

Use the `title` prop to customize the slideover.

::component-example
---
extraClass: 'overflow-hidden'
padding: false
component: DashboardSlideoverExample
iframe: true
iframeProps:
  height: 500
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  header: {
    base: 'flex items-center justify-between gap-x-1.5 flex-shrink-0 border-b border-gray-200 dark:border-gray-800 h-[--header-height]',
    padding: 'p-4'
  },
  body: {
    base: 'flex-1 overflow-y-auto',
    padding: 'p-4'
  },
  footer: {
    base: 'flex items-center gap-x-1.5 flex-shrink-0',
    padding: 'p-4'
  },
  title: 'text-gray-900 dark:text-white font-semibold flex items-center gap-x-1.5 min-w-0',
  default: {
    closeButton: {
      icon: 'i-heroicons-x-mark-20-solid',
      color: 'gray',
      variant: 'ghost',
      size: 'sm'
    }
  }
}
```
