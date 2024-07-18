---
title: DashboardNavbarToggle
description: A Button to toggle a DashboardPanel on mobile.
links:
  - label: Button
    icon: i-simple-icons-nuxtdotjs
    to: /components/button
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardNavbarToggle.vue
---

## Usage

This component is used internally in the `#toggle` slot of the [DashboardNavbar](/pro/components/dashboard-navbar) component. It is only visible on mobile and will open the parent [DashboardPanel](/pro/components/dashboard-panel) as a [Slideover](/components/slideover).

You can pass any prop of the [Button](/components/button) component to override the style or size, they will be forwarded.

```vue [pages/inbox.vue]
<template>
  <UDashboardPage>
    <UDashboardPanel>
      <UDashboardNavbar title="Inbox" />
    </UDashboardPanel>

    <UDashboardPanel>
      <UDashboardNavbar>
        <template #toggle>
          <UDashboardNavbarToggle icon="i-heroicons-x-mark" />
        </template>
      </UDashboardNavbar>
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

Its icon defaults to :u-icon{name="i-heroicons-bars-3-20-solid" class="align-middle"} `i-heroicons-bars-3-20-solid` from `appConfig.ui.icons.menu`. You can override it with the `icon` prop or globally in your `app.config.ts`.

::callout{icon="i-heroicons-light-bulb" to="/pro/getting-started/theming#icons"}
Read more about global icons configuration through the Nuxt App Config.
::
