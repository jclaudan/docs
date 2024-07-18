---
title: DashboardModal
description: A pre-built Modal with consistent styling for your dashboard.
links:
  - label: Modal
    icon: i-simple-icons-nuxtdotjs
    to: /components/modal
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardModal.vue
---

## Usage

Built on top of the [Modal](/components/modal) component, the `DashboardModal` contains a header, body and footer.

Its header matches exactly the [DashboardNavbar](/pro/components/dashboard-navbar) on mobile and contains a close button matching the [DashboardSlideover](/pro/components/dashboard-slideover) and [DashboardSearch](/pro/components/dashboard-search).

Use the `title`, `description` and `icon` props to customize the modal.

::component-example
---
extraClass: 'overflow-hidden'
padding: false
component: DashboardModalExample
iframe: true
iframeProps:
  height: 300
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  rounded: 'sm:rounded-lg',
  shadow: 'sm:shadow-xl',
  width: 'sm:max-w-xl',
  height: 'h-dvh sm:h-auto',
  padding: 'p-0',
  header: {
    base: 'flex items-start justify-between gap-x-1.5 flex-shrink-0 min-h-[--header-height]',
    inner: 'flex items-start gap-4',
    padding: 'px-4 py-4 sm:px-6'
  },
  body: {
    base: 'flex-1 flex flex-col gap-y-3 overflow-y-auto',
    padding: 'px-4 py-5 sm:p-6'
  },
  footer: {
    base: 'flex items-center gap-x-1.5 flex-shrink-0',
    padding: 'px-4 py-4 sm:px-6'
  },
  title: 'text-gray-900 dark:text-white font-semibold',
  description: 'mt-1 text-gray-500 dark:text-gray-400 text-sm',
  icon: {
    wrapper: 'inline-flex',
    base: 'w-12 h-12 flex-shrink-0 text-gray-900 dark:text-white'
  },
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
