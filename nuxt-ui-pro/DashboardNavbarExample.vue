<template>
  <UDashboardNavbar>
    <template #left>
      <UTooltip text="Archive">
        <UButton icon="i-heroicons-archive-box" color="gray" variant="ghost" />
      </UTooltip>

      <UDivider orientation="vertical" class="mx-1.5" />

      <UTooltip text="Move to junk">
        <UButton icon="i-heroicons-archive-box-x-mark" color="gray" variant="ghost" />
      </UTooltip>
    </template>

    <template #right>
      <UTooltip text="Reply">
        <UButton icon="i-heroicons-arrow-uturn-left" color="gray" variant="ghost" />
      </UTooltip>

      <UTooltip text="Forward">
        <UButton icon="i-heroicons-arrow-uturn-right" color="gray" variant="ghost" />
      </UTooltip>
    </template>
  </UDashboardNavbar>
</template>
