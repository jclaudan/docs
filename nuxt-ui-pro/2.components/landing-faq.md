---
title: LandingFAQ
description: A pre-styled Accordion to display an FAQ on your landing pages.
links:
  - label: Accordion
    icon: i-simple-icons-nuxtdotjs
    to: /components/accordion
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/landing/LandingFAQ.vue
---

## Usage

Built on top of the [Accordion](/components/accordion) component, use the `items` prop to pass a list of questions and answers.

::component-example
---
extraClass: '!py-0'
component: LandingFAQExample
componentClass: 'w-full relative z-0 !mt-0'
---
::

::callout{icon="i-heroicons-light-bulb"}
You can set the `multiple` prop to `true` to allow multiple items to be open at the same time.
::

This component can be put directly inside a [LandingSection](/pro/components/landing-section) with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
faq:
  title: Frequently Asked Questions
  description: If you can't find what you're looking for, email our support team and if you're lucky someone will get back to you.
  items:
    - label: Do you have a free trial?
      content: We have much better than a free trial, you can use Nuxt UI Pro for free in development mode. Once you are ready to deploy your application, you can purchase a license.
      defaultOpen: true
    - label: Can I use Nuxt UI Pro for Open Source projects?
      content: Yes, you can use Nuxt UI Pro for your open source projects as well as your commercial projects as long as you don't sell Nuxt UI Pro as a product and that you don't share your license key.
    - label: What does “Unlimited minor & patch updates” include?
      content: We add new components and improvements to Nuxt UI Pro as we get new ideas and feedback, you will receive these updates for the major version you purchased. :br **Your license key will work forever for the major version.** We may release a major version including more advanced components and features in the future, you will be able to upgrade to this version with a generous discount.
    - label: Do you offer technical support?
      content: Once you sign up you get access to our private GitHub repository, where you can ask questions, report bugs or feature requests and get help from other customers. If you require more specialised support or consultancy, contact us at ui-pro@nuxt.com.
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection :title="page.faq.title" :description="page.faq.description">
    <ULandingFAQ :items="page.faq.items" multiple>
      <template #item="{ item }">
        <MDC :value="item.content" class="prose prose-primary dark:prose-invert max-w-none text-gray-500 dark:text-gray-400" />
      </template>
    </ULandingFAQ>
  </ULandingSection>
</template>
```

## Props

:component-props{slug="ULandingFAQ"}

## Config

```yml
{
  wrapper: 'divide-y divide-gray-200 dark:divide-gray-800 -mt-6',
  item: {
    size: 'text-base',
    padding: 'py-6'
  },
  button: {
    base: 'text-left text-lg py-6',
    label: 'text-gray-900 dark:text-white',
    trailingIcon: {
      name: 'i-heroicons-chevron-down-20-solid',
      base: 'w-5 h-5 ms-auto transform transition-transform duration-200 flex-shrink-0 mr-1.5',
      active: '',
      inactive: '-rotate-90'
    }
  }
}
```
