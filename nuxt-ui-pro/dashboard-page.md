---
title: DashboardPage
description: A wrapper for your dashboard pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardPage.vue
---

## Usage

The `DashboardPage` component is meant to be the root component of your pages. It ensures a consistent layout and scrolling behavior across all [DashboardPanel](/pro/components/dashboard-panel).

```vue [pages/settings.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel>
      <UDashboardNavbar />

      <NuxtPage />
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

This demonstrates a parent page with a [NuxtPage](https://nuxt.com/docs/api/components/nuxt-page) inside the [DashboardPanel](/pro/components/dashboard-panel). This way, its children can be wrapped inside a [DashboardPanelContent](/pro/components/dashboard-panel-content).

## Props

:component-props

## Config

```yml
{
  wrapper: 'flex flex-1 w-full min-w-0'
}
```
