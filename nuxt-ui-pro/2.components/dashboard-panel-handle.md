---
title: DashboardPanelHandle
description: A handle used in a resizable DashboardPanel.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardPanelHandle.vue
---

## Usage

This component is used internally in the `#handle` slot of the [DashboardPanel](/pro/components/dashboard-panel) component when the `resizable` prop is set. You might want to use it to change its style or behavior.

```vue [pages/inbox.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel resizable>
      <template #handle="{ onDrag }">
        <UDashboardPanelHandle :ui="{ container: 'group-hover:bg-primary-500 dark:group-hover:bg-primary-400' }" @mousedown="onDrag" />
      </template>
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'hidden md:block bg-transparent select-none absolute z-50 group w-[9px] h-full inset-y-0 -right-[5px] cursor-col-resize',
  container: 'group-hover:bg-gray-300 dark:group-hover:bg-gray-700 transition duration-200 absolute w-px h-full inset-x-0 mx-auto'
}
```
