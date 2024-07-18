<script setup lang="ts">
const links = [ {
  label: 'ContentSearch',
  to: '/pro/components/content-search',
  icon: 'i-heroicons-document-magnifying-glass'
}, {
  label: 'ContentSearchButton',
  to: '/pro/components/content-search-button',
  icon: 'i-heroicons-magnifying-glass',
  badge: 'New'
}, {
  label: 'ContentSurround',
  to: '/pro/components/content-surround',
  icon: 'i-heroicons-arrows-right-left'
}, {
  label: 'ContentToc',
  to: '/pro/components/content-toc',
  icon: 'i-heroicons-list-bullet'
}]
</script>

<template>
  <UNavigationLinks :links="links" />
</template>
