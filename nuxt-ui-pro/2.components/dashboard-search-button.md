---
title: DashboardSearchButton
description: A pre-styled Button to open the DashboardSearch modal.
links:
  - label: Button
    icon: i-simple-icons-nuxtdotjs
    to: /components/button
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSearchButton.vue
---

## Usage

The Button is already styled and will render as an icon button if you unset the `label`. You can override all the [Button](/components/button) props as it's the root component.

::component-card
---
props:
  label: 'Search...'
---
::

You can also do this by yourself using the `useUIState` composable:

```vue
<script setup lang="ts">
const { toggleDashboardSearch, isDashboardSearchModalOpen } = useUIState()
</script>

<template>
  <UButton label="Open" @click="toggleDashboardSearch" />
</template>
```

## Props

:component-props
