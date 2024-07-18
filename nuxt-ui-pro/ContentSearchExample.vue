<script setup lang="ts">
import type { ParsedContent } from '@nuxt/content'

const { data: navigation } = await useAsyncData('navigation', () => fetchContentNavigation(), { default: () => [] })
const { data: files } = useLazyFetch<ParsedContent[]>('/api/search.json', { default: () => [], server: false })

const links = [{
  label: 'Docs',
  icon: 'i-heroicons-book-open',
  to: '/getting-started'
}, {
  label: 'Pro',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro'
}, {
  label: 'Pricing',
  to: '/pro/pricing',
  icon: 'i-heroicons-ticket'
}, {
  label: 'Templates',
  icon: 'i-heroicons-computer-desktop',
  to: '/pro/templates'
}, {
  label: 'Releases',
  icon: 'i-heroicons-rocket-launch',
  to: '/releases'
}]

const open = ref(true)

// This is a hack to make the search modal open by default
watch(open, (value) => {
  if (!value) {
    setTimeout(() => open.value = true, 1000)
  }
})
</script>

<template>
  <UContentSearch v-model="open" :navigation="navigation" :files="files" :links="links" :ui="{ height: 'sm:h-[400px]' }" />
</template>
