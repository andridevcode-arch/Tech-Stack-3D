# Rencana: Tambah Header & Footer 3D (Revisi)

## Summary
Revisi struktur layout:
1. **Header (Atas)**: Judul "ANDRI FULLSTACK DEVELOPER" dengan efek teks 3D.
2. **Footer (Bawah)**:
   - Teks status santai profesional: *"Host sedang istirahat sejenak (makan / beli cemilan) — segera kembali live!"*
   - Tautan/URL Website: `https://andri-creative.my.id` ditempatkan di paling bawah (footer).

## Current State Analysis
- File HTML: `/Users/andri.dev.code/Coding/Html/andri-creative-live/3d/index.html`
- File CSS: `/Users/andri.dev.code/Coding/Html/andri-creative-live/3d/style.css`
- Carousel lingkaran ada di tengah body (`.cards-container.cards` memiliki posisi tetap/fleksibel di tengah).

## Proposed Changes

### 1. File `index.html`
- **Di atas carousel (`<ul class="cards-container cards">`):**
  ```html
  <header class="header-3d">
    <h1 class="text-3d">ANDRI FULLSTACK DEVELOPER</h1>
  </header>
  ```
- **Di bawah carousel:**
  ```html
  <footer class="footer-info">
    <p class="status-live">Sedang istirahat sejenak (makan / cari camilan) &bull; Segera kembali live!</p>
    <a class="website-link" href="https://andri-creative.my.id" target="_blank" rel="noopener noreferrer">
      https://andri-creative.my.id
    </a>
  </footer>
  ```

### 2. File `style.css`
- Styling header 3D di bagian atas:
  - Font tebal, letter spacing lebar, efek `text-shadow` berlapis multi-depth (efek 3D timbul).
  - Posisi tetap aman (tidak menutupi kartu atau thumbnail saat berputar).
- Styling footer di bagian bawah:
  - Teks status live bernada santai tapi rapi, warna kontras lembut.
  - Link website dengan style glow neon / 3D shadow yang elegan dan responsif di mobile.
  - `z-index: 100` dan `pointer-events: auto` agar link bisa diklik dengan nyaman.

## Assumptions & Decisions
- Status istirahat diformulasikan: *"Sedang istirahat sejenak (makan / cari camilan) • Segera kembali live!"* agar sesuai konteks live stream (bukan tidur/off coding lama).
- URL ditempatkan di bagian footer paling bawah seperti instruksi.
- Teks judul tetap memiliki efek 3D tebal.

## Verification Steps
1. Periksa tampilan judul 3D di bagian atas layar mobile/desktop.
2. Pastikan carousel kartu di tengah tetap berputar lancar tanpa tertabrak teks.
3. Pastikan teks status live dan link website tampil rapi di area bawah.
4. Uji klik link website menuju `https://andri-creative.my.id`.
