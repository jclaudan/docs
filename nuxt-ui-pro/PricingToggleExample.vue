<script setup lang="ts">
const isYearly = ref(false)
</script>

<template>
  <UPricingToggle v-model="isYearly" class="max-w-xs" />
</template>
