---
title: LandingTestimonial
description: A pre-built Card to display a testimonial in your landing pages.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingTestimonial.vue
---

## Usage

The `LandingTestimonial` component will wrap your content in a [Card](/components/card).

Use the `quote`, `icon` and `author` props to customize the content of card.

::component-card
---
props:
  icon: i-simple-icons-google
  quote: Aliquip irure laboris deserunt in dolore in consectetur ex duis. Mollit ad esse ipsum irure id veniam irure culpa dolore labore.
  author:
    name: Rose Roberson
    description: CEO at Google
    to: https://google.com
    target: _blank
    avatar:
      src: https://i.pravatar.cc/120?img=1
      loading: lazy
  card: true
excludedProps:
  - icon
  - author
---
::

::callout{icon="i-heroicons-light-bulb"}
You can disable its border and card style by setting the `card` prop to `false`.
::

This component can be put directly inside a [PageColumns](/pro/components/page-columns) with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
testimonials:
  title: What people are saying
  description: Hear from our customers about their experience.
  items:
    - quote: Nostrud tempor sunt fugiat.
      author:
        name: Rose Roberson
        description: CEO at Company
        avatar:
          src: https://i.pravatar.cc/120?img=1
    - quote: Eiusmod dolor aute ut nulla pariatur officia consequat aute amet exercitation.
      author:
        name: Chace Rodgers
        description: CEO at Company
        avatar:
          src: https://i.pravatar.cc/120?img=7
    - quote: Id duis velit enim officia ad nisi incididunt magna ex dolor minim deserunt dolor.
      author:
        name: Cornelius Sheppard
        description: CEO at Company
        avatar:
          src: https://i.pravatar.cc/120?img=3
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection :title="page.testimonials.title" :description="page.testimonials.description">
    <UPageColumns>
      <!-- Hack for Safari -->
      <div v-for="(testimonial, index) in page.testimonials.items" :key="index" class="break-inside-avoid">
        <ULandingTestimonial v-bind="testimonial" />
      </div>
    </UPageColumns>
  </ULandingSection>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  body: {
    base: 'flex flex-col',
    padding: ''
  },
  wrapper: 'relative',
  quote: 'text-gray-600 dark:text-gray-300',
  icon: {
    wrapper: 'mb-6 flex',
    base: 'w-8 h-8 flex-shrink-0 text-gray-900 dark:text-white'
  },
  author: {
    wrapper: 'flex items-center gap-3 mt-6 relative',
    name: 'font-semibold text-gray-900 dark:text-white text-sm',
    description: 'text-gray-500 dark:text-gray-400 text-sm',
    avatar: {
      base: '',
      size: 'md'
    }
  }
}
```
