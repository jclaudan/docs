---
title: DashboardSidebar
description: A scrollable container to display links inside a DashboardPanel.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSidebar.vue
---

## Usage

The `DashboardSidebar` component is a scrollable container with some padding to display some [DashboardSidebarLinks](/pro/components/dashboard-sidebar-links) and contains a sticky `#header` and `#footer`.

It is generally placed inside a [DashboardPanel](/pro/components/dashboard-panel) under the [DashboardNavbar](/pro/components/dashboard-navbar) component.

```vue [layouts/default.vue]
<template>
  <UDashboardLayout>
    <UDashboardPanel>
      <UDashboardNavbar />

      <UDashboardSidebar>
        <template #header>
          <!-- Place anything you like here -->
          <UDashboardSearchButton />
        </template>

        <UDashboardSidebarLinks />

        <UDivider />

        <UDashboardSidebarLinks />

        <template #footer>
          <!-- Place anything you like here -->
        </template>
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
  wrapper: 'flex flex-col w-full flex-1 relative overflow-hidden',
  container: 'flex-grow flex flex-col min-h-0 gap-y-2 py-2',
  header: 'w-full flex flex-col px-4',
  body: 'flex-1 px-4 flex flex-col gap-y-2 overflow-y-auto',
  footer: 'flex items-center justify-between gap-x-1.5 flex-shrink-0 px-4'
}
```
