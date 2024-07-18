<script setup lang="ts">
const links = [{
  id: 'home',
  label: 'Home',
  icon: 'i-heroicons-home',
  shortcuts: ['G', 'H']
}, {
  id: 'inbox',
  label: 'Inbox',
  icon: 'i-heroicons-inbox',
  shortcuts: ['G', 'I']
}, {
  id: 'users',
  label: 'Users',
  icon: 'i-heroicons-user-group',
  shortcuts: ['G', 'U']
}, {
  id: 'settings',
  label: 'Settings',
  icon: 'i-heroicons-cog-8-tooth',
  shortcuts: ['G', 'S']
}]

const groups = [{ key: 'links', label: 'Go to', commands: links }]

const open = ref(true)

// This is a hack to make the search modal open by default
watch(open, (value) => {
  if (!value) {
    setTimeout(() => open.value = true, 1000)
  }
})
</script>

<template>
  <UDashboardSearch v-model="open" :groups="groups" :ui="{ height: 'sm:h-[400px]' }" />
</template>
