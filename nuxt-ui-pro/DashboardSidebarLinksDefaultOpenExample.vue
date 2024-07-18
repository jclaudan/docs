<script setup lang="ts">
const route = useRoute()

const links = computed(() => [{
  label: 'Settings',
  icon: 'i-heroicons-cog-8-tooth',
  defaultOpen: route.path.startsWith('/settings'),
  children: [{
    label: 'General'
  }, {
    label: 'Members'
  }, {
    label: 'Notifications'
  }]
}])
</script>

<template>
  <UDashboardSidebarLinks :links="links" />
</template>
