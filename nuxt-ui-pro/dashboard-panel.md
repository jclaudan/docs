---
title: DashboardPanel
description: A responsive and resizable panel to build multi-column layouts.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardPanel.vue
---

## Usage

The `DashboardPanel` component is the building block to create a multi-column layout.

::component-example
---
padding: false
component: DashboardPanelExample
---
::

### Width

By default, the `DashboardPanel` will take its content's width. You can use the `width` prop to set a fixed one.

```vue
<template>
  <UDashboardPanel :width="250" />
</template>
```

### Grow

You can use the `grow` prop to make the `DashboardPanel` take the remaining space. It can be useful for the last panel on the right side of the layout.

```vue
<template>
  <UDashboardPanel grow />
</template>
```

::callout{icon="i-heroicons-light-bulb"}
When using the `grow` prop, the right border will be removed to make the layout look seamless.
::

### Resizable

You can use the `resizable` prop to make the `DashboardPanel` resizable and set the `min` and `max` values to limit the resizing.

```vue
<template>
  <UDashboardPanel :width="300" :resizable="{ min: 200, max: 400 }" />
</template>
```

The width will be stored in a cookie to keep the layout consistent on refresh. You might want to use local storage instead by setting the `storage` key to `local` (this will only work if you've disabled `ssr` if your `nuxt.config.ts`).

```vue
<template>
  <UDashboardPanel :width="300" :resizable="{ min: 200, max: 400, storage: 'local' }" />
</template>
```

We use the [`useId` composable](https://nuxt.com/docs/api/composables/use-id) to generate a unique id. When you have multiple resizable panels, it can be useful to set a custom one through the `id` prop.

```vue
<template>
  <UDashboardPanel id="inbox" :width="400" :resizable="{ min: 300, max: 500 }" />
</template>
```

When the `resizable` prop is used, a bar will be displayed on hover at the right of the panel. You can use the `#handle` slot to customize it as described in [DashboardPanelHandle](/pro/components/dashboard-panel-handle).

### Collapsible

A two or three column layout will not be very usable on mobile. You can use the `collapsible` prop to transform the `DashboardPanel` into a [Slideover](/components/slideover) on mobile.

```vue
<template>
  <UDashboardPanel collapsible />
</template>
```

In the `useUIState` composable, we store a `isDashboardSidebarSlideoverOpen` ref to control the state of the slideover on mobile. The `DashboardPanel` will inject this to the [DashboardNavbar](/pro/components/dashboard-navbar) inside to display a toggle button.

If you want to control the state of the slideover yourself or if you have multiple panels, you can pass a `v-model` to the `DashboardPanel`.

```vue
<script setup lang="ts">
const selected = ref(null)

const isOpen = computed({
  get () {
    return !!selected.value
  },
  set (value: boolean) {
    if (!value) {
      selected.value = null
    }
  }
})
</script>

<template>
  <UDashboardPanel v-model="isOpen" collapsible />
</template>
```

::callout{icon="i-heroicons-light-bulb"}
It can be useful to change the icon of the toggle button as explained in [DashboardNavbar](/pro/components/dashboard-navbar#toggle).
::

### Side

When using the `collapsible` prop, you can use the `side` prop to set the side of the panel. The default value is `left`.

```vue
<template>
  <UDashboardPanel v-model="isOpen" collapsible side="right" />
</template>
```

---

The `DashboardPanel` can be placed inside a [DashboardLayout](/pro/components/dashboard-layout) or a [DashboardPage](/pro/components/dashboard-page).

You can put a [DashboardNavbar](/pro/components/dashboard-navbar) at the top followed by a [DashboardSidebar](/pro/components/dashboard-sidebar), a [DashboardToolbar](/pro/components/dashboard-toolbar) or a [DashboardPanelContent](/pro/components/dashboard-panel-content) to display scrollable content for example.

```vue [layouts/default.vue]
<template>
  <UDashboardLayout>
    <UDashboardPanel :width="250" :resizable="{ min: 200, max: 300 }" collapsible>
      <UDashboardNavbar />

      <UDashboardSidebar />
    </UDashboardPanel>

    <slot />
  </UDashboardLayout>
</template>
```

```vue [pages/inbox.vue]
<script setup lang="ts">
const isOpen = ref(false)
</script>

<template>
  <UDashboardPage>
    <UDashboardPanel id="inbox" :width="400" :resizable="{ min: 300, max: 500 }">
      <UDashboardNavbar title="Inbox" />

      <UDashboardPanelContent />
    </UDashboardPanel>

    <UDashboardPanel v-model="isOpen" collapsible grow side="right">
      <UDashboardNavbar />

      <UDashboardToolbar />

      <UDashboardPanelContent />
    </UDashboardPanel>
  </UDashboardPage>
</template>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'flex-col items-stretch relative w-full',
  border: 'border-b lg:border-b-0 lg:border-r border-gray-200 dark:border-gray-800 lg:w-[--width] flex-shrink-0',
  grow: 'flex-1',
  collapsible: 'hidden lg:flex',
  slideover: 'lg:hidden'
}
```
