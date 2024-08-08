---
title: DashboardToolbar
description: A sub-navbar to add actions to your DashboardPanel.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardToolbar.vue
---

## Usage

The `DashboardToolbar` component acts as a sub-navbar with a pre-defined height matching exactly the `#header` slot of a [DashboardSidebar](/pro/components/dashboard-sidebar) or even a [Table](/components/table) row.

You can either use the `#default` or the `#left` and `#right` slots to add actions to the toolbar.

Put anything you like inside, for example an [HorizontalNavigation](/components/horizontal-navigation) component.

::component-example
---
componentClass: 'w-full'
component: DashboardToolbarExample
---
::

---

The `DashboardToolbar` is generally placed inside a [DashboardPanel](/pro/components/dashboard-panel) under the [DashboardNavbar](/pro/components/dashboard-navbar).

```vue [pages/users.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel>
      <UDashboardNavbar title="Users" />

      <UDashboardToolbar>
        <template #left>
          <USelectMenu icon="i-heroicons-check" placeholder="Status" multiple />
          <USelectMenu icon="i-heroicons-map-pin" placeholder="Location" multiple />
        </template>

        <template #right>
          <USelectMenu label="Display" icon="i-heroicons-computer-desktop" multiple />
        </template>
      </UDashboardToolbar>
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'min-h-[49px] flex-shrink-0 flex items-center border-b border-gray-200 dark:border-gray-800 px-4 py-2 gap-x-4',
  container: 'flex items-center justify-between flex-1 gap-x-1.5',
  left: 'flex items-stretch gap-1.5',
  right: 'flex items-stretch gap-1.5'
}
```
