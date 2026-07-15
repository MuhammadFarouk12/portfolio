<script setup>
import MatrixIcon from './MatrixIcon.vue'
// test
const highlights = [
  { icon: 'bolt', label: 'Performance', text: 'High-performance web applications' },
  { icon: 'lock', label: 'Security', text: 'OWASP Top 10 & best practices' },
  { icon: 'brain', label: 'AI Integration', text: 'RAG systems & AI workflows' },
  { icon: 'layout', label: 'Architecture', text: 'Scalable, clean system design' },
]
</script>

<template>
  <section id="about" class="section">
    <div class="container">
      <div class="about-grid">
        <div class="about-main fade-in">
          <span class="section-label">About</span>
          <h2 class="section-title">Who I Am</h2>
          <p class="about-text">
            A professional full stack web developer with experience building modern web applications.
            I specialize in creating high-performance, secure, and scalable systems using
            <span class="accent-text">Laravel</span>, <span class="accent-text">Vue</span>,
            and integrating
            <span class="accent-text">AI-powered solutions</span> into production workflows.
          </p>
          <p class="about-text">
            Currently pursuing my Bachelor's in Computer Science, while actively
            contributing to the tech community through teaching web development and writing tech-content
          </p>

          <div class="about-quick">
            <div class="quick-item">
              <span class="quick-label">Location</span>
              <span class="quick-value">Sana'a, Yemen</span>
            </div>
            <div class="quick-item">
              <span class="quick-label">Focus</span>
              <span class="quick-value">Full Stack & AI</span>
            </div>
          </div>
        </div>

        <div class="about-highlights fade-in delay-2">
          <div
            v-for="item in highlights"
            :key="item.label"
            class="highlight-card"
          >
            <span class="highlight-icon"><MatrixIcon :name="item.icon" :size="22" /></span>
            <div>
              <span class="highlight-label">{{ item.label }}</span>
              <span class="highlight-text">{{ item.text }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: start;
}

.about-text {
  font-size: 16px;
  color: var(--text-secondary);
  line-height: 1.8;
  margin-bottom: 16px;
}

.accent-text {
  color: var(--accent);
  font-weight: 500;
}

.about-quick {
  display: flex;
  gap: 32px;
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid var(--border-color);
}

.quick-item {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.quick-label {
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.quick-value {
  font-family: var(--font-mono);
  font-size: 14px;
  color: var(--text-heading);
  font-weight: 500;
}

.about-highlights {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.highlight-card {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 20px 24px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 10px;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.highlight-card:hover {
  border-color: var(--accent-border);
  box-shadow: 0 0 16px var(--accent-glow);
}

.highlight-icon {
  flex-shrink: 0;
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-bg);
  border-radius: 10px;
}

.highlight-label {
  font-family: var(--font-mono);
  font-size: 14px;
  font-weight: 600;
  color: var(--text-heading);
  display: block;
  margin-bottom: 2px;
}

.highlight-text {
  font-size: 13px;
  color: var(--text-secondary);
}

@media (max-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .about-quick {
    flex-direction: column;
    gap: 16px;
  }
}
</style>
