---
title: DashboardSearch
description: A ready to use CommandPalette to add to your dashboard.
links:
  - label: CommandPalette
    icon: i-simple-icons-nuxtdotjs
    to: /components/command-palette
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSearch.vue
---

## Usage

Use the `groups` prop to provide commands like a normal [CommandPalette](/components/command-palette).

You can open the CommandPalette by pressing :shortcut{value="meta"} :shortcut{value="K"} or using the [DashboardSearchButton](/pro/components/dashboard-search-button) component. You can also do this manually with `const { toggleDashboardSearch } = useUIState()`{lang="ts"}.

::component-example
---
extraClass: 'overflow-hidden'
padding: false
component: DashboardSearchExample
iframe: true
iframeProps:
  height: 500
hiddenCode: true
---
::

You'll usually use this component in your `app.vue` or layout:

```vue [layouts/default.vue]
<script setup lang="ts">
const links = [{
  id: 'home',
  label: 'Home',
  icon: 'i-heroicons-home',
  to: '/',
  tooltip: {
    text: 'Home',
    shortcuts: ['G', 'H']
  }
}, {
  id: 'inbox',
  label: 'Inbox',
  icon: 'i-heroicons-inbox',
  to: '/inbox',
  badge: '4',
  tooltip: {
    text: 'Inbox',
    shortcuts: ['G', 'I']
  }
}, {
  id: 'users',
  label: 'Users',
  icon: 'i-heroicons-user-group',
  to: '/users',
  tooltip: {
    text: 'Users',
    shortcuts: ['G', 'U']
  }
}, {
  id: 'settings',
  label: 'Settings',
  to: '/settings',
  icon: 'i-heroicons-cog-8-tooth',
  children: [{
    label: 'General',
    to: '/settings',
    exact: true
  }, {
    label: 'Members',
    to: '/settings/members'
  }, {
    label: 'Notifications',
    to: '/settings/notifications'
  }],
  tooltip: {
    text: 'Settings',
    shortcuts: ['G', 'S']
  }
}]

const groups = [{
  key: 'links',
  label: 'Go to',
  commands: links.map(link => ({ ...link, shortcuts: link.tooltip?.shortcuts }))
}]
</script>

<template>
  <UDashboardLayout>
    <UDashboardPanel>
      <UDashboardNavbar />

      <UDashboardSidebar>
        <UDashboardSidebarLinks :links="links" />
      </UDashboardSidebar>
    </UDashboardPanel>

    <slot />

    <ClientOnly>
      <LazyUDashboardSearch :groups="groups" />
    </ClientOnly>
  </UDashboardLayout>
</template>
```

It is recommended to wrap the `DashboardSearch` component in a [ClientOnly](https://nuxt.com/docs/api/components/client-only) component so it's not rendered on the server.

### Color Mode

By default, a group of commands will be added to the command palette so you can switch between light and dark mode. This will only take effect if the `colorMode` is not forced in a specific page which can be achieved through `definePageMeta`:

```ts [pages/index.vue]
<script setup lang="ts">
definePageMeta({
  colorMode: 'dark'
})
</script>
```

You can also disable this behavior manually by setting the `hide-color-mode` prop: `<UDashboardSearch hide-color-mode />`. This can be quite useful when forcing the color mode for the entire app in your `nuxt.config.ts`:

```ts [nuxt.config.ts]
export default defineNuxtConfig({
  colorMode: {
    preference: 'light'
  }
})
```

## Props

:component-props

## Config

```yml
{
  padding: 'p-0 sm:p-4',
  rounded: 'rounded-none sm:rounded-lg',
  width: 'sm:max-w-3xl',
  height: 'h-dvh sm:h-[28rem]',
  commandPalette: {
    input: {
      height: 'h-[--header-height] sm:h-12',
      icon: {
        size: 'h-5 w-5',
        padding: 'ps-11'
      }
    },
    group: {
      command: {
        prefix: `!text-foreground after:content-['_>']`
      }
    },
    container: 'scroll-py-10'
  },
  fileIcon: {
    name: 'i-heroicons-document-text'
  },
  default: {
    closeButton: {
      icon: 'i-heroicons-x-mark-20-solid',
      color: 'gray',
      variant: 'ghost',
      size: 'sm'
    }
  }
}
```
