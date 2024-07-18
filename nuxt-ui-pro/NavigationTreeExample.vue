<script lang="ts" setup>
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))
</script>

<template>
  <UNavigationTree :links="mapContentNavigation(navigation)" :multiple="false" default-open />
</template>
