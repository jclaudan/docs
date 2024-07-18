<script setup lang="ts">
const colors = ref(['green', 'teal', 'cyan', 'sky', 'blue', 'indigo', 'violet'].map(color => ({ label: color, chip: color })))

const links = computed(() => [{
  label: 'Favorites',
  draggable: true,
  children: colors.value
}])
</script>

<template>
  <UDashboardSidebarLinks :links="links" @update:links="links => colors = links" />
</template>
