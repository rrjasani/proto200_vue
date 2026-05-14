<script setup lang="ts">
import { RouterLink } from 'vue-router'
import LinkButton from '../components/LinkButton.vue'
import ThemeToggle from '../components/ThemeToggle.vue'

type LinkItem = {
  label: string
  url: string
  icon: string
}

const links: LinkItem[] = [
  { label: 'Portfolio', url: 'https://example.com', icon: 'mdi-web' },
  { label: 'Dribbble', url: 'https://dribbble.com', icon: 'mdi-dribbble' },
  { label: 'LinkedIn', url: 'https://linkedin.com', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: 'mdi-email-outline' },
]
</script>

<template>
  <ThemeToggle />
  <v-main>
    <v-container class="fill-height pa-4" fluid>
      <v-row justify="center" align="center" class="w-100">
        <v-col cols="12" sm="10" md="6" lg="5" xl="4" style="max-width: 480px">
          <v-card class="pa-6 pa-sm-8 text-center" rounded="xl" elevation="4">
            <v-avatar size="96" class="mx-auto mb-4 profile-avatar">
              <span class="text-h5 font-weight-bold text-white">RJ</span>
            </v-avatar>

            <h1 class="text-h5 font-weight-bold">Rohan Jasani</h1>
            <p class="text-body-2 text-medium-emphasis mt-2">
              Designer &amp; developer crafting thoughtful digital experiences.
            </p>

            <div class="d-flex flex-column ga-3 mt-6">
              <LinkButton
                v-for="link in links"
                :key="link.label"
                :label="link.label"
                :url="link.url"
                :icon="link.icon"
              />
              <v-btn
                :to="{ name: 'about' }"
                :component="RouterLink"
                prepend-icon="mdi-account-outline"
                variant="tonal"
                size="large"
                block
              >
                About me
              </v-btn>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.profile-avatar {
  background: linear-gradient(135deg, #6366f1, #ec4899);
}
</style>
