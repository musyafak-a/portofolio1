<script setup>
</script>

<template>
  <section id="home" class="hero section">
    <div class="blob blob-a"></div>
    <div class="blob blob-b"></div>

    <div class="hero-grid">
      <div class="hero-text">
        <p class="eyebrow">// 01 — profil</p>
        <h1>
          Yusril Musyafak<br />
        </h1>
        <H2>          Website & Mobile <span class="highlight">Developer</span> 
</H2>
        <p class="intro">
          Mahasiswa D3 Manajemen Informatika di PSDKU POLINEMA Kampus Kediri.
          Saya membangun aplikasi web dan mobile dari nol, mulai dari rancangan diagram pengguna, fungsi, relasi, sampai design dan implementasi logika sistemnya
        </p>
        <div class="cta-row">
          <a href="#projects" class="btn btn-primary">
            Lihat Proyek <span class="btn-arrow">→</span>
          </a>
          <a href="#contact" class="btn btn-secondary">
            Hubungi Saya <span class="btn-arrow">→</span>
          </a>
        </div>
      </div>

      <div class="hero-photo">
        <div class="photo-frame">
          <!-- Ganti file public/profile.svg dengan foto asli (bisa .jpg/.png), lalu ubah src di bawah -->
          <img src="/profile.svg" alt="Foto Yusril" />
        </div>
        <div class="chip-row">
          <span class="chip chip-blue">Web</span>
          <span class="chip chip-yellow">Mobile</span>
          <span class="chip chip-blue">Data</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding-top: 56px;
  overflow: hidden;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  z-index: -1;
  opacity: 0.55;
}

.blob-a {
  width: 340px;
  height: 340px;
  background: var(--color-secondary);
  top: -80px;
  right: 60px;
}

.blob-b {
  width: 260px;
  height: 260px;
  background: var(--color-primary);
  opacity: 0.18;
  bottom: -60px;
  left: -60px;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1.15fr 0.85fr;
  gap: 48px;
  align-items: center;
}

h1 {
  font-size: clamp(2.2rem, 5vw, 3.4rem);
  line-height: 1.08;
  margin-bottom: 20px;
}

.highlight {
  background: linear-gradient(180deg, transparent 62%, var(--color-secondary) 62%);
  padding: 0 2px;
}

.intro {
  color: var(--color-text-dim);
  max-width: 46ch;
  font-size: 1.02rem;
  margin-bottom: 32px;
}

.cta-row {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.hero-photo {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.photo-frame {
  position: relative;
  width: 100%;
  max-width: 320px;
  aspect-ratio: 3 / 4;
  border-radius: 28px;
  background: var(--color-bg-soft);
  border: 1px solid var(--color-card-border);
  overflow: hidden;
  box-shadow: 0 24px 48px -24px rgba(7, 148, 254, 0.35);
}

.photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.chip-row {
  display: flex;
  gap: 10px;
}

.chip {
  font-family: var(--font-mono);
  font-size: 0.78rem;
  font-weight: 500;
  padding: 8px 16px;
  border-radius: 999px;
}

.chip-blue { background: var(--color-primary); color: #fff; }
.chip-yellow { background: var(--color-secondary); color: #10131A; }

@media (max-width: 860px) {
  .hero-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .intro { margin-left: auto; margin-right: auto; }
  .cta-row { justify-content: center; }
  .chip-row { justify-content: center; }
}
</style>
