---
title: Tabs
description: Toggle content using the Tabs component.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/Tabs.vue
---

## Usage

Wrap your content around a `Tabs` component. You can pass the `label` and `icon` props to the children to customize the tab.

::component-example
---
prose: true
---

::tabs{class="w-full !my-0 [&>div>div>div>pre]:!mb-0"}
  ::div
  ---
  label: Code
  icon: i-heroicons-code-bracket-square
  ---

    ```mdc
    ::callout
    Lorem velit voluptate ex reprehenderit ullamco et culpa.
    ::
    ```
  ::

  ::div
  ---
  label: Preview
  icon: i-heroicons-magnifying-glass-circle
  ---

    ::callout
    Lorem velit voluptate ex reprehenderit ullamco et culpa.
    ::
  ::
::

#code
````mdc
::tabs
  ::div
  ---
  label: Code
  icon: i-heroicons-code-bracket-square
  ---

  ```mdc
  ::callout
  Lorem velit voluptate ex reprehenderit ullamco et culpa.
  ::
  ```
  ::

  ::div
  ---
  label: Preview
  icon: i-heroicons-magnifying-glass-circle
  ---

  ::callout
  Lorem velit voluptate ex reprehenderit ullamco et culpa.
  ::
  ::
::
````
::

::callout{icon="i-heroicons-exclamation-triangle"}
You might need to wrap your children in a `div` if you don't want to pass-through props or when using code-blocks.
::

## Config

```yml
{
  wrapper: 'relative my-5 space-y-6',
  header: 'flex items-center relative',
  border: 'absolute bottom-0 inset-x-0 w-full h-px bg-gray-200 dark:bg-gray-800',
  tab: {
    base: 'px-4 py-2.5 font-semibold text-sm/6 flex items-center gap-1.5 border-b z-[1] focus-visible:outline-primary',
    active: 'text-primary border-primary',
    inactive: 'text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200 border-transparent hover:border-gray-300 dark:hover:border-gray-700',
    icon: {
      base: 'w-5 h-5 flex-shrink-0'
    }
  }
}
```
