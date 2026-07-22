<script setup>
const projects = [
  {
    name: 'Arena Gym',
    role: 'Aplikasi Android + Backend',
    desc: 'Aplikasi mobile keanggotaan gym (Kotlin, ViewBinding, Volley) dengan backend Laravel 12, termasuk halaman kasir bertema dark-red.',
    tags: ['Kotlin', 'Laravel 12', 'Volley'],
    accent: 'blue',
    image: '/arenafitness.png'
  },
  {
    name: 'SDMS — MIN 4 Jombang',
    role: 'Sistem Manajemen Sekolah',
    desc: 'Sistem manajemen sekolah berbasis Django + PostgreSQL, dengan halaman profil sekolah publik dan pendaftaran (SPMB) bergaya glassmorphism.',
    tags: ['Django', 'PostgreSQL', 'Glassmorphism'],
    accent: 'yellow',
    image: '/min4jombang.png'
  },
  {
    name: 'Mobile Speedtracker',
    role: 'Aplikasi Mobile',
    desc: 'Aplikasi pelacak kecepatan (speed tracker) berbasis mobile untuk memonitor kecepatan secara real-time.',
    tags: ['Mobile', 'Tracking'],
    accent: 'blue',
    image: '/speedtracker.png'
  },
  {
    name: 'Sistem Peminjaman Buku',
    role: 'Aplikasi Desktop',
    desc: 'Aplikasi desktop manajemen peminjaman perpustakaan dengan PyQt5 dan SQLite, dilengkapi akses berbasis peran (admin/pengunjung).',
    tags: ['PyQt5', 'SQLite'],
    accent: 'yellow',
    image: '/perpus.png'
  },
]
</script>

<template>
  <section id="projects" class="section">
    <p class="eyebrow">// 03 — kilas proyek</p>
    <h2>Beberapa hal yang sudah saya bangun</h2>

    <div class="project-grid">
      <article class="project-card" :class="'accent-' + p.accent" v-for="p in projects" :key="p.name">
        <div class="card-bg" :style="{ backgroundImage: 'url(' + p.image + ')' }"></div>
        <div class="card-content">
          <span class="role">{{ p.role }}</span>
          <h3>{{ p.name }}</h3>
          <p class="desc">{{ p.desc }}</p>
          <div class="tags">
            <span class="tag" v-for="t in p.tags" :key="t">{{ t }}</span>
          </div>
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
  color: #fff;
  overflow: hidden;
  transition: transform 0.15s ease;
}

.card-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  opacity: 0.12; /* Hampir tidak terlihat */
  z-index: 1;
  transition: opacity 0.3s ease;
}

.project-card:hover .card-bg {
  opacity: 0.35;
}

.card-content {
  position: relative;
  z-index: 2;
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  height: 100%;
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
