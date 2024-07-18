---
title: AuthForm
description: A customizable Form to create login, register or password reset forms.
links:
  - label: Form
    icon: i-simple-icons-nuxtdotjs
    to: /components/form
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/auth/AuthForm.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/login) to see how you can build your authentication pages! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/login.vue))
::

## Usage

Built on top of the [Form](/components/form) component, the `AuthForm` component can be used in your pages or wrapped in a [Card](/components/card).

The form will construct itself based on the `fields` prop and the state will be handled internally. You can pass all the props you would pass to a [FormGroup](/components/form-group) or an [Input](/components/input) to each field.

Use the `providers` prop to add some [Buttons](/components/button) above or below the form (depending on the `align` prop) and the `title`, `description`, `icon` props to customize the form (which can be overriden with slots).

::component-card
---
componentClass: 'mx-auto w-full max-w-sm py-8'
props:
  title: Login
  description: 'Enter your credentials to access your account.'
  align: 'bottom'
  icon: i-heroicons-user-circle
  fields:
    - type: 'email'
      label: 'Email'
      placeholder: 'Enter your email'
      color: gray
    - type: 'password'
      label: 'Password'
      placeholder: 'Enter your password'
      color: gray
  providers:
    - label: 'GitHub'
      icon: 'i-simple-icons-github'
      color: gray
  loading: false
excludedProps:
  - icon
  - fields
  - providers
---
::

As it is a [Form](/components/form) underneath, you can handle the validation logic through the `schema` or `validate` props.

::component-example
---
component: AuthFormExample
componentClass: 'mx-auto'
extraClass: 'py-8'
---
::

::callout{icon="i-heroicons-light-bulb"}
You can override each [FormGroup](/components/form-group) slots by prefixing with the field name: `#password-hint`.
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'w-full max-w-sm space-y-6',
  base: '',
  container: 'gap-y-6 flex flex-col',
  title: 'text-2xl text-gray-900 dark:text-white font-bold',
  description: 'text-gray-500 dark:text-gray-400 mt-1',
  icon: {
    wrapper: 'mb-2 pointer-events-none',
    base: 'w-8 h-8 flex-shrink-0 text-gray-900 dark:text-white'
  },
  providers: 'space-y-3',
  form: 'space-y-6',
  footer: 'text-sm text-gray-500 dark:text-gray-400 mt-2',
  default: {
    submitButton: {
      label: 'Continue'
    }
  }
}
```
