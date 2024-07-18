---
title: DashboardSidebarLinks
description: A list of collapsible and draggable links to display in a DashboardSidebar.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSidebarLinks.vue
---

## Usage

Pass a tree of links with their children to the `links` prop of the `DashboardSidebarLinks` component.

Each link can have a `label`, `icon`, [`avatar`](/components/avatar), [`chip`](/components/chip), [`badge`](/components/badge), [`tooltip`](/components/tooltip), etc. (see the [props](#props) section for more details). You can also pass any property from the [NuxtLink](https://nuxt.com/docs/api/components/nuxt-link#props) component such as `to`, `target`, `exact`, etc.

::component-example
---
componentClass: 'w-48'
component: DashboardSidebarLinksExample
---
::

::callout{icon="i-heroicons-light-bulb"}
The children have a specific style with a dot and a border when no icon, avatar or chip is provided.
::

### Collapsible

You can use the `collapsible` attribute (defaults to `true`) to prevent a link with children from being collapsible.

::component-example
---
componentClass: 'w-48'
component: DashboardSidebarLinksCollapsibleExample
---
::

### Default open

You can use the `defaultOpen` attribute (defaults to `true`) to make a collapsible link (with children) open by default.

This can be useful if you want to control the open state based on the current route.

::component-example
---
componentClass: 'w-48'
component: DashboardSidebarLinksDefaultOpenExample
---
::

### Draggable

You can use the `draggable` attribute to make the children draggable. You'll need to listen to the `@update:links` event to update your links.

::component-example
---
componentClass: 'w-48'
component: DashboardSidebarLinksDraggableExample
---
::

---

You can use multiple instances of the `DashboardSidebarLinks` component inside the `DashboardSidebar` component to create different sections.

```vue [layouts/default.vue]
<template>
  <UDashboardLayout>
    <UDashboardPanel>
      <UDashboardNavbar />

      <UDashboardSidebar>
        <UDashboardSidebarLinks />

        <UDivider />

        <UDashboardSidebarLinks />

        <div class="flex-1" />

        <UDashboardSidebarLinks />

        <UDivider class="sticky bottom-0" />
      </UDashboardSidebar>
    </UDashboardPanel>

    <slot />
  </UDashboardLayout>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative !min-h-[auto] !min-w-[auto]',
  container: '!overflow-visible',
  base: 'group relative flex items-center gap-1.5 px-2.5 py-1.5 w-full rounded-md font-medium text-sm focus:outline-none focus-visible:outline-none dark:focus-visible:outline-none focus-visible:before:ring-inset focus-visible:before:ring-2 focus-visible:before:ring-primary-500 dark:focus-visible:before:ring-primary-400 before:absolute before:inset-px before:rounded-md disabled:cursor-not-allowed disabled:opacity-75',
  active: 'text-gray-900 dark:text-white before:bg-gray-100 dark:before:bg-gray-800',
  inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white hover:before:bg-gray-50 dark:hover:before:bg-gray-800/50',
  icon: {
    base: 'flex-shrink-0 w-5 h-5 relative',
    active: 'text-gray-900 dark:text-white',
    inactive: 'text-gray-400 dark:text-gray-500 group-hover:text-gray-700 dark:group-hover:text-gray-200'
  },
  trailingIcon: {
    name: i-heroicons-chevron-down-20-solid,
    base: 'ml-auto w-5 h-5 transform transition-transform duration-200 flex-shrink-0',
    active: '',
    inactive: '-rotate-90'
  },
  avatar: {
    base: 'flex-shrink-0',
    size: '2xs'
  },
  chip: {
    base: 'flex-shrink-0 mx-2.5',
    size: 'sm'
  },
  badge: {
    base: 'flex-shrink-0 ml-auto relative rounded',
    color: 'gray',
    variant: 'solid',
    size: 'xs'
  },
  label: 'text-sm truncate relative',
  dot: {
    wrapper: 'w-px h-full mx-[9.5px] bg-gray-200 dark:bg-gray-700 relative',
    after: 'after:absolute after:z-[1] after:w-px after:h-full after:bg-gray-200 after:dark:bg-gray-700 after:transform after:translate-y-full',
    base: 'w-1 h-1 rounded-full absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2',
    active: 'bg-gray-900 dark:bg-white',
    inactive: 'bg-gray-400 dark:bg-gray-500 group-hover:bg-gray-700 dark:group-hover:bg-gray-200'
  },
  tooltip: {
    strategy: 'override',
    transition: {
      enterActiveClass: 'transition ease-out duration-200',
      enterFromClass: 'opacity-0',
      enterToClass: 'opacity-100',
      leaveActiveClass: 'transition ease-in duration-150',
      leaveFromClass: 'opacity-100',
      leaveToClass: 'opacity-0'
    }
  },
  transition: {
    enterActiveClass: 'overflow-hidden transition-[height] duration-200 ease-out',
    leaveActiveClass: 'overflow-hidden transition-[height] duration-200 ease-out'
  }
}
```
