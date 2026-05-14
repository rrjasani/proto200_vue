<script setup lang="ts">
import ThemeToggle from '../components/ThemeToggle.vue'

type LinkItem = {
  label: string
  href: string
  icon: string
}

const links: LinkItem[] = [
  { label: 'Portfolio', href: 'https://example.com', icon: '🌐' },
  { label: 'Dribbble', href: 'https://dribbble.com', icon: '🏀' },
  { label: 'LinkedIn', href: 'https://linkedin.com', icon: '💼' },
  { label: 'Email', href: 'mailto:hello@example.com', icon: '✉️' },
]
</script>

<template>
  <ThemeToggle />
  <main class="page">
    <section class="card">
      <div class="avatar" aria-hidden="true">RJ</div>
      <h1 class="name">Rohan Jasani</h1>
      <p class="tagline">Designer &amp; developer crafting thoughtful digital experiences.</p>

      <nav class="links" aria-label="Profile links">
        <a
          v-for="link in links"
          :key="link.label"
          class="link"
          :href="link.href"
          target="_blank"
          rel="noopener noreferrer"
        >
          <span class="link-icon" aria-hidden="true">{{ link.icon }}</span>
          <span class="link-label">{{ link.label }}</span>
        </a>
      </nav>
    </section>
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

.links {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.link {
  position: relative;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.9rem 1.1rem;
  border-radius: 14px;
  border: 1px solid var(--border);
  background: var(--button-bg);
  color: var(--text);
  font-weight: 500;
  font-size: 0.975rem;
  overflow: hidden;
  transition:
    transform 0.2s ease,
    background-color 0.25s ease,
    color 0.25s ease,
    border-color 0.25s ease,
    box-shadow 0.25s ease;
}

.link::after {
  content: '↗';
  margin-left: auto;
  opacity: 0;
  transform: translateX(-4px);
  transition: opacity 0.25s ease, transform 0.25s ease;
}

.link:hover {
  transform: translateY(-2px);
  background: var(--button-hover-bg);
  color: var(--button-hover-text);
  border-color: var(--button-hover-bg);
  box-shadow: var(--shadow);
}

.link:hover::after {
  opacity: 1;
  transform: translateX(0);
}

.link:active {
  transform: translateY(0);
}

.link-icon {
  font-size: 1.1rem;
}

@media (min-width: 480px) {
  .card {
    padding: 3rem 2.25rem;
  }
}
</style>
