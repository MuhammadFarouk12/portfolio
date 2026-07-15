<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  theme: String
})

const emit = defineEmits(['toggle-theme'])

const scrolled = ref(false)
const mobileOpen = ref(false)

const navLinks = [
  { label: 'About', href: '#about' },
  { label: 'Skills', href: '#skills' },
  { label: 'Experience', href: '#experience' },
  { label: 'Projects', href: '#projects' },
  { label: 'Contact', href: '#contact' },
]

function handleScroll() {
  scrolled.value = window.scrollY > 20
}

function closeMobile() {
  mobileOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav :class="['navbar', { scrolled }]">
    <div class="nav-inner container">
      <a href="#" class="nav-logo" @click="closeMobile">
        <span class="logo-bracket">&lt;</span>
        <span class="logo-text">MF</span>
        <span class="logo-bracket">/&gt;</span>
      </a>

      <div class="nav-links" :class="{ open: mobileOpen }">
        <a
          v-for="link in navLinks"
          :key="link.href"
          :href="link.href"
          class="nav-link"
          @click="closeMobile"
        >
          {{ link.label }}
        </a>
        <a
          href="https://github.com/MuhammadFarouk12"
          target="_blank"
          rel="noopener"
          class="nav-link github-link"
          @click="closeMobile"
        >
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor">
            <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
          </svg>
          GitHub
        </a>
        <button
          class="theme-toggle"
          @click="emit('toggle-theme')"
          :aria-label="`Switch to ${theme === 'dark' ? 'light' : 'dark'} theme`"
        >
          <svg v-if="theme === 'dark'" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <circle cx="12" cy="12" r="5"/>
            <line x1="12" y1="1" x2="12" y2="3"/>
            <line x1="12" y1="21" x2="12" y2="23"/>
            <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/>
            <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
            <line x1="1" y1="12" x2="3" y2="12"/>
            <line x1="21" y1="12" x2="23" y2="12"/>
            <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/>
            <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
          </svg>
          <svg v-else width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
          </svg>
        </button>
      </div>

      <button
        class="mobile-toggle"
        @click="mobileOpen = !mobileOpen"
        :aria-label="mobileOpen ? 'Close menu' : 'Open menu'"
      >
        <span :class="['bar', { open: mobileOpen }]"></span>
        <span :class="['bar', { open: mobileOpen }]"></span>
        <span :class="['bar', { open: mobileOpen }]"></span>
      </button>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  height: var(--nav-height);
  background: var(--bg-nav);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid transparent;
  transition: border-color 0.3s, background 0.3s;
}

.navbar.scrolled {
  border-bottom-color: var(--border-color);
}

.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100%;
}

.nav-logo {
  font-family: var(--font-mono);
  font-size: 18px;
  font-weight: 700;
  color: var(--text-heading);
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 2px;
}

.logo-bracket {
  color: var(--accent);
  font-weight: 400;
}

.logo-text {
  color: var(--text-heading);
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 4px;
}

.nav-link {
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--text-secondary);
  padding: 6px 14px;
  border-radius: 6px;
  text-decoration: none;
  transition: color 0.2s, background 0.2s;
}

.nav-link:hover {
  color: var(--accent);
  background: var(--accent-bg);
}

.github-link {
  display: flex;
  align-items: center;
  gap: 6px;
  margin-left: 8px;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 6px 14px;
}

.github-link:hover {
  border-color: var(--accent-border);
}

.theme-toggle {
  background: none;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 7px 10px;
  cursor: pointer;
  color: var(--text-secondary);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 8px;
  transition: color 0.2s, border-color 0.2s;
}

.theme-toggle:hover {
  color: var(--accent);
  border-color: var(--accent-border);
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.bar {
  width: 22px;
  height: 2px;
  background: var(--text-secondary);
  border-radius: 2px;
  transition: transform 0.3s, opacity 0.3s;
}

.bar.open:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}
.bar.open:nth-child(2) {
  opacity: 0;
}
.bar.open:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

@media (max-width: 768px) {
  .mobile-toggle {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: var(--nav-height);
    left: 0;
    right: 0;
    background: var(--bg-nav);
    backdrop-filter: blur(12px);
    flex-direction: column;
    padding: 16px 24px;
    gap: 4px;
    border-bottom: 1px solid var(--border-color);
    transform: translateY(-100%);
    opacity: 0;
    pointer-events: none;
    transition: transform 0.3s, opacity 0.3s;
  }

  .nav-links.open {
    transform: translateY(0);
    opacity: 1;
    pointer-events: auto;
  }

  .nav-link {
    width: 100%;
    text-align: center;
    padding: 10px;
  }

  .github-link {
    margin-left: 0;
    justify-content: center;
  }

  .theme-toggle {
    margin-left: 0;
    align-self: center;
  }
}
</style>
