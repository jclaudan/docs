---
title: BlogList
description: Display your BlogPost in an horizontal / vertical list.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/blog/BlogList.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/blog) to see how you can build your own blog! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/blog/index.vue))
::

## Usage

Use some [BlogPost](/pro/components/blog-post) to display articles horizontally or vertically.

::component-card
---
extraClass: '!p-8'
props:
  orientation: horizontal
code: |
  <UBlogPost title="Nuxt 3.9" description="Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive..." />
  <UBlogPost title="Nuxt DevTools 1.0" description="Nuxt DevTools v1.0 is out, generally available to all Nuxt projects!" />
  <UBlogPost title="Nuxt 3.8" description="Nuxt 3.8 is out, bringing built-in DevTools, automatic Nuxt Image install, a new app..." />
---

#default
:u-blog-post{title="Nuxt 3.9" description="Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive..." image="https://picsum.photos/id/10/640/360"}
:u-blog-post{title="Nuxt DevTools 1.0" description="Nuxt DevTools v1.0 is out, generally available to all Nuxt projects!" image="https://picsum.photos/id/11/640/360"}
:u-blog-post{title="Nuxt 3.8" description="Nuxt 3.8 is out, bringing built-in DevTools, automatic Nuxt Image install, a new app..." image="https://picsum.photos/id/12/640/360"}
::

When using the vertical orientation on the `BlogList` component, you will want to use the `BlogPost` components with the `horizontal` orientation.

::component-card
---
extraClass: '!p-8'
props:
  orientation: vertical
code: |
  <UBlogPost title="Nuxt 3.9" description="Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive..." orientation="horizontal" />
  <UBlogPost title="Nuxt DevTools 1.0" description="Nuxt DevTools v1.0 is out, generally available to all Nuxt projects!" orientation="horizontal" />
  <UBlogPost title="Nuxt 3.8" description="Nuxt 3.8 is out, bringing built-in DevTools, automatic Nuxt Image install, a new app..." orientation="horizontal" />
---

#default
:u-blog-post{title="Nuxt 3.9" description="Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive..." image="https://picsum.photos/id/10/640/360" orientation="horizontal"}
:u-blog-post{title="Nuxt DevTools 1.0" description="Nuxt DevTools v1.0 is out, generally available to all Nuxt projects!" image="https://picsum.photos/id/11/640/360" orientation="horizontal"}
:u-blog-post{title="Nuxt 3.8" description="Nuxt 3.8 is out, bringing built-in DevTools, automatic Nuxt Image install, a new app..." image="https://picsum.photos/id/12/640/360" orientation="horizontal"}
::

This component can be put directly inside a [LandingSection](/pro/components/landing-section) with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
blog:
  title: Blog
  description: Read the latest news from our blog.
  posts:
    - title: Nuxt 3.9
      description: Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive...
      image:
        src: https://picsum.photos/id/10/640/360
        alt: Nuxt 3.9
    - title: Nuxt DevTools 1.0
      description: Nuxt DevTools v1.0 is out, generally available to all Nuxt projects!
      image:
        src: https://picsum.photos/id/11/640/360
        alt: Nuxt DevTools 1.0
    - title: Nuxt 3.8
      description: Nuxt 3.8 is out, bringing built-in DevTools, automatic Nuxt Image install, a new app...
      image:
        src: https://picsum.photos/id/12/640/360
        alt: Nuxt 3.8
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection :title="page.blog.title" :description="page.blog.description">
    <UBlogList>
      <UBlogPost v-for="(post, index) in page.blog.posts" :key="index" v-bind="post" />
    </UBlogList>
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
  wrapper: 'flex flex-col lg:grid lg:grid-cols-3 gap-x-8 gap-y-16'
}
```
