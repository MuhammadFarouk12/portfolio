<script setup>
import { ref, onMounted } from 'vue'
import MatrixRain from './components/MatrixRain.vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Experience from './components/Experience.vue'
import Projects from './components/Projects.vue'
import Education from './components/Education.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const theme = ref('dark')

function toggleTheme() {
  theme.value = theme.value === 'dark' ? 'light' : 'dark'
  document.documentElement.setAttribute('data-theme', theme.value)
}

onMounted(() => {
  // Check system preference
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches
  theme.value = prefersDark ? 'dark' : 'light'
  document.documentElement.setAttribute('data-theme', theme.value)
})
</script>

<template>
  <MatrixRain />
  <NavBar :theme="theme" @toggle-theme="toggleTheme" />
  <main>
    <Hero />
    <About />
    <Skills />
    <Experience />
    <Projects />
    <Education />
    <Contact />
  </main>
  <Footer />
</template>

<style scoped>
main {
  position: relative;
  z-index: 1;
}
</style>
