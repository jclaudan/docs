---
title: LandingLogos
description: A list of logos or images to put on your landing pages.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingLogos.vue
---

## Usage

Use the `title` prop and pass a list of icons or images in the default slot.

::component-card
---
componentClass: 'w-full'
extraClass: '!p-8'
props:
  title: Trusted by the best front-end teams
  align: center
code: |
  <UIcon name="i-simple-icons-github" class="w-10 h-10 flex-shrink-0" />
  <UIcon name="i-simple-icons-discord" class="w-10 h-10 flex-shrink-0" />
  <UIcon name="i-simple-icons-x" class="w-10 h-10 flex-shrink-0" />
  <UIcon name="i-simple-icons-instagram" class="w-10 h-10 flex-shrink-0" />
  <UIcon name="i-simple-icons-linkedin" class="w-10 h-10 flex-shrink-0" />
  <UIcon name="i-simple-icons-facebook" class="w-10 h-10 flex-shrink-0" />
---

#default
:u-icon{name="i-simple-icons-github" class="w-10 h-10 flex-shrink-0"}
:u-icon{name="i-simple-icons-discord" class="w-10 h-10 flex-shrink-0"}
:u-icon{name="i-simple-icons-x" class="w-10 h-10 flex-shrink-0"}
:u-icon{name="i-simple-icons-instagram" class="w-10 h-10 flex-shrink-0"}
:u-icon{name="i-simple-icons-linkedin" class="w-10 h-10 flex-shrink-0"}
:u-icon{name="i-simple-icons-facebook" class="w-10 h-10 flex-shrink-0"}
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'text-center',
  title: 'text-lg font-semibold leading-8 text-gray-900 dark:text-white',
  images: 'mx-auto mt-10 flex flex-wrap items-center justify-between gap-8'
}
```
