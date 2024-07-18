---
title: CardGroup
description: Group cards together in a grid.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/CardGroup.vue
---

## Usage

::component-example
---
prose: true
---

::card-group
  ::card{title="Components" icon="i-heroicons-cube" to="https://nuxt.com/docs/api/components/client-only" target="_blank"}
  Explore Nuxt built-in components for pages, layouts, head, and more.
  ::
  ::card{title="Composables" icon="i-heroicons-arrows-right-left" to="https://nuxt.com/docs/api/composables/use-app-config" target="_blank"}
  Discover Nuxt composable functions for data-fetching, head management and more.
  ::
  ::card{title="Utils" icon="i-heroicons-scissors" to="https://nuxt.com/docs/api/utils/dollarfetch" target="_blank"}
  Learn about Nuxt utility functions for navigation, error handling and more.
  ::
  ::card{title="Commands" icon="i-heroicons-command-line" to="https://nuxt.com/docs/api/commands/add" target="_blank"}
  List of Nuxt CLI commands to init, analyze, build, and preview your application.
  ::
::

#code
```mdc
::card-group
  ::card
  ---
  title: Components
  icon: i-heroicons-cube
  to: https://nuxt.com/docs/api/components/client-only
  target: _blank
  ---
  Explore Nuxt built-in components for pages, layouts, head, and more.
  ::
  ::card
  ---
  title: Composables
  icon: i-heroicons-arrows-right-left
  to: https://nuxt.com/docs/api/composables/use-app-config
  target: _blank
  ---
  Discover Nuxt composable functions for data-fetching, head management and more.
  ::
  ::card
  ---
  title: Utils
  icon: i-heroicons-scissors
  to: https://nuxt.com/docs/api/utils/dollarfetch
  target: _blank
  ---
  Learn about Nuxt utility functions for navigation, error handling and more.
  ::
  ::card
  ---
  title: Commands
  icon: i-heroicons-command-line
  to: https://nuxt.com/docs/api/commands/add
  target: _blank
  ---
  List of Nuxt CLI commands to init, analyze, build, and preview your application.
  ::
::
```
::

## Config

```yml
{
  wrapper: 'grid sm:grid-cols-2 gap-4'
}
```
