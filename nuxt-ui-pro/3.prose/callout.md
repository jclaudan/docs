---
title: Callout
description: A callout to add eye-catching context to your content.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Callout.vue
---

## Usage

Use the default slot to display a callout component with full **markdown** support.

::component-example
---
prose: true
extraClass: 'flex-col [&>div]:!my-0'
---

::callout
This is a `callout` with full **markdown** support. It can be used to link to [another page](/pro/prose/card).
::

#code
```mdc
::callout
This is a `callout` with full **markdown** support. It can be used to link to [another page](/pro/prose/card).
::
```
::

### Icon

You can add an `icon` prop to display an icon on the left of the callout:

::component-example
---
prose: true
extraClass: 'flex-col [&>div]:!my-0'
---

::callout{icon="i-heroicons-light-bulb"}
This suggests a helpful tip.
::

#code
```mdc
::callout{icon="i-heroicons-light-bulb"}
This suggests a helpful tip.
::
```
::

### Color

You can use the `color` prop to change the color of the callout:

::component-example
---
prose: true
extraClass: 'flex-col [&>div]:!my-0'
---

::callout{icon="i-heroicons-exclamation-triangle" color="amber"}
This raises a warning to watch out for.
::

#code
```mdc
::callout{icon="i-heroicons-exclamation-triangle" color="amber"}
This raises a warning to watch out for.
::
```
::

### Link

You can add a `to` prop to make it a link, an external icon will be displayed when the link is external:

::component-example
---
prose: true
extraClass: 'flex-col [&>div]:!my-0'
---

::callout{icon="i-heroicons-light-bulb" to="https://nuxt.com" target="_blank"}
Check out this documentation.
::

#code
```mdc
::callout{icon="i-heroicons-light-bulb" to="https://nuxt.com" target="_blank"}
Check out this documentation.
::
```
::

## Props

:component-props{slug="Callout"}

## Config

```yml
{
  wrapper: 'block pl-4 pr-6 py-3 rounded-md border border-gray-200 dark:border-gray-700 bg-gray-50 dark:bg-gray-800 text-gray-700 dark:text-gray-300 text-sm/6 my-5 last:mb-0 font-normal group relative prose-code:bg-white dark:prose-code:bg-gray-900',
  to: 'hover:border-[--color-light] dark:hover:border-[--color-dark] hover:text-[--color-light] dark:hover:text-[--color-dark] border-dashed hover:border-solid hover:text-gray-800 dark:hover:text-gray-200',
  icon: {
    base: 'w-4 h-4 mr-2 inline-flex items-center align-sub text-[--color-light] dark:text-[--color-dark]'
  },
  externalIcon: {
    name: 'i-heroicons-arrow-up-right-20-solid',
    base: 'w-4 h-4 absolute right-2 top-2 text-gray-400 dark:text-gray-500 group-hover:text-[--color-light] dark:group-hover:text-[--color-dark]'
  }
}
```
