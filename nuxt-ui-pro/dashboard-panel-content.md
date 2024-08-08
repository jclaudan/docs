---
title: DashboardPanelContent
description: A scrollable container for your DashboardPanel.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardPanelContent.vue
---

## Usage

Used inside a [DashboardPanel](/pro/components/dashboard-panel), the `DashboardPanelContent` provides a scrollable container with some padding to display content such as [DashboardCard](/pro/components/dashboard-card), [DashboardSection](/pro/components/dashboard-section) or your own custom components.

```vue [pages/index.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel>
      <UDashboardNavbar title="Home" />

      <UDashboardPanelContent>
        <UDashboardCard />

        <div class="grid lg:grid-cols-2 gap-4 mt-4">
          <UDashboardCard />
          <UDashboardCard />
        </div>
      </UDashboardPanelContent>
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'p-4 flex-1 flex flex-col overflow-y-auto'
}
```
