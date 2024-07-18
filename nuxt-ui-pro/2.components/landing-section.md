---
title: LandingSection
description: A customizable section for your landing pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingSection.vue
---

## Usage

The `LandingSection` component will wrap your content in a [Container](/components/container) but the wrapper takes the full width of the screen so you can easily change the background.

Use the `headline`, `title` and `description` props to customize the content of the section.

::component-card
---
padding: false
props:
  headline: Pro
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
---
::

Use the `icon` prop to add an icon on top of the title.

::component-card
---
padding: false
props:
  icon: i-heroicons-rocket-launch
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
excludedProps:
  - icon
---
::

You can add anything you want in the default slot, an image, a code-block using the [`MDC`](https://github.com/nuxt-modules/mdc/blob/main/src/runtime/components/MDC.vue) component (when using `@nuxt/content`), a [LandingGrid](/pro/components/landing-grid), a [PageGrid](/pro/components/page-grid), a [PricingGrid](/pro/components/pricing-grid), a [LandingFAQ](/pro/components/landing-faq), a [LandingCTA](/pro/components/landing-cta), etc.

You can change the `align` prop from `center` to `left` or `right` to position the slot horizontaly.

::component-card
---
padding: false
props:
  headline: Pro
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
  align: center
code: |

  <img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/640/360" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

Use the `links` prop to add some [Buttons](/components/button) below the description. Those will be rendered below the default slot when the `align` prop is set to `center`.

::component-card
---
padding: false
props:
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
  links:
    - label: Explore components
      color: gray
      trailingIcon: 'i-heroicons-arrow-right'
      size: lg
  align: 'left'
excludedProps:
  - links
code: |

  <img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

Use the `features` prop to add a list of features below the description. Those will be rendered as a grid when the `align` prop is set to `center`.

::component-card
---
padding: false
props:
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
  features:
    - name: Fully customizable
      description: Like Nuxt UI, change the style of any component from your App Config or customize them specifically through the ui prop.
      icon: i-heroicons-wrench-screwdriver
    - name: Slots for everything
      description: Each component leverages the power of Vue's slots to give you the flexibility to build anything.
      icon: i-heroicons-square-3-stack-3d
  align: 'right'
excludedProps:
  - features
code: |

  <img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
---

<img src="https://picsum.photos/360/640" class="w-full rounded-md shadow-xl ring-1 ring-gray-300 dark:ring-gray-700">
::

You can also use the `#headline`, `#title`, `#description` and `#links` slots to customize the content of the section. This can be quite useful when using `@nuxt/content` if your content has HTML for example:

```yml [content/index.yml]
feature:
  title: The freedom to build anything
  description: Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.
  code: |
    ```vue [app.vue]
    <template>
      <UHeader :links="links" />

      <UMain>
        <ULandingHero title="Hello World" />

        <ULandingSection title="Features">
          <UPageGrid>
            <ULandingCard title="First Card" />
            <ULandingCard title="Second Card" />
            <ULandingCard title="Third Card" />
          </UPageGrid>
        </ULandingSection>
      </UMain>

      <UFooter />
    </template>
    ```
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
     <template #title>
      <span v-html="page.feature.title" />
    </template>

    <template #description>
      <span v-html="page.feature.description" />
    </template>

    <MDC
      v-if="page.feature.code"
      :value="page.feature.code"
      tag="pre"
      class="prose prose-primary dark:prose-invert max-w-none"
    />
  </ULandingSection>
</template>
```

You can use the `slot` prop to change the default slot name, this can be useful when using `@nuxt/content` and iterating over a list of sections for example:

```yml [content/index.yml]
sections:
  - title: 'The power of<br><span class="text-primary">Vue Components</span>'
    description: 'We love Vue Single-File Components as much as you do.'
    class: 'dark bg-gray-900'
    align: left
    slot: code
    code: |
      ```vue [app.vue]
      <template>
        <NuxtPage />
      </template>
      ```
  - title: 'Compose with<br><span class="text-primary">everything you need.</span>'
    slot: features
    features:
      - title: 'Routing & Layouts'
        description: 'File based routing system to build complex views and interfaces with a powerful and conventional approach.'
        icon: 'i-ph-signpost-duotone'
      - title: 'Data Fetching'
        description: 'Composables that run on the server to fetch data for your components and enable you to render content in different ways.'
        icon: 'i-ph-plugs-connected-duotone'
      - title: 'Assets & Style'
        description: 'Image, Font and Script optizations with a built-in support for CSS Modules, Sass, PostCSS, CSS-in-JS and more.'
        icon: 'i-ph-image-duotone'
```

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection v-for="(section, index) of page.sections" :key="index" :slot="section.slot" :class="section.class" :align="section.align" :links="section.links">
    <template #title>
      <span v-html="section.title" />
    </template>

    <template #description>
      <span v-if="section.description" v-html="section.description" />
    </template>

    <template #code>
      <MDC :value="section.code" tag="pre" class="prose prose-primary dark:prose-invert max-w-none" />
    </template>

    <template #features>
      <UPageGrid>
        <UPageCard v-for="(feature, index) in features" :key="index" v-bind="feature" />
      </UPageGrid>
    </template>
  </ULandingSection>
</template>
```

You can use the `#top` and `#bottom` slots to add content above and below the container, this can be useful when adding some absolute positioned svgs for example.

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'py-24 sm:py-32',
  container: 'gap-16 sm:gap-y-24 flex flex-col',
  base: 'text-center flex flex-col items-center',
  icon: {
    wrapper: 'flex mb-6',
    base: 'w-10 h-10 flex-shrink-0 text-primary'
  },
  headline: 'mb-2 text-base/7 font-semibold text-primary',
  title: 'text-3xl font-bold tracking-tight text-gray-900 dark:text-white sm:text-4xl lg:text-5xl',
  description: 'mt-6 text-lg/8 text-gray-600 dark:text-gray-300',
  links: 'mt-8 flex flex-wrap gap-x-3 gap-y-1.5',
  features: {
    wrapper: {
      base: 'mt-6 leading-7',
      list: 'space-y-4',
      grid: 'grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 lg:gap-x-8 lg:gap-y-16'
    },
    base: 'relative pl-8',
    name: 'font-semibold text-gray-900 dark:text-white',
    description: 'text-gray-500 dark:text-gray-400 leading-6',
    icon: {
      base: 'absolute left-0 top-1 h-5 w-5 text-primary',
      name: 'i-heroicons-check-circle-20-solid'
    }
  }
}
```
