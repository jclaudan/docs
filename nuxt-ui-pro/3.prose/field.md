---
title: Field
description: A field, prop or parameter to display in your content.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Field.vue
---

## Usage

Use the `name`, `type`, `required` and `default` props to display a field component in your content.

::component-example
---
prose: true
extraClass: 'flex-col'
---

::field{name="name" type="string" required}
The `description` can be set as prop or in the default slot with full **markdown** support.
::

#code
```mdc
::field{name="name" type="string" required}
The `description` can be set as prop or in the default slot with full **markdown** support.
::

```
::

## Props

:component-props{slug="Field"}

## Config

```yml
{
  wrapper: 'mt-5',
  container: 'flex items-start gap-x-2.5 font-mono text-sm',
  name: 'rounded-md font-semibold text-primary',
  required: 'text-gray-500 dark:text-gray-400',
  type: 'text-right',
  label: 'flex flex-1 gap-x-2.5',
  description: 'mt-3 mb-0 text-gray-600 dark:text-gray-300 text-sm space-y-3'
}
```
