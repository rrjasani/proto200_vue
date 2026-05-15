<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <v-btn
    class="link-button"
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    :prepend-icon="icon"
    variant="tonal"
    size="large"
    block
  >
    {{ label }}
  </v-btn>
</template>

<style scoped>
.link-button {
  height: auto;
  min-height: 64px;
  padding-top: 16px;
  padding-bottom: 16px;
}

.link-button :deep(.v-btn__prepend) {
  margin-inline-end: 16px;
  margin-inline-start: 8px;
}
</style>
