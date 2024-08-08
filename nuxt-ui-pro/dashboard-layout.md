---
title: DashboardLayout
description: A wrapper for your dashboard layout.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardLayout.vue
---

## Usage

The `DashboardLayout` component is meant to be the root component of your layout. It ensures a consistent placement between all [DashboardPanel](/pro/components/dashboard-panel) and [DashboardPage](/pro/components/dashboard-page).

```vue [layouts/default.vue]
<template>
  <UDashboardLayout>
    <UDashboardPanel>
      <UDashboardNavbar />

      <UDashboardSidebar />
    </UDashboardPanel>

    <slot />
  </UDashboardLayout>
</template>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'fixed inset-0 flex overflow-hidden'
}
```
