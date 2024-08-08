---
title: DashboardNavbar
description: A navbar to display inside a DashboardPanel.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardNavbar.vue
---

## Usage

The `DashboardNavbar` component is meant to be the top bar of each [DashboardPanel](/pro/components/dashboard-panel). Its height is based on the [`--header-height`  variable](/pro/getting-started/theming#variables) like the [DashboardModal](/pro/components/dashboard-modal), [DashboardSlideover](/pro/components/dashboard-slideover) and [DashboardSearch](/pro/components/dashboard-search) components.

Use the `title` and [`badge`](/components/badge) props to customize the left side or use the `#left` and `#right` slots.

::component-card
---
componentClass: 'w-full'
props:
  title: Inbox
  badge: '5'
---
::

### Toggle

The [DashboardPanel](/pro/components/dashboard-panel) component transforms itself into a slideover on mobile with the `collapsible` prop. The `DashboardNavbar` inside will automatically display a toggle button next to the title on small screens.

You can use the `#toggle` slot to customize this button as described in [DashboardNavbarToggle](/pro/components/dashboard-navbar-toggle).

---

The `DashboardNavbar` is generally placed inside a [DashboardPanel](/pro/components/dashboard-panel).

```vue [pages/users.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel>
      <UDashboardNavbar title="Users" badge="5">
        <template #right>
          <UButton label="New user" trailing-icon="i-heroicons-plus" color="gray" />
        </template>
      </UDashboardNavbar>
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
  wrapper: 'h-[--header-height] flex-shrink-0 flex items-center border-b border-gray-200 dark:border-gray-800 px-4 gap-x-4 min-w-0',
  container: 'flex items-center justify-between flex-1 gap-x-1.5 min-w-0',
  left: 'flex items-stretch gap-1.5 min-w-0',
  title: 'flex items-center gap-1.5 font-semibold text-gray-900 dark:text-white min-w-0',
  badge: {
    wrapper: 'inline-flex items-center',
    base: '',
    size: 'xs',
    color: 'primary',
    variant: 'subtle'
  },
  center: 'hidden lg:flex',
  right: 'flex items-stretch flex-shrink-0 gap-1.5'
}
```
