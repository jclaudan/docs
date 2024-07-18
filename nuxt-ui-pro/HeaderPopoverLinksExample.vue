<script setup lang="ts">
const links = [{
  label: 'Pricing',
  to: '/pro/pricing',
  icon: 'i-heroicons-ticket',
  description: 'A simple pricing, for solo developers or teams.'
}, {
  label: 'Templates',
  to: '/pro/templates',
  icon: 'i-heroicons-computer-desktop',
  description: 'Get started with one of our official templates.'
}, {
  label: 'Getting Started',
  to: '/pro/getting-started',
  icon: 'i-heroicons-book-open',
  description: 'Learn how to use Nuxt UI Pro in your app.'
}, {
  label: 'Components',
  to: '/pro/components',
  icon: 'i-heroicons-cube',
  description: 'Discover all the components available in Nuxt UI Pro.'
}]
</script>

<template>
  <UHeaderPopoverLinks :links="links" />
</template>
