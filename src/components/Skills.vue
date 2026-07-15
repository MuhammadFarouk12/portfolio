<script setup>
import MatrixIcon from './MatrixIcon.vue'

const categories = [
  {
    title: 'Frontend',
    icon: 'palette',
    skills: [
      'HTML5', 'CSS3', 'JavaScript (ES6+)', 'TypeScript',
      'Vue.js', 'React', 'Next.js', 'Tailwind CSS',
      'Bootstrap', 'SCSS', 'Responsive Design', 'Pinia', 'Vite',
    ],
  },
  {
    title: 'Backend',
    icon: 'gear',
    skills: [
      'Laravel', 'Node.js', 'Express.js', 'RESTful APIs',
      'JWT Auth', 'Session-Based Auth', 'Web Sockets',
      'Laravel Reverb', 'Mails & Notifications',
    ],
  },
  {
    title: 'Database',
    icon: 'database',
    skills: [
      'MySQL', 'PostgreSQL', 'MongoDB',
      'Database Normalization', 'Query Optimization',
    ],
  },
  {
    title: 'DevOps & Tools',
    icon: 'wrench',
    skills: [
      'Git & GitHub', 'Docker', 'Linux', 'Nginx',
      'CI/CD', 'Ubuntu', 'Debian', 'Cron Jobs',
    ],
  },
  {
    title: 'Security',
    icon: 'shield',
    skills: [
      'OWASP Top 10', 'SQL Injection', 'XSS', 'CSRF',
      'Hashing & Encryption', 'RBAC', 'PBAC',
    ],
  },
  {
    title: 'AI & Engineering',
    icon: 'code',
    skills: [
      'Prompt Engineering', 'RAG Systems', 'MCPs',
      'AI Agents', 'Code Review', 'Python',
      'Architecture Design', 'Technical Writing',
    ],
  },
]
</script>

<template>
  <section id="skills" class="section">
    <div class="container">
      <span class="section-label">Skills</span>
      <h2 class="section-title">Tech Stack</h2>

      <div class="skills-grid">
        <div
          v-for="(cat, i) in categories"
          :key="cat.title"
          :class="['skill-category', 'fade-in']"
          :style="{ animationDelay: `${i * 0.08}s` }"
        >
          <div class="cat-header">
            <span class="cat-icon"><MatrixIcon :name="cat.icon" :size="20" /></span>
            <h3 class="cat-title">{{ cat.title }}</h3>
          </div>
          <div class="cat-skills">
            <span
              v-for="skill in cat.skills"
              :key="skill"
              class="tag"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.skill-category {
  padding: 28px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.skill-category:hover {
  border-color: var(--accent-border);
  box-shadow: 0 0 20px var(--accent-glow);
}

.cat-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
  padding-bottom: 16px;
  border-bottom: 1px solid var(--border-color);
}

.cat-icon {
  font-size: 20px;
}

.cat-title {
  font-family: var(--font-mono);
  font-size: 15px;
  font-weight: 600;
  color: var(--text-heading);
}

.cat-skills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

@media (max-width: 1024px) {
  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
