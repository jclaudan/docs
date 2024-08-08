---
title: PricingGrid
description: A customizable grid for your PricingCard components.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/pricing/PricingGrid.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [SaaS template](https://saas-template.nuxt.dev/pricing) to see how you can build your own pricing page! ([view source](https://github.com/nuxt-ui-pro/saas/blob/main/app/pages/pricing.vue))
::

## Usage

Use some [PricingCard](/pro/components/pricing-card) to display pricing plans side by side.

::component-card
---
componentClass: 'p-8'
props:
  compact: false
code: |
  <UPricingCard title="Free" description="Get started for free in development." />
  <UPricingCard title="Solo" description="For bootstrappers and indie hackers." price="$199" scale highlight />
  <UPricingCard title="Team" description="Unlimited license for growing teams." price="$699" />
---

#default
:u-pricing-card{title="Free" description="Get started for free in development."}
:u-pricing-card{title="Solo" description="For bootstrappers and indie hackers." price="$199" scale highlight}
:u-pricing-card{title="Team" description="Unlimited license for growing teams." price="$699"}
::

This component can be put directly inside a [LandingSection](/pro/components/landing-section) with its content fetched from `@nuxt/content` easily:

```yml [content/index.yml]
pricing:
  title: Pricing
  description: Choose the plan that works for you.
  plans:
    - title: Free
      description: Get started for free in development.
    - title: Solo
      description: For bootstrappers and indie hackers.
      price: $199
      scale: true
      highlight: true
    - title: Team
      description: Unlimited license for growing teams.
      price: $699
```

::callout{icon="i-heroicons-information-circle"}
We're using `.yml` files as an example here but you can use any format supported by `@nuxt/content` like `.md` or `.json`.
::

```vue [pages/index.vue]
<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
</script>

<template>
  <ULandingSection :title="page.pricing.title" :description="page.pricing.description">
    <UPricingGrid>
      <UPricingCard v-for="(plan, index) in page.pricing.plans" :key="index" v-bind="plan" />
    </UPricingGrid>
  </ULandingSection>
</template>
```

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  wrapper: 'flex flex-col lg:grid lg:grid-cols-3 w-full justify-center items-center gap-8'
}
```
