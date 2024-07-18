<script setup lang="ts">
const open = ref(true)

// This is a hack to keep the slideover open
watch(open, (value) => {
  if (!value) {
    setTimeout(() => open.value = true, 1000)
  }
})
</script>

<template>
  <UDashboardSlideover v-model="open" title="Notifications" />
</template>
