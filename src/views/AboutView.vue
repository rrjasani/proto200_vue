<script setup lang="ts">
import { RouterLink } from 'vue-router'
import ThemeToggle from '../components/ThemeToggle.vue'
</script>

<template>
  <ThemeToggle />
  <main class="page">
    <article class="card">
      <div class="avatar" aria-hidden="true">RJ</div>
      <h1 class="name">About Rohan</h1>
      <p class="tagline">Designer &amp; developer crafting thoughtful digital experiences.</p>

      <section class="bio">
        <p>
          I'm a product-minded designer and developer based in the Pacific Northwest. I work at the
          intersection of design and engineering — prototyping ideas, shipping interfaces, and
          obsessing over the small details that make software feel alive.
        </p>
        <p>
          Lately I've been exploring AI-assisted tooling, design systems, and the craft of building
          fast, accessible web experiences. When I'm not at a keyboard, you'll find me on a trail or
          hunting for the next great cup of coffee.
        </p>
      </section>

      <RouterLink to="/" class="back-link">← Back to links</RouterLink>
    </article>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 1rem;
}

.card {
  width: 100%;
  max-width: 480px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 24px;
  padding: 2.5rem 1.5rem;
  text-align: center;
  box-shadow: var(--shadow);
}

.avatar {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  margin: 0 auto 1.25rem;
  background: linear-gradient(135deg, #6366f1, #ec4899);
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  font-size: 1.75rem;
  letter-spacing: 0.02em;
  border: 3px solid var(--surface);
  box-shadow: var(--shadow);
}

.name {
  font-size: 1.5rem;
  font-weight: 600;
  letter-spacing: -0.01em;
}

.tagline {
  margin-top: 0.5rem;
  color: var(--text-muted);
  font-size: 0.95rem;
}

.bio {
  margin-top: 1.75rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  text-align: left;
  color: var(--text);
  font-size: 0.975rem;
  line-height: 1.65;
}

.back-link {
  display: inline-block;
  margin-top: 2rem;
  padding: 0.6rem 1rem;
  border-radius: 999px;
  border: 1px solid var(--border);
  background: var(--button-bg);
  color: var(--text);
  font-weight: 500;
  font-size: 0.9rem;
  transition:
    transform 0.2s ease,
    background-color 0.25s ease,
    color 0.25s ease,
    border-color 0.25s ease;
}

.back-link:hover {
  transform: translateY(-2px);
  background: var(--button-hover-bg);
  color: var(--button-hover-text);
  border-color: var(--button-hover-bg);
}

@media (min-width: 480px) {
  .card {
    padding: 3rem 2.25rem;
  }
}
</style>
