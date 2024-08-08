---
title: DashboardCard
description: A pre-built Card to display stats, charts or any data you'd need in a dashboard.
links:
  - label: Card
    icon: i-simple-icons-nuxtdotjs
    to: /components/card
    target: _self
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/components/dashboard/DashboardCard.vue
---

::callout{icon="i-heroicons-rectangle-group"}
Take a look at the [Dashboard template](https://dashboard-template.nuxt.dev/) to see what you can do! ([view source](https://github.com/nuxt-ui-pro/dashboard/blob/main/app/components/home/HomeChart.client.vue#L70))
::

## Usage

Built on top of the [Card](/components/card) component, the `DashboardCard` can be used inside a [DashboardPanelContent](/pro/components/dashboard-panel-content) to display stats, charts, etc.

Use the `title`, `description`, and `icon` props to customize the card.

::component-card
---
componentClass: 'w-full leading-6'
props:
  title: Recent sales
  description: You made 265 sales this month.
  icon: i-heroicons-chart-bar
code: |

  <UProgress />
excludedProps:
  - icon
---

:u-progress
::

You can also add some [Buttons](/components/button) with the `links` prop or use the `#links` slot.

::component-card
---
componentClass: 'w-full leading-6 [&>div:first-child]:!pb-4 [&>div:last-child]:!p-0'
props:
  title: Top countries
  description: You have 12,000 users from 150 countries.
  links:
    - label: 'Learn more'
      color: 'gray'
      trailingIcon: 'i-heroicons-arrow-right-20-solid'
excludedProps:
  - links
---
::

## Slots

:component-slots

## Props

:component-props

## Config

```yml
{
  divide: '',
  header: {
    base: 'flex flex-wrap items-center justify-between gap-2',
    inner: 'flex items-start gap-4',
    padding: 'px-4 py-4 sm:px-6'
  },
  title: 'text-gray-900 dark:text-white font-semibold',
  description: 'mt-1 text-gray-500 dark:text-gray-400 text-sm',
  links: 'flex flex-wrap items-center gap-1.5',
  icon: {
    wrapper: 'inline-flex',
    base: 'w-12 h-12 flex-shrink-0 text-gray-900 dark:text-white'
  }
}
```
