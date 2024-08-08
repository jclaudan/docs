---
title: Aside
description: A sticky <aside> with customizable slots and anchors.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/aside/Aside.vue
---

## Usage

The `Aside` component will instantiate a sticky `<aside>` element, displayed only after the `lg` breakpoint with a `min-height` based on the [`--header-height` variable](/pro/getting-started/theming#variables).

Use the `links` prop to display a list of links at the top of the Aside and the `#top` or `#bottom` slots to display content above or below the links.

::component-example
---
extraClass: 'h-96'
component: AsideExample
componentClass: 'w-60 !py-0'
---
::

You'll usually use this component in the `#left` slot of a [Page](/pro/components/page) with a [NavigationTree](/pro/components/navigation-tree) inside.

```vue [layouts/docs.vue]
<template>
  <UContainer>
    <UPage>
      <template #left>
        <UAside :links="links">
          <UNavigationTree :links="navigationLinks" default-open :multiple="false" />
        </UAside>
      </template>

      <slot />
    </UPage>
  </UContainer>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'hidden overflow-y-auto lg:block lg:max-h-[calc(100vh-var(--header-height))] lg:sticky lg:top-[--header-height] py-8 lg:px-4 lg:-mx-4',
  top: {
    wrapper: 'sticky -top-8 -mt-8 pointer-events-none z-[1]',
    header: 'h-8 bg-background -mx-4 px-4',
    body: 'bg-background relative pointer-events-auto flex -mx-4 px-4',
    footer: 'h-8 bg-gradient-to-b from-background -mx-4 px-4'
  }
}

```
