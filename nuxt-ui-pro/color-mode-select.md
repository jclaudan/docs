---
title: ColorModeSelect
description: A Select to switch between color mode.
links:
  - label: SelectMenu
    icon: i-simple-icons-nuxtdotjs
    to: /components/select-menu
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/color-mode/ColorModeSelect.vue
---

## Usage

You can pass any prop of the [Select](/components/select) component to override the style or size, they will be forwarded.

::component-card
---
ignoreVModel: true
props:
  class: w-28
---
::

::callout{icon="i-heroicons-light-bulb"}
A `class` prop has been added to avoid layout shift here.
::
