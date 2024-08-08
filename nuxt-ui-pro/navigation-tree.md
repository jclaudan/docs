---
title: NavigationTree
description: A ready to use links tree to navigate between pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/navigation/NavigationTree.vue
---

## Usage

Pass a tree of links with their children to the `links` prop, this will automatically create an accordion when there are children or display a simple link otherwise:

::callout{icon="i-heroicons-light-bulb"}
Use the [`mapContentNavigation`](/pro/getting-started/content#mapcontentnavigation) util to transform `@nuxt/content` navigation into `@nuxt/ui-pro` links.
::

::component-example
---
component: NavigationTreeExample
componentClass: 'w-full'
---
::

### Multiple

You can disallow multiple accordion items to be open at the same time by setting the `multiple` prop to `false` (defaults to `true`):

```vue
<template>
  <UNavigationTree :links="links" :multiple="false" />
</template>
```

### Default open

You can set the `default-open` prop to `true` to automatically open the tree matching the current route (defaults to `false`):

```vue
<template>
  <UNavigationTree :links="links" default-open />
</template>
```

---

You'll usually use this component in an [Aside](/pro/components/aside) component or in the `#panel` slot of an [Header](/pro/components/header):

```vue [layouts/docs.vue]
<template>
  <UContainer>
    <UPage>
      <template #left>
        <UAside>
          <UNavigationTree :links="mapContentNavigation(navigation)" />
        </UAside>
      </template>

      <slot />
    </UPage>
  </UContainer>
</template>
```

```vue [components/Header.vue]
<template>
  <UHeader :links="links">
    <template #logo>
      <Logo class="w-auto h-6" />
    </template>

    <template #right>
      <UColorModeButton />
    </template>

    <template #panel>
      <UNavigationTree :links="mapContentNavigation(navigation)" default-open :multiple="false" />
    </template>
  </UHeader>
</template>
```

## Props

:component-props

## Config

```yml
{
  wrapper: 'space-y-3',
  accordion: {},
  links: {}
}
```
