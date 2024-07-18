---
title: FieldGroup
description: Group fields together in a list.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/FieldGroup.vue
---

## Usage

::component-example
---
prose: true
extraClass: 'flex-col'
---

::field-group
  ::field{name="validate (path?: string, opts: { silent?: boolean })" type="Promise<T>"}
  Triggers form validation. Will raise any errors unless `opts.silent` is set to true.
  ::
  ::field{name="clear (path?: string)" type="void"}
  Clears form errors associated with a specific path. If no path is provided, clears all form errors.
  ::
  ::field{name="getErrors (path?: string)" type="FormError[]"}
  Retrieves form errors associated with a specific path. If no path is provided, returns all form errors.
  ::
  ::field{name="setErrors (errors: FormError[], path?: string)" type="void"}
  Sets form errors for a given path. If no path is provided, overrides all errors.
  ::
  ::field{name="errors" type="Ref<FormError[]>"}
  A reference to the array containing validation errors. Use this to access or manipulate the error information.
  ::
::

#code
````mdc
::field-group
  ::field{name="validate (path?: string, opts: { silent?: boolean })" type="Promise<T>"}
  Triggers form validation. Will raise any errors unless `opts.silent` is set to true.
  ::
  ::field{name="clear (path?: string)" type="void"}
  Clears form errors associated with a specific path. If no path is provided, clears all form errors.
  ::
  ::field{name="getErrors (path?: string)" type="FormError[]"}
  Retrieves form errors associated with a specific path. If no path is provided, returns all form errors.
  ::
  ::field{name="setErrors (errors: FormError[], path?: string)" type="void"}
  Sets form errors for a given path. If no path is provided, overrides all errors.
  ::
  ::field{name="errors" type="Ref<FormError[]>"}
  A reference to the array containing validation errors. Use this to access or manipulate the error information.
  ::
::
````
::

## Config

```yml
{
  wrapper: 'mt-5 space-y-5 divide-y divide-gray-200 dark:divide-gray-800 [&>div]:pt-5 [&>div:first-child]:pt-0 [&>div:first-child]:mt-0'
}
```
