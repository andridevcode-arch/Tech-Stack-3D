# Rencana Implementasi: Tambahkan Animasi Latar Belakang Garis ke index.html

## Ringkasan
Menambahkan elemen `.lines` dengan tiga `.line` dan animasi `drop` ke `index.html` sebagai latar belakang animasi, dengan CSS dikonversi dari sintaks SCSS yang diberikan ke CSS biasa yang konsisten dengan `style.css` yang sudah ada.

## Status Saat Ini
- `index.html`: berisi carousel galeri Pokemon dengan `<ul class="cards-container cards">`, tidak ada latar belakang garis animasi.
- `style.css`: CSS biasa (bukan SCSS), menata `.cards`, `body`, dan elemen terkait. Body saat ini `min-height: 100svh; display: flex; flex-direction: column; ...` tanpa `position: relative`.
- `bg.html`: berkas terpisah dengan animasi daun jatuh, tidak terkait dengan tugas ini.

## Perubahan yang Diusulkan

### 1. `index.html` — tambahkan elemen HTML `.lines`
- Masukkan `<div class="lines">` dengan tiga `<div class="line"></div>` di dalam `<body>`, sebelum atau sesudah `<ul class="cards-container cards">`.
- Elemen ini akan ditempatkan secara absolut di atas body sehingga menjadi latar belakang di balik konten carousel.

### 2. `style.css` — tambahkan CSS untuk `.lines` dan `.line`
Konversi dari sintaks SCSS yang diberikan ke CSS biasa:

```css
.lines {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100%;
  margin: auto;
  width: 90vw;
  pointer-events: none;
}

.line {
  position: absolute;
  width: 1px;
  height: 100%;
  top: 0;
  left: 50%;
  background: rgba(255, 255, 255, 0.1);
  overflow: hidden;
}

.line::after {
  content: "";
  display: block;
  position: absolute;
  height: 15vh;
  width: 100%;
  top: -50%;
  left: 0;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0) 0%, #ffffff 75%, #ffffff 100%);
  animation: drop 7s 0s infinite;
  animation-fill-mode: forwards;
  animation-timing-function: cubic-bezier(0.4, 0.26, 0, 0.97);
}

.line:nth-child(1) {
  margin-left: -25%;
}

.line:nth-child(1)::after {
  animation-delay: 2s;
}

.line:nth-child(3) {
  margin-left: 25%;
}

.line:nth-child(3)::after {
  animation-delay: 2.5s;
}

@keyframes drop {
  0% {
    top: -50%;
  }
  100% {
    top: 110%;
  }
}
```

- Tambahkan `position: relative` pada `body` agar `.lines` dapat diposisikan secara absolut relatif terhadap body.
- Tambahkan `pointer-events: none` pada `.lines` agar animasi tidak menghalangi interaksi carousel.

## Asumsi & Keputusan
- CSS ditambahkan ke `style.css` (bukan inline di `index.html`) untuk konsistensi dengan pola proyek yang sudah ada.
- Sintaks SCSS (`&`, nesting) dikonversi ke CSS biasa karena `style.css` tidak menggunakan preprocessor.
- `.lines` diletakkan di balik konten carousel dengan `pointer-events: none` sehingga tidak mengganggu klik radio/button pada kartu Pokemon.

## Verifikasi
- Buka `index.html` di browser, pastikan tiga garis vertikal muncul dan bergerak ke bawah secara berulang dengan jeda animasi yang berbeda.
- Pastikan carousel Pokemon masih dapat diklik/diinteraksikan (tidak terhalang oleh `.lines`).