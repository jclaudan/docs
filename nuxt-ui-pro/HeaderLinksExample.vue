<script setup lang="ts">
const links = [{
  label: 'Docs',
  icon: 'i-heroicons-book-open',
  to: '/getting-started'
}, {
  label: 'Pro',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro',
  children: [{
    label: 'Pricing',
    to: '/pro/pricing',
    icon: 'i-heroicons-ticket',
    description: 'A simple pricing, for solo developers or teams.'
  }, {
    label: 'Templates',
    to: '/pro/templates',
    icon: 'i-heroicons-computer-desktop',
    description: 'Get started with one of our official templates.'
  }]
}, {
  label: 'Releases',
  icon: 'i-heroicons-rocket-launch',
  to: '/releases'
}]
</script>

<template>
  <UHeaderLinks :links="links" />
</template>
