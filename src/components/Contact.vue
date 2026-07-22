<script setup>
const channels = [
  { label: 'Email', value: 'yusril703@email.com', href: 'mailto:yusril703@email.com' },
  { label: 'GitHub', value: 'github.com/musyafak-a', href: 'https://github.com/musyafak-a' },
  { label: 'Instagram', value: '@yusrilki', href: 'https://instagram.com/yusrilki' },
  { label: 'LinkedIn', value: 'linkedin.com/in/yusril-musyafak', href: 'www.linkedin.com/in/yusrilmusyafak' },
]
</script>

<template>
  <section id="contact" class="section contact">
    <p class="eyebrow">// 04 — kontak</p>
    <h2>Mari terhubung</h2>
    <p class="lead">
      Terbuka untuk kolaborasi proyek, magang, atau sekadar ngobrol soal data
      dan pengembangan aplikasi. Hubungi lewat salah satu channel di bawah.
    </p>

    <div class="channel-grid">
      <a class="channel" v-for="(c, i) in channels" :key="c.label" :href="c.href" target="_blank" rel="noopener">
        <span class="channel-label">{{ c.label }}</span>
        <span class="channel-value">{{ c.value }}</span>
        <span class="channel-arrow" :class="i % 2 === 0 ? 'arrow-blue' : 'arrow-yellow'">↗</span>
      </a>
    </div>

    <footer class="footer">
      <span>© {{ new Date().getFullYear() }} Yusril. Dibangun dengan Vue 3 &amp; Vite.</span>
    </footer>
  </section>
</template>

<style scoped>
h2 {
  font-size: clamp(1.7rem, 3.5vw, 2.4rem);
  margin-bottom: 16px;
}

.lead {
  color: var(--color-text-dim);
  max-width: 55ch;
  margin-bottom: 48px;
}

.channel-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 12px;
}

.channel {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  background: #fff;
  border: 1px solid var(--color-card-border);
  border-radius: 12px;
  padding: 14px 16px;
  box-shadow: 0 8px 24px -16px rgba(16, 19, 26, 0.15);
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.channel:hover {
  transform: translateY(-2px);
  box-shadow: 0 12px 28px -14px rgba(7, 148, 254, 0.35);
}

.channel-label {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  color: var(--color-text-dim);
  min-width: 60px;
}

.channel-value {
  font-weight: 600;
  font-size: 0.85rem;
  flex: 1;
  text-align: left;
  overflow-wrap: break-word;
  word-break: break-word;
}

.channel-arrow {
  width: 22px;
  height: 22px;
  border-radius: 50%;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
}

.arrow-blue { background: var(--color-primary); color: #fff; }
.arrow-yellow { background: var(--color-secondary); color: #10131A; }

.footer {
  margin-top: 72px;
  padding-top: 24px;
  border-top: 1px solid var(--color-card-border);
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--color-text-dim);
}
</style>
