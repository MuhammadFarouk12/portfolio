<script setup>
const experiences = [
  {
    role: 'Full Stack Developer & AI Engineer — Internship',
    company: 'Teknokeys',
    period: 'Apr 2026 — Jun 2026',
    bullets: [
      'Developed, maintained, and scaled full-stack web applications, delivering 2 production-ready platforms while optimizing frontend and backend.',
      'Architected and deployed automated AI workflows and custom Retrieval-Augmented Generation (RAG) systems.',
      'Designed and built an AI-testing environment for quality assurance.',
    ],
  },
  {
    role: 'Full Stack Developer — Freelance',
    company: 'Self-Employed',
    period: 'Dec 2023 — Present',
    bullets: [
      'Developed an end-to-end Online English Institution System, engineering the system analysis, responsive frontend, and backend for student management.',
      'Designed and implemented a Quality Management System for operational efficiency.',
    ],
  },
]
</script>

<template>
  <section id="experience" class="section">
    <div class="container">
      <span class="section-label">Experience</span>
      <h2 class="section-title">Where I've Worked</h2>

      <div class="timeline">
        <div
          v-for="(exp, i) in experiences"
          :key="i"
          :class="['timeline-item', 'fade-in']"
          :style="{ animationDelay: `${i * 0.15}s` }"
        >
          <div class="timeline-dot"></div>
          <div class="timeline-content">
            <div class="exp-header">
              <div>
                <h3 class="exp-role">{{ exp.role }}</h3>
                <span class="exp-company">{{ exp.company }}</span>
              </div>
              <span class="exp-period">{{ exp.period }}</span>
            </div>
            <ul class="exp-bullets">
              <li v-for="(bullet, j) in exp.bullets" :key="j">
                {{ bullet }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.timeline {
  position: relative;
  padding-left: 32px;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 5px;
  top: 8px;
  bottom: 8px;
  width: 1px;
  background: linear-gradient(to bottom, var(--accent), var(--border-color));
}

.timeline-item {
  position: relative;
  margin-bottom: 40px;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

.timeline-dot {
  position: absolute;
  left: -32px;
  top: 8px;
  width: 11px;
  height: 11px;
  background: var(--accent);
  border-radius: 50%;
  border: 2px solid var(--bg-primary);
  z-index: 1;
}

.timeline-content {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  padding: 28px;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.timeline-content:hover {
  border-color: var(--accent-border);
  box-shadow: 0 0 20px var(--accent-glow);
}

.exp-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 16px;
  margin-bottom: 20px;
}

.exp-role {
  font-family: var(--font-mono);
  font-size: 16px;
  font-weight: 600;
  color: var(--text-heading);
  margin-bottom: 4px;
}

.exp-company {
  font-size: 14px;
  color: var(--accent);
  font-weight: 500;
}

.exp-period {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
  white-space: nowrap;
  padding: 4px 12px;
  background: var(--accent-bg);
  border: 1px solid var(--accent-border);
  border-radius: 6px;
}

.exp-bullets {
  list-style: none;
  padding: 0;
}

.exp-bullets li {
  position: relative;
  padding-left: 20px;
  margin-bottom: 12px;
  font-size: 14px;
  color: var(--text-secondary);
  line-height: 1.7;
}

.exp-bullets li:last-child {
  margin-bottom: 0;
}

.exp-bullets li::before {
  content: '▸';
  position: absolute;
  left: 0;
  color: var(--accent);
  font-weight: 700;
}

@media (max-width: 768px) {
  .exp-header {
    flex-direction: column;
    gap: 8px;
  }

  .exp-period {
    align-self: flex-start;
  }
}
</style>
