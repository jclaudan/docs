---
title: LandingCTA
description: A pre-built Card to display a call to action panel in your landing pages.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingCTA.vue
---

## Usage

The `LandingCTA` component will wrap your content in a [Card](/components/card).

Use the `title`, `description` and `icon` props to customize the content of card.

::component-card{slug="ULandingCTA"}
---
props:
  title: Trusted and supported by our amazing community
  description: We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success.
  card: true
---
::

::callout{icon="i-heroicons-light-bulb"}
You can disable its border and card style by setting the `card` prop to `false`.
::

You can add anything you want in the default slot, a gradient or an image for example (this will render better on full-screen).

You can change the `align` prop from `center` to `left` or `right` to position the slot horizontaly.

::component-card{slug="ULandingCTA"}
---
props:
  title: Join us
  description: Incididunt fugiat duis in.
  align: left
  card: true
code: |

  <img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

Use the `links` prop to add some [Buttons](/components/button) below the description.

::component-card{slug="ULandingCTA"}
---
props:
  title: Trusted and supported by our amazing community
  description: We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success.
  card: true
  links:
    - label: 'Get started'
      color: 'gray'
      size: 'md'
    - label: 'Learn more'
      variant: 'link'
      color: 'gray'
      size: 'md'
      trailingIcon: 'i-heroicons-arrow-right-20-solid'
excludedProps:
  - links
---
::

This component can be put directly inside a [LandingSection](/pro/components/landing-section) or a [Container](/components/container) directly with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
cta:
  title: Trusted and supported by our amazing community
  description: We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success.
  links:
    - label: 'Get started'
      color: 'gray'
      size: 'md'
    - label: 'Learn more'
      variant: 'link'
      color: 'gray'
      size: 'md'
      trailingIcon: 'i-heroicons-arrow-right-20-solid'
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection>
    <ULandingCTA v-bind="page.cta" card />
  </ULandingSection>
</template>
```

## Slots

:component-slots{slug="ULandingCTA"}

## Props

:component-props{slug="ULandingCTA"}

## Config

```yml
{
  wrapper: 'relative',
  container: 'text-center',
  body: {
    base: 'flex flex-col gap-16 sm:gap-y-24',
    padding: 'py-24 sm:py-32 sm:px-16'
  },
  title: 'text-3xl font-bold tracking-tight text-gray-900 dark:text-white sm:text-4xl',
  description: 'mt-6 text-lg/8 text-gray-600 dark:text-gray-300',
  links: 'mt-10 flex items-center justify-center gap-x-6'
}
```
