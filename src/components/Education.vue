<script setup>
const education = [
  {
    degree: 'Bachelor of Science in Computer Science',
    school: 'International University of Technology Twintech',
    detail: 'Minor in Web Development',
    location: 'Sana\'a, Yemen',
    year: '2026',
    gpa: '4.00',
    note: 'Presenting lectures for Web Development to second-level students',
  },
  {
    degree: 'Bachelor of Computer Science (Self Taught)',
    school: 'Open Source Society University',
    detail: 'Online — GitHub',
    location: 'Remote',
    year: 'Ongoing',
    gpa: null,
    note: 'Comprehensive self-directed CS curriculum based on OSSU path',
  },
  {
    degree: 'Advanced English Diploma',
    school: 'New Horizons Institute',
    detail: null,
    location: 'Sana\'a, Yemen',
    year: '2023',
    gpa: null,
    note: null,
  },
]
</script>

<template>
  <section id="education" class="section">
    <div class="container">
      <span class="section-label">Education</span>
      <h2 class="section-title">Academic Background</h2>

      <div class="edu-grid">
        <div
          v-for="(edu, i) in education"
          :key="i"
          :class="['edu-card', 'fade-in']"
          :style="{ animationDelay: `${i * 0.1}s` }"
        >
          <div class="edu-top">
            <div class="edu-year">{{ edu.year }}</div>
            <div v-if="edu.gpa" class="edu-gpa">
              <span class="gpa-label">GPA</span>
              <span class="gpa-value">{{ edu.gpa }}</span>
            </div>
          </div>
          <h3 class="edu-degree">{{ edu.degree }}</h3>
          <span class="edu-school">{{ edu.school }}</span>
          <span v-if="edu.detail" class="edu-detail">{{ edu.detail }}</span>
          <div class="edu-meta">
            <span class="edu-location">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
              {{ edu.location }}
            </span>
          </div>
          <p v-if="edu.note" class="edu-note">{{ edu.note }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.edu-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.edu-card {
  padding: 28px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  transition: border-color 0.2s, box-shadow 0.2s;
  display: flex;
  flex-direction: column;
}

.edu-card:hover {
  border-color: var(--accent-border);
  box-shadow: 0 0 20px var(--accent-glow);
}

.edu-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}

.edu-year {
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--text-secondary);
  padding: 3px 10px;
  background: var(--accent-bg);
  border: 1px solid var(--accent-border);
  border-radius: 6px;
}

.edu-gpa {
  display: flex;
  align-items: center;
  gap: 6px;
}

.gpa-label {
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--text-secondary);
  text-transform: uppercase;
}

.gpa-value {
  font-family: var(--font-mono);
  font-size: 16px;
  font-weight: 700;
  color: var(--accent);
}

.edu-degree {
  font-family: var(--font-mono);
  font-size: 16px;
  font-weight: 600;
  color: var(--text-heading);
  margin-bottom: 8px;
  line-height: 1.4;
}

.edu-school {
  font-size: 14px;
  color: var(--accent);
  font-weight: 500;
  margin-bottom: 4px;
}

.edu-detail {
  font-size: 13px;
  color: var(--text-secondary);
  margin-bottom: 12px;
}

.edu-meta {
  margin-top: auto;
  padding-top: 16px;
  border-top: 1px solid var(--border-color);
}

.edu-location {
  display: flex;
  align-items: center;
  gap: 6px;
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
}

.edu-note {
  margin-top: 12px;
  font-size: 13px;
  color: var(--text-secondary);
  line-height: 1.6;
  padding: 10px 14px;
  background: var(--accent-bg);
  border-radius: 8px;
  border-left: 2px solid var(--accent);
}

@media (max-width: 1024px) {
  .edu-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .edu-grid {
    grid-template-columns: 1fr;
  }
}
</style>
