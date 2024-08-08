---
title: DashboardSection
description: A customizable section to display content in a DashboardPanelContent.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardSection.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [Dashboard template](https://dashboard-template.nuxt.dev/settings) to see what you can do! ([view source](https://github.com/nuxt-ui-pro/dashboard/blob/main/app/pages/settings/index.vue#L49))
::

## Usage

The `DashboardSection` component is used to group related content together.

Use the `icon`, `title` and `description` props to customize the content of the section.

::component-card
---
padding: false
componentClass: 'w-full leading-6 px-4 mt-6'
baseProps:
  class: 'px-4 mt-6'
props:
  icon: i-heroicons-user
  title: Profile
  description: This information will be displayed publicly.
  orientation: vertical
---
::

You can also add some [Buttons](/components/button) with the `links` prop or use the `#links` slot.

::component-card
---
padding: false
componentClass: 'w-full leading-6 px-4 mt-6'
props:
  icon: i-heroicons-user
  title: Profile
  description: This information will be displayed publicly.
  links:
    - label: 'Save changes'
      color: 'black'
excludedProps:
  - links
---
::

---

The `DashboardSection` is generally placed inside a [DashboardPanelContent](/pro/components/dashboard-panel-content).

```vue [pages/settings/index.vue]
<template>
  <UDashboardPanelContent>
    <UDashboardSection title="Theme">
      <template #links>
        <UColorModeSelect />
      </template>
    </UDashboardSection>

    <UDivider class="mb-4" />

    <UDashboardSection title="Profile">
      <template #links>
        <UButton type="submit" label="Save changes" color="black" />
      </template>

      <UFormGroup>
        <UInput />
      </UFormGroup>
    </UDashboardSection>
  </UDashboardPanelContent>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'divide-y divide-gray-200 dark:divide-gray-800 space-y-6 *:pt-6 first:*:pt-2 first:*:pt-0 mb-6',
  container: 'flex flex-wrap items-center justify-between gap-4',
  inner: 'flex items-start gap-4',
  title: 'text-gray-900 dark:text-white font-semibold',
  description: 'mt-1 text-sm text-gray-500 dark:text-gray-400',
  links: 'flex flex-wrap items-center gap-1.5',
  icon: {
    wrapper: 'inline-flex',
    base: 'w-12 h-12 flex-shrink-0 text-gray-900 dark:text-white'
  }
}
```
