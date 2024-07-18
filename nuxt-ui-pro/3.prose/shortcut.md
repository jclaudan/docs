---
title: Shortcut
description: A <kbd> in your content.
links:
  - label: Kbd
    icon: i-simple-icons-nuxtdotjs
    to: /components/kbd
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Shortcut.vue
---

## Usage

Built on top of the [Kbd](/components/kbd) component, the Shortcut component will help you display a keyboard shortcut in your content.

::component-example
:shortcut{value="K"}

#code
```mdc
:shortcut{value="K"}
```
::

You can also specify the `meta` key to automatically display either `⌘` or `Ctrl` based on the platform.

::component-example
:shortcut{value="meta"} :shortcut{value="K"}

#code
```mdc
:shortcut{value="meta"} :shortcut{value="K"}
```
::

## Props

:component-props{slug="Shortcut"}

## Config

```yml
{
  wrapper: '!my-0 align-text-top'
}
```
