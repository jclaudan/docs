<script setup lang="ts">
const links = [{
  id: 'introduction',
  depth: 2,
  text: 'Introduction'
}, {
  id: 'configuration',
  depth: 2,
  text: 'Configuration',
  children: [{
    id: 'variables',
    depth: 3,
    text: 'Variables'
  }, {
    id: 'icons',
    depth: 3,
    text: 'Icons'
  }]
}, {
  id: 'structure',
  depth: 2,
  text: 'Structure',
  children: [{
    id: 'nuxt.config.ts',
    depth: 3,
    text: 'nuxt.config.ts'
  }, {
    id: 'app.config.ts',
    depth: 3,
    text: 'app.config.ts'
  }, {
    id: 'tailwind.config.ts',
    depth: 3,
    text: 'tailwind.config.ts'
  }, {
    id: 'app.vue',
    depth: 3,
    text: 'app.vue'
  }, {
    id: 'pages.index.vue',
    depth: 3,
    text: 'pages/index.vue'
  }]
}]
</script>

<template>
  <UContentToc :links="links" />
</template>
