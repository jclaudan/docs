<script setup lang="ts">
const links = [{
  label: 'Getting Started',
  icon: 'i-heroicons-book-open',
  children: [{
    label: 'Introduction',
    to: '/getting-started'
  }, {
    label: 'Installation',
    to: '/pro/getting-started/installation'
  }, {
    label: 'Theming',
    to: '/pro/getting-started/theming'
  }, {
    label: 'Structure',
    to: '/pro/getting-started/structure'
  }, {
    label: 'Content',
    to: '/pro/getting-started/content'
  }]
}]
</script>

<template>
  <UNavigationAccordion :links="links" />
</template>
