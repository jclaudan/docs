---
title: BlogPost
description: A customizable <article> to display in your blog pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/blog/BlogPost.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/blog) to see how you can build your own blog! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/blog/index.vue))
::

## Usage

The `BlogPost` component is a pre-built `<article>` element that you can use in a [BlogList](/pro/components/blog-list).

Use the `title`, `description`, `date`, `image`, `badge` and `authors` props to customize the article.

You can also pass any property from the [NuxtLink](https://nuxt.com/docs/api/components/nuxt-link#props) component such as `to`, `target`, `exact`, etc.

::component-card
---
props:
  title: 'Nuxt 3.9'
  description: 'Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive server components, new composables, a new loading API and more.'
  date: 'Dec 25, 2023'
  orientation: vertical
  image:
    src: 'https://picsum.photos/640/360'
    alt: 'Nuxt 3.9'
  authors:
    - name: Daniel Roe
      avatar:
        src: https://github.com/danielroe.png
        target: _blank
      to: https://twitter.com/danielcroe
  badge:
    label: 'Release'
excludedProps:
  - badge
  - image
  - date
  - authors
---
::

The `image` prop can be a string that will be used as the `src` attribute of an `<img>` element, or an object with any of the `<img>` attributes.

::callout{icon="i-heroicons-exclamation-triangle"}
The [`<NuxtImg>`](https://image.nuxt.com/usage/nuxt-img) component is used to display the image. You will be prompted to install `@nuxt/image` if you haven't already.
::

You can change the orientation from `vertical` to `horizontal` to display the image on the left.

::component-card
---
props:
  title: 'Nuxt 3.9'
  description: 'Nuxt 3.9 is out - a Christmas gift from the Nuxt team bringing Vite 5, interactive server components, new composables...'
  date: 'Dec 25, 2023'
  orientation: horizontal
  image:
    src: 'https://picsum.photos/640/360'
    alt: 'Nuxt 3.9'
  authors:
    - name: Daniel Roe
      avatar:
        src: https://github.com/danielroe.png
        target: _blank
      to: https://twitter.com/danielcroe
  badge:
    label: 'Release'
excludedProps:
  - badge
  - image
  - date
  - authors
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'relative group flex flex-col w-full gap-y-6',
  image: {
    wrapper: 'ring-1 ring-gray-200 dark:ring-gray-800 relative overflow-hidden aspect-[16/9] w-full rounded-lg pointer-events-none',
    base: 'object-cover object-top w-full h-full transform transition-transform duration-200 group-hover:scale-105'
  },
  container: 'flex flex-col justify-between flex-1',
  inner: 'flex-1',
  badge: {
    wrapper: 'mb-3',
    base: ''
  },
  title: 'text-gray-900 dark:text-white text-xl font-semibold truncate group-hover:text-gray-600 dark:group-hover:text-gray-300 transition-colors duration-200',
  description: 'text-base text-gray-500 dark:text-gray-400 mt-1',
  date: 'text-sm text-gray-500 dark:text-gray-400 font-medium pointer-events-none',
  authors: {
    wrapper: 'relative flex items-center gap-x-3 mt-4',
    avatar: {
      base: 'relative ring-1 lg:hover:scale-105 lg:hover:ring-primary-500 dark:lg:hover:ring-primary-400 transition-transform',
      size: 'xs'
    }
  }
}
```
