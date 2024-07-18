<script setup lang="ts">
const light = 'https://source.unsplash.com/random/200x200?sky'
const dark = 'https://source.unsplash.com/random/200x200?stars'
</script>

<template>
  <UColorModeImage :light="light" :dark="dark" />
</template>
