# Portofolio Yusril — Vue 3 + Vite

Website portofolio pribadi, dibuat dengan Vue 3 dan Vite, siap dihosting di Vercel.

## Struktur

- `src/components/Hero.vue` — Section 1: nama, profesi, perkenalan singkat + foto
- `src/components/Skills.vue` — Section 2: skill & pengalaman
- `src/components/Projects.vue` — Section 3: kilas proyek
- `src/components/Contact.vue` — Section 4: kontak
- `src/style.css` — token warna, font, dan gaya global

## Sebelum deploy — yang perlu diganti

1. **Foto profil**: ganti `public/profile.svg` dengan foto asli kamu.
   - Bisa file `.jpg` / `.png`, cukup taruh di folder `public/` lalu ubah
     `src="/profile.svg"` di `src/components/Hero.vue` menjadi nama file kamu,
     misalnya `src="/foto-saya.jpg"`.
2. **Kontak**: buka `src/components/Contact.vue`, ganti email, GitHub,
   Instagram, dan LinkedIn dengan akun asli kamu.
3. **Proyek**: buka `src/components/Projects.vue`, tambahkan link demo/repo
   asli di properti `link` tiap proyek (saat ini masih placeholder `#`).
4. Cek ulang teks di `Hero.vue` dan `Skills.vue` — sudah diisi berdasarkan
   info yang saya punya, sesuaikan lagi kalau ada yang kurang tepat.

## Menjalankan secara lokal

```bash
npm install
npm run dev
```

Buka `http://localhost:5173`.

## Build

```bash
npm run build
```

Hasil build ada di folder `dist/`.

## Deploy ke Vercel

**Cara 1 — lewat GitHub (disarankan)**
1. Push folder ini ke repository GitHub baru.
2. Buka [vercel.com](https://vercel.com) → **Add New Project** → import
   repo tadi.
3. Vercel otomatis mendeteksi Vite. Pastikan pengaturan:
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. Klik **Deploy**.

**Cara 2 — lewat Vercel CLI (tanpa GitHub)**
```bash
npm install -g vercel
vercel
```
Ikuti instruksi di terminal (login, pilih scope, konfirmasi setting).
Untuk deploy production: `vercel --prod`.

## Catatan desain

Palet warna mengikuti referensi: `#0794FE` (primary/biru), `#ECF401`
(secondary/kuning-lime), putih sebagai latar utama, dan teks hitam/putih
menyesuaikan kontras background — persis seperti pada gambar acuan. Label
section pakai gaya komentar kode (`// 01 — profil`) sebagai sentuhan
identitas developer, dan kartu proyek memakai gaya "poster" gelap dengan
glow biru/kuning, mengingatkan pada kartu portofolio di referensi.
