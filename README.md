# Dimas Aspal — Website (Static)

Landing page jasa pengaspalan Dimas Aspal. Situs statis murni (HTML + CSS + JS, tanpa build step), siap di-deploy ke Vercel.

## Struktur
```
dimas-aspal/
├── index.html          # halaman utama (multi-section: Layanan, Proses, Galeri, dll)
├── vercel.json         # konfigurasi Vercel + cache gambar
└── img/
    ├── logo.png        # logo untuk header (latar terang)
    ├── logo-light.png  # logo versi terang untuk footer (latar gelap)
    ├── hero.jpg        # foto kartu "Pekerjaan Terbaru" di beranda
    ├── team.jpg        # foto tim di halaman "Mengapa Kami"
    └── g1.jpg .. g7.jpg# 7 foto galeri proyek (g1 = foto besar/utama)
```

## SEBELUM DEPLOY — ganti nomor WhatsApp
Buka `index.html`, cari baris:
```js
const WA_NUMBER = "62812XXXXXXXX";
```
Ganti dengan nomor WhatsApp asli, format internasional tanpa tanda "+".
Contoh: nomor 0812-3456-7890 → tulis `"6281234567890"`.

Ganti juga teks nomor/telepon/email yang masih "XXXX" di bagian top bar dan footer (cari "XXXX").

## Cara Deploy ke Vercel

### Opsi A — Tanpa coding (paling mudah, drag & drop)
1. Buat akun di https://vercel.com (bisa login pakai GitHub/Google).
2. Klik **Add New… → Project**.
3. Pilih **Deploy** lalu seret seluruh **isi folder ini** (file index.html, vercel.json, dan folder img) ke area upload. Atau zip folder ini lalu upload.
4. Klik **Deploy**. Selesai — situs langsung online dengan domain gratis `*.vercel.app`.

### Opsi B — Lewat Vercel CLI
```bash
npm i -g vercel      # sekali saja
cd dimas-aspal       # masuk ke folder proyek ini
vercel               # deploy preview
vercel --prod        # deploy ke produksi
```

### Opsi C — Lewat GitHub (otomatis update tiap push)
1. Upload folder ini ke sebuah repository GitHub.
2. Di Vercel: **Add New… → Project → Import** repo tersebut.
3. Framework Preset: **Other** (situs statis, tanpa build command).
4. Deploy. Setiap `git push` akan otomatis memperbarui situs.

## Pakai domain sendiri
Setelah deploy: buka project di Vercel → **Settings → Domains → Add**, lalu arahkan domain Anda sesuai instruksi (A record / CNAME) dari Vercel.

## Mengganti foto galeri
Ganti file `img/g1.jpg` … `img/g7.jpg` (pakai nama yang sama) atau edit caption di `index.html` (cari teks dalam `<div class="cap">`). `g1.jpg` adalah foto besar/utama di galeri.
