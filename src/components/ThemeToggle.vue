<script setup lang="ts">
import { computed, onMounted, watch } from 'vue'
import { useTheme } from 'vuetify'

const theme = useTheme()

onMounted(() => {
  const stored = localStorage.getItem('theme')
  if (stored === 'light' || stored === 'dark') {
    theme.global.name.value = stored
  }
})

watch(
  () => theme.global.name.value,
  (value) => localStorage.setItem('theme', value),
)

const isDark = computed(() => theme.global.current.value.dark)

const toggle = () => {
  theme.global.name.value = isDark.value ? 'light' : 'dark'
}
</script>

<template>
  <v-btn
    class="theme-toggle"
    icon
    variant="tonal"
    :aria-label="`Switch to ${isDark ? 'light' : 'dark'} mode`"
    @click="toggle"
  >
    <v-icon :icon="isDark ? 'mdi-white-balance-sunny' : 'mdi-weather-night'" />
  </v-btn>
</template>

<style scoped>
.theme-toggle {
  position: fixed;
  top: 1rem;
  right: 1rem;
  z-index: 10;
}
</style>
