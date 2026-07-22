<script setup>
const projects = [
  {
    name: 'Arena Gym',
    role: 'Aplikasi Android + Backend',
    desc: 'Aplikasi mobile keanggotaan gym (Kotlin, ViewBinding, Volley) dengan backend Laravel 12, termasuk halaman kasir bertema dark-red.',
    tags: ['Kotlin', 'Laravel 12', 'Volley'],
    accent: 'blue',
  },
  {
    name: 'SDMS — MIN 4 Jombang',
    role: 'Sistem Manajemen Sekolah',
    desc: 'Sistem manajemen sekolah berbasis Django + PostgreSQL, dengan halaman profil sekolah publik dan pendaftaran (SPMB) bergaya glassmorphism.',
    tags: ['Django', 'PostgreSQL', 'Glassmorphism'],
    accent: 'yellow',
  },
  {
    name: 'Data Science Suite',
    role: '4 Web App Analitik',
    desc: 'Kumpulan aplikasi Flask untuk clustering K-Means, klasifikasi KNN, forecasting regresi, dan association rules Apriori dari dataset BPS.',
    tags: ['Flask', 'scikit-learn', 'PythonAnywhere'],
    accent: 'blue',
  },
  {
    name: 'Sistem Peminjaman Buku',
    role: 'Aplikasi Desktop',
    desc: 'Aplikasi desktop manajemen peminjaman perpustakaan dengan PyQt5 dan SQLite, dilengkapi akses berbasis peran (admin/pengunjung).',
    tags: ['PyQt5', 'SQLite'],
    accent: 'yellow',
  },
]
</script>

<template>
  <section id="projects" class="section">
    <p class="eyebrow">// 03 — kilas proyek</p>
    <h2>Beberapa hal yang sudah saya bangun</h2>

    <div class="project-grid">
      <article class="project-card" :class="'accent-' + p.accent" v-for="p in projects" :key="p.name">
        <span class="role">{{ p.role }}</span>
        <h3>{{ p.name }}</h3>
        <p class="desc">{{ p.desc }}</p>
        <div class="tags">
          <span class="tag" v-for="t in p.tags" :key="t">{{ t }}</span>
        </div>
      </article>
    </div>

    <p class="note">
      * Tautan demo/repo bisa ditambahkan di <code>src/components/Projects.vue</code> begitu sudah siap dipublikasikan.
    </p>
  </section>
</template>

<style scoped>
h2 {
  font-size: clamp(1.7rem, 3.5vw, 2.4rem);
  margin-bottom: 40px;
  max-width: 20ch;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

@media (max-width: 768px) {
  .project-grid {
    grid-template-columns: 1fr;
  }
}

.project-card {
  position: relative;
  background: #10131A;
  border-radius: 20px;
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  color: #fff;
  overflow: hidden;
  transition: transform 0.15s ease;
}

.project-card::before {
  content: '';
  position: absolute;
  width: 180px;
  height: 180px;
  border-radius: 50%;
  filter: blur(50px);
  top: -60px;
  right: -60px;
  opacity: 0.45;
}

.accent-blue::before { background: var(--color-primary); }
.accent-yellow::before { background: var(--color-secondary); }

.project-card:hover { transform: translateY(-4px); }

.role {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: rgba(255, 255, 255, 0.6);
}

.project-card h3 {
  font-size: 1.3rem;
  color: #fff;
  margin: 0;
}

.desc {
  color: rgba(255, 255, 255, 0.72);
  font-size: 0.92rem;
  margin: 0;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: auto;
}

.tag {
  font-family: var(--font-mono);
  font-size: 0.72rem;
  padding: 5px 10px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.1);
  color: rgba(255, 255, 255, 0.85);
}

.note {
  margin-top: 28px;
  font-size: 0.82rem;
  color: var(--color-text-dim);
}

.note code {
  font-family: var(--font-mono);
  background: var(--color-bg-soft);
  padding: 2px 6px;
  border-radius: 4px;
}
</style>
