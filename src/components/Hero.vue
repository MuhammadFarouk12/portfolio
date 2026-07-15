<script setup>
const links = [
  { label: 'View Projects', href: '#projects', primary: true },
  { label: 'Contact Me', href: '#contact', primary: false },
]
</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="hero-content fade-in">
        <!-- <div class="status">
          <span class="status-dot"></span>
          <span class="status-text">Available for work</span>
        </div> -->

        <h1 class="hero-name">
          <span class="greeting">Hello, I'm</span>
          <span class="name">Muhammad Farouk</span>
        </h1>

        <p class="hero-role">
          <span class="terminal-prompt">$</span>
          Full Stack Developer <span class="accent">&amp;</span> AI Engineer
        </p>

        <p class="hero-desc">
          Building high-performance, secure, and scalable web applications
          with modern technologies and AI-powered solutions.
        </p>

        <div class="hero-actions">
          <a
            v-for="link in links"
            :key="link.href"
            :href="link.href"
            :class="['btn', { 'btn-primary': link.primary }]"
          >
            {{ link.label }}
          </a>
        </div>

        <div class="hero-stats">
          <div class="stat">
            <span class="stat-value">28+</span>
            <span class="stat-label">Repos</span>
          </div>
          <div class="stat">
            <span class="stat-value">100</span>
            <span class="stat-label">Followers</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: var(--nav-height);
}

.hero-content {
  max-width: 680px;
}

.status {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  background: var(--accent-bg);
  border: 1px solid var(--accent-border);
  border-radius: 20px;
  margin-bottom: 32px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: var(--accent);
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.status-text {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--accent);
  font-weight: 500;
}

.hero-name {
  font-family: var(--font-mono);
  font-size: 52px;
  font-weight: 700;
  line-height: 1.15;
  margin-bottom: 16px;
}

.greeting {
  display: block;
  font-size: 18px;
  font-weight: 400;
  color: var(--text-secondary);
  margin-bottom: 8px;
}

.name {
  color: var(--text-heading);
  background: linear-gradient(135deg, var(--text-heading), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-role {
  font-family: var(--font-mono);
  font-size: 20px;
  color: var(--text-secondary);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 8px;
}

.terminal-prompt {
  color: var(--accent);
  font-weight: 700;
}

.accent {
  color: var(--accent);
}

.hero-desc {
  font-size: 17px;
  color: var(--text-secondary);
  line-height: 1.8;
  margin-bottom: 36px;
  max-width: 520px;
}

.hero-actions {
  display: flex;
  gap: 12px;
  margin-bottom: 48px;
}

.btn {
  font-family: var(--font-mono);
  font-size: 14px;
  font-weight: 500;
  padding: 12px 28px;
  border-radius: 8px;
  text-decoration: none;
  transition: all 0.2s;
  border: 1px solid var(--border-color);
  color: var(--text-primary);
  background: var(--bg-card);
}

.btn:hover {
  border-color: var(--accent-border);
  color: var(--accent);
}

.btn-primary {
  background: var(--accent);
  color: #0a0e0a;
  border-color: var(--accent);
}

.btn-primary:hover {
  background: var(--accent-dim);
  border-color: var(--accent-dim);
  color: #0a0e0a;
}

.hero-stats {
  display: flex;
  align-items: center;
  gap: 24px;
}

.stat {
  display: flex;
  flex-direction: column;
}

.stat-value {
  font-family: var(--font-mono);
  font-size: 24px;
  font-weight: 700;
  color: var(--text-heading);
}

.stat-label {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.stat-divider {
  width: 1px;
  height: 32px;
  background: var(--border-color);
}

@media (max-width: 768px) {
  .hero {
    min-height: auto;
    padding-top: calc(var(--nav-height) + 48px);
    padding-bottom: 48px;
  }

  .hero-name {
    font-size: 34px;
  }

  .hero-role {
    font-size: 16px;
  }

  .hero-desc {
    font-size: 15px;
  }

  .hero-actions {
    flex-direction: column;
  }

  .btn {
    text-align: center;
  }

  .hero-stats {
    gap: 16px;
  }

  .stat-value {
    font-size: 20px;
  }
}
</style>
