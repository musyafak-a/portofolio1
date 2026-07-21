<script setup>
import { ref } from 'vue'
const open = ref(false)
const active = ref('home')
</script>

<template>
  <header class="nav">
    <div class="nav-inner">
      <a href="#home" class="logo">
        <span class="logo-mark">Y</span>
        yusril<span class="logo-accent"></span>
      </a>

      <nav class="links" :class="{ open }">
        <a href="#home" :class="{ active: active === 'home' }" @click="active = 'home'; open = false">Home</a>
        <a href="#skills" :class="{ active: active === 'skills' }" @click="active = 'skills'; open = false">Skill</a>
        <a href="#projects" :class="{ active: active === 'projects' }" @click="active = 'projects'; open = false">Proyek</a>
        <a href="#contact" :class="{ active: active === 'contact' }" @click="active = 'contact'; open = false">Kontak</a>
      </nav>

      <div class="nav-right">
        <a href="#contact" class="avatar" aria-label="Kontak">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none">
            <circle cx="12" cy="8" r="4" stroke="white" stroke-width="2"/>
            <path d="M4 20c0-4 3.6-6 8-6s8 2 8 6" stroke="white" stroke-width="2" stroke-linecap="round"/>
          </svg>
        </a>
        <button class="burger" @click="open = !open" :aria-expanded="open" aria-label="Buka menu">
          <span :class="{ open }"></span>
        </button>
      </div>
    </div>
  </header>
</template>

<style scoped>
.nav {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--color-card-border);
}

.nav-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 16px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.05rem;
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo-mark {
  width: 32px;
  height: 32px;
  border-radius: 10px;
  background: var(--color-primary);
  color: #fff;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-weight: 800;
}

.logo-accent { color: var(--color-text-dim); font-weight: 500; }

.links {
  display: flex;
  gap: 6px;
  font-family: var(--font-display);
  font-size: 0.9rem;
  font-weight: 600;
  background: var(--color-bg-soft);
  padding: 6px;
  border-radius: 999px;
}

.links a {
  color: var(--color-text-dim);
  padding: 8px 18px;
  border-radius: 999px;
  transition: background 0.15s ease, color 0.15s ease;
}

.links a:hover { color: var(--color-text); }

.links a.active {
  background: var(--color-secondary);
  color: #10131A;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 12px;
}

.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: var(--color-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 6px 16px -6px rgba(7, 148, 254, 0.6);
}

.burger {
  display: none;
  background: none;
  border: none;
  width: 32px;
  height: 32px;
  cursor: pointer;
  position: relative;
}

.burger span,
.burger span::before,
.burger span::after {
  content: '';
  position: absolute;
  left: 6px;
  right: 6px;
  height: 2px;
  background: var(--color-text);
  transition: transform 0.2s ease, opacity 0.2s ease;
}

.burger span { top: 15px; }
.burger span::before { top: -8px; }
.burger span::after { top: 8px; }
.burger span.open { background: transparent; }
.burger span.open::before { transform: translateY(8px) rotate(45deg); }
.burger span.open::after { transform: translateY(-8px) rotate(-45deg); }

@media (max-width: 720px) {
  .links {
    position: absolute;
    top: 100%;
    left: 16px;
    right: 16px;
    flex-direction: column;
    background: #fff;
    padding: 12px;
    gap: 6px;
    border: 1px solid var(--color-card-border);
    border-radius: 16px;
    display: none;
    box-shadow: 0 12px 24px -12px rgba(16, 19, 26, 0.2);
  }
  .links.open { display: flex; }
  .links a { text-align: center; }
  .burger { display: block; }
}
</style>
