<script setup>
const skillGroups = [
  { label: 'Web & Backend', tags: ['Django', 'Laravel', 'Flask', 'PostgreSQL', 'MySQL', 'SQLite'] },
  { label: 'Mobile', tags: ['Kotlin', 'Flutter', 'ViewBinding', 'Volley'] },
  { label: 'Tools', tags: ['VS Code', 'Laragon', 'PyQt5', 'PythonAnywhere', 'ngrok', 'Git'] },
]

const experience = [
  { year: '2024 — sekarang', title: 'Mahasiswa D3 Manajemen Informatika', desc: 'PSDKU POLINEMA Kampus Kediri — fokus pada pengembangan perangkat lunak mobile maupun web.' },
  { year: '2026', title: 'PKL', desc: 'saya melaksanakan PKL selama 3 bulan di Adisatya IT Consultant sebagai mobile dev' },
]
</script>

<template>
  <section id="skills" class="section">
    <p class="eyebrow">// 02 — skill &amp; pengalaman</p>
    <h2>Yang saya kuasai</h2>

    <div class="skills-grid">
      <div class="skill-card" v-for="(group, i) in skillGroups" :key="group.label">
        <h3 :class="i % 2 === 0 ? 'label-blue' : 'label-yellow'">{{ group.label }}</h3>
        <div class="tags">
          <span class="tag" v-for="tag in group.tags" :key="tag">{{ tag }}</span>
        </div>
      </div>
    </div>

    <div class="timeline">
      <div class="timeline-item" v-for="item in experience" :key="item.title">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <span class="timeline-year">{{ item.year }}</span>
          <h3>{{ item.title }}</h3>
          <p>{{ item.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
h2 {
  font-size: clamp(1.7rem, 3.5vw, 2.4rem);
  margin-bottom: 40px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  margin-bottom: 64px;
}

.skill-card {
  background: #fff;
  border: 1px solid var(--color-card-border);
  border-radius: 18px;
  padding: 24px;
  box-shadow: 0 12px 28px -18px rgba(16, 19, 26, 0.15);
}

.skill-card h3 {
  font-size: 1rem;
  margin-bottom: 16px;
  font-family: var(--font-mono);
  font-weight: 600;
}

.label-blue { color: var(--color-primary); }
.label-yellow { color: #A6AD00; }

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag {
  font-family: var(--font-mono);
  font-size: 0.78rem;
  padding: 6px 12px;
  border-radius: 8px;
  background: var(--color-bg-soft);
  border: 1px solid var(--color-card-border);
  color: var(--color-text-dim);
}

.timeline {
  position: relative;
  padding-left: 28px;
  border-left: 2px solid var(--color-card-border);
}

.timeline-item { position: relative; padding-bottom: 40px; }
.timeline-item:last-child { padding-bottom: 0; }

.timeline-marker {
  position: absolute;
  left: -34px;
  top: 4px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--color-primary);
  box-shadow: 0 0 0 4px var(--color-secondary);
}

.timeline-year {
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--color-primary);
  font-weight: 500;
}

.timeline-content h3 { font-size: 1.1rem; margin: 6px 0 8px; }
.timeline-content p { color: var(--color-text-dim); max-width: 60ch; margin: 0; }
</style>
