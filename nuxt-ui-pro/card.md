---
title: Card
description: A card to link your content with other pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Card.vue
---

## Usage

Use the `title` and `icon` props to display a card component in your content, the description will be displayed in the default slot with full **markdown** support.

::component-example
---
prose: true
extraClass: 'flex-col'
---

::card{title="Components" icon="i-heroicons-cube-transparent"}
Discover all the components available in **Nuxt UI Pro**.
::

#code
```mdc
::card{title="Components" icon="i-heroicons-cube-transparent"}
Discover all the components available in **Nuxt UI Pro**.
::
```
::

### Color

You can use the `color` prop to change the color of the card:

::component-example
---
prose: true
extraClass: 'flex-col'
---

::card{title="Components" icon="i-heroicons-cube-transparent" color="red"}
Discover all the components available in **Nuxt UI Pro**.
::

#code
```mdc
::card{title="Components" icon="i-heroicons-cube-transparent" color="red"}
Discover all the components available in **Nuxt UI Pro**.
::
```
::

### Link

You can add a `to` prop to make it a link, an external icon will be displayed when the link is external:

::component-example
---
prose: true
extraClass: 'flex-col'
---

::card{title="Components" icon="i-heroicons-cube" to="https://nuxt.com/docs/api/components/client-only" target="_blank"}
Explore Nuxt built-in components for pages, layouts, head, and more.
::

#code
```mdc
::card
---
title: Components
icon: i-heroicons-cube
to: https://nuxt.com/docs/api/components/client-only
target: _blank
---
Explore Nuxt built-in components for pages, layouts, head, and more.
::
```
::

## Props

:component-props{slug="Callout"}

## Config

```yml
{
  wrapper: 'relative group overflow-hidden flex items-center rounded-lg',
  to: 'hover:ring-1 hover:ring-[--color-light] dark:hover:ring-[--color-dark] hover:bg-gray-100/50 dark:hover:bg-gray-800/50',
  icon: {
    base: 'w-6 h-6 mb-4 inline-flex items-center text-[--color-light] dark:text-[--color-dark] pointer-events-none'
  },
  body: {
    base: 'flex-1'
  },
  externalIcon: {
    name: appConfig.ui.icons.external,
    base: 'w-4 h-4 absolute right-2 top-2 text-gray-400 dark:text-gray-500 group-hover:text-[--color-light] dark:group-hover:text-[--color-dark]'
  },
  title: 'text-gray-900 dark:text-white font-semibold text-base my-0',
  description: 'text-[15px] text-gray-500 dark:text-gray-400 mt-1 mb-0'
}
```
