---
title: Header
description: A responsive and sticky <header> component.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/header/Header.vue
---

## Usage

Use the `links` prop to display a list of links in the center of the header. Those links will transform into a styled [Popover](/components/popover) if they have children. You can also use the `#left`, `#center` and `#right` slots to customize it further.

By default, a link labeled `Nuxt UI Pro` that goes to the `/` route will be displayed on the left. You can change the link by using the `to` prop and use the `#logo` slot to put your own logo. If you want to completely override this, use the `#left` slot.

::component-example
---
extraClass: 'overflow-hidden'
padding: false
component: HeaderExample
componentClass: 'w-full relative z-0'
iframe: true
---
::

The `links` prop will be displayed in the center of the header using the [HeaderLinks](/pro/components/header-links) component.

You can override this by using the `#center` slot, for example you could put the [ContentSearchButton](/pro/components/content-search-button) component there, it will fit perfectly.

```vue
<template>
  <UHeader>
    <template #center>
      <UContentSearchButton />
    </template>
  </UHeader>
</template>
```

On mobile, the links in the `#center` slot will be hidden and a hamburger menu will be displayed instead.

::callout{icon="i-heroicons-exclamation-triangle"}
If you've overriden the `#center` slot, it's up to you to add the `hidden lg:flex` classes.
::

To customize the panel that opens when clicking on the hamburger menu, use the `#panel` slot. You could put the [NavigationTree](/pro/components/navigation-tree) component and/or the [AsideLinks](/pro/components/aside-links) components there for example, they will fit perfectly too.

```vue
<template>
  <UHeader>
    <template #panel>
      <UAsideLinks :links="links" />

      <UNavigationTree :links="mapContentNavigation(navigation)" />
    </template>
  </UHeader>
</template>
```

::callout{icon="i-heroicons-light-bulb"}
Take a look at the mobile version of this documentation to see how it looks like.
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'bg-background/75 backdrop-blur border-b border-gray-200 dark:border-gray-800 -mb-px sticky top-0 z-50',
  container: 'flex items-center justify-between gap-3 h-[--header-height]',
  left: 'lg:flex-1 flex items-center gap-1.5',
  center: '',
  right: 'flex items-center justify-end lg:flex-1 gap-1.5',
  logo: 'flex-shrink-0 font-bold text-xl text-gray-900 dark:text-white flex items-end gap-1.5',
  panel: {
    wrapper: 'fixed inset-0 z-50 overflow-y-auto bg-background lg:hidden',
    header: 'px-4 sm:px-6',
    body: 'px-4 sm:px-6 pt-3 pb-6'
  },
  button: {
    base: 'lg:hidden',
    icon: {
      open: 'i-heroicons-bars-3-20-solid',
      close: 'i-heroicons-x-mark-20-solid'
    }
  }
}
```
