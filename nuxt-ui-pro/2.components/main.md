---
title: Main
description: A <main> component to fill the screen.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/main/Main.vue
---

## Usage

The `Main` component will instantiate a `<main>` tag and set the `min-height` to fill the screen based on the [`--header-height` variable](/pro/getting-started/theming#variables), the footer will be pushed out of the screen.

```vue [app.vue]
<template>
  <UHeader />

  <UMain>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </UMain>

  <UFooter />
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'min-h-[calc(100vh-var(--header-height))]'
}
```
