<script setup>
const contactMethods = [
  {
    label: 'Email',
    value: 'Muhammad12fk@gmail.com',
    href: 'mailto:Muhammad12fk@gmail.com',
    icon: 'mail',
  },
  {
    label: 'Phone',
    value: '+967 783 004 006',
    href: 'tel:+967783004006',
    icon: 'phone',
  },
  {
    label: 'GitHub',
    value: 'MuhammadFarouk12',
    href: 'https://github.com/MuhammadFarouk12',
    icon: 'github',
  },
  {
    label: 'Telegram',
    value: '@superuserdoer',
    href: 'https://t.me/superuserdoer',
    icon: 'telegram',
  },
  {
    label: 'Location',
    value: 'Amanat Al Asimah, Yemen',
    href: null,
    icon: 'map',
  },
]
</script>

<template>
  <section id="contact" class="section">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info fade-in">
          <span class="section-label">Contact</span>
          <h2 class="section-title">Get In Touch</h2>
          <p class="contact-text">
            I'm always open to discussing new projects, creative ideas, or opportunities
            to be part of your vision. Feel free to reach out through any of the channels below.
          </p>

          <div class="contact-methods">
            <a
              v-for="method in contactMethods"
              :key="method.label"
              :href="method.href || '#'"
              :target="method.href?.startsWith('http') ? '_blank' : undefined"
              :rel="method.href?.startsWith('http') ? 'noopener' : undefined"
              :class="['contact-method', { 'no-link': !method.href }]"
            >
              <div class="method-icon">
                <!-- Mail -->
                <svg v-if="method.icon === 'mail'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                  <polyline points="22,6 12,13 2,6"/>
                </svg>
                <!-- Phone -->
                <svg v-else-if="method.icon === 'phone'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                </svg>
                <!-- GitHub -->
                <svg v-else-if="method.icon === 'github'" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
                </svg>
                <!-- Telegram -->
                <svg v-else-if="method.icon === 'telegram'" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.479.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
                </svg>
                <!-- Map -->
                <svg v-else-if="method.icon === 'map'" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                  <circle cx="12" cy="10" r="3"/>
                </svg>
              </div>
              <div class="method-info">
                <span class="method-label">{{ method.label }}</span>
                <span class="method-value">{{ method.value }}</span>
              </div>
            </a>
          </div>
        </div>

        <div class="contact-terminal fade-in delay-2">
          <div class="terminal-header">
            <div class="terminal-dots">
              <span class="dot red"></span>
              <span class="dot yellow"></span>
              <span class="dot green"></span>
            </div>
            <span class="terminal-title">contact.sh</span>
          </div>
          <div class="terminal-body">
            <div class="terminal-line">
              <span class="prompt">$</span>
              <span class="cmd">echo</span>
              <span class="string">"Let's build something amazing together"</span>
            </div>
            <div class="terminal-line output">
              Let's build something amazing together
            </div>
            <br />
            <div class="terminal-line">
              <span class="prompt">$</span>
              <span class="cmd">cat</span>
              <span class="string">availability.txt</span>
            </div>
            <div class="terminal-line output">
              <svg class="check-icon" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Open for freelance work
            </div>
            <div class="terminal-line output">
              <svg class="check-icon" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Open for collaboration
            </div>
            <div class="terminal-line output">
              <svg class="check-icon" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Open to full-time opportunities
            </div>
            <br />
            <div class="terminal-line">
              <span class="prompt">$</span>
              <span class="cursor">▊</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  align-items: start;
}

.contact-text {
  font-size: 16px;
  color: var(--text-secondary);
  line-height: 1.8;
  margin-bottom: 32px;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 16px 20px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 10px;
  text-decoration: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.contact-method:not(.no-link):hover {
  border-color: var(--accent-border);
  box-shadow: 0 0 16px var(--accent-glow);
}

.method-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-bg);
  border-radius: 8px;
  color: var(--accent);
  flex-shrink: 0;
}

.method-info {
  display: flex;
  flex-direction: column;
}

.method-label {
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-bottom: 2px;
}

.method-value {
  font-size: 14px;
  color: var(--text-heading);
  font-weight: 500;
}

/* Terminal */
.contact-terminal {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  overflow: hidden;
}

.terminal-header {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  background: var(--bg-secondary);
  border-bottom: 1px solid var(--border-color);
}

.terminal-dots {
  display: flex;
  gap: 6px;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.dot.red { background: #ff5f57; }
.dot.yellow { background: #febc2e; }
.dot.green { background: #28c840; }

.terminal-title {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
}

.terminal-body {
  padding: 24px;
  font-family: var(--font-mono);
  font-size: 13px;
  line-height: 1.8;
}

.terminal-line {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.prompt {
  color: var(--accent);
  font-weight: 700;
}

.cmd {
  color: var(--text-heading);
}

.string {
  color: #f9a825;
}

.output {
  color: var(--text-secondary);
  padding-left: 20px;
  display: flex;
  align-items: center;
  gap: 6px;
}

.check-icon {
  color: var(--accent);
  flex-shrink: 0;
}

.cursor {
  color: var(--accent);
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}

@media (max-width: 768px) {
  .contact-wrapper {
    grid-template-columns: 1fr;
    gap: 32px;
  }

  .contact-terminal {
    order: -1;
  }
}
</style>
