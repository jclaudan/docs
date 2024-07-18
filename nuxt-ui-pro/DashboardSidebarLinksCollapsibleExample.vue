<script setup lang="ts">
const links = [{
  label: 'Settings',
  icon: 'i-heroicons-cog-8-tooth',
  collapsible: false,
  children: [{
    label: 'General'
  }, {
    label: 'Members'
  }, {
    label: 'Notifications'
  }]
}]
</script>

<template>
  <UDashboardSidebarLinks :links="links" />
</template>
