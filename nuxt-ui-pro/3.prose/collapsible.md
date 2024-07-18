---
title: Collapsible
description: A toggle to display nested properties.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Collapsible.vue
---

## Usage

Most often used in conjunction with the [Field](/pro/prose/field) and [FieldGroup](/pro/prose/field-group) components, the Collapsible component allows you to toggle the display of nested properties.

::component-example
---
extraClass: 'flex-col [&>div]:!my-0'
---

::field{name="links" type="Link[]"}
  ::collapsible
    :field{name="label" type="string" required}
  ::
::

#code
```mdc
::field{name="links" type="Link[]"}
  ::collapsible
    :field{name="label" type="string" required}
  ::
::
```
::

You can change the icon specifically in your `app.config.ts` through the `ui.content.collapsible.icon` key:

```ts
export default defineAppConfig({
  ui: {
    content: {
      collapsible: {
        button: {
          icon: {
            name: 'i-ph-caret-down'
          }
        }
      }
    }
  }
})
```

Or globally through the `ui.icons.chevron` key:

```ts
export default defineAppConfig({
  ui: {
    icons: {
      chevron: 'i-ph-caret-down'
    }
  }
})
```

## Props

:component-props{slug="Collapsible"}

## Config

```yml
{
  button: {
    base: 'flex items-center gap-1 text-sm text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200',
    icon: {
      name: 'i-heroicons-chevron-down-20-solid',
      base: 'w-4 h-4 transform transition-transform duration-200',
      active: '',
      inactive: '-rotate-90'
    }
  },
  panel: 'mt-4 ml-2 py-2.5 pl-4 border-l border-gray-200 dark:border-gray-800 [&>div]:!mt-0'
}
```
