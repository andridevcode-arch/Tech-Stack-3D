# Rencana Perubahan Data Hewan (Pokemon) Menjadi Data Tech Stack / Tools

Rencana ini menjelaskan langkah-langkah untuk mengganti seluruh 20 item carousel 3D (sebelumnya data Pokémon seperti Bulbasaur, Charmander, dst.) dengan 20 item teknologi/tools yang diberikan oleh pengguna.

---

## 1. Ringkasan Kebutuhan
Mengganti seluruh konten daftar item pada elemen `<ul class="cards-container cards">` di file `index.html` dari data Pokémon menjadi data 20 Tech Stack/Tools dengan:
- Atribut `data-name` disesuaikan dengan nama teknologi.
- Thumbnail gambar (`<label for="item-X"><img src="...">`) menggunakan Simple Icons URL.
- Gambar utama preview (`<img src="..." />`) menggunakan Simple Icons URL.
- Judul (`<h2>`) sesuai nama teknologi.
- Deskripsi (`<p>`) sesuai penjelasan teknologi yang disediakan.

---

## 2. Analisis Kondisi Saat Ini
- Di [index.html](file:///Users/andri.dev.code/Coding/Html/andri-creative-live/3d/index.html#L178-L506), terdapat 20 elemen `<li>` (indeks `--i: 0` sampai `--i: 19`, dengan radio button id `item-1` sampai `item-20`).
- Masing-masing `<li>` saat ini berisi:
  ```html
  <li style="--i: 0" data-name="Bulbasaur">
    <input type="radio" id="item-1" name="gallery-item" checked />
    <label for="item-1">
      <img src="..." />
    </label>
    <img src="..." />
    <h2>Bulbasaur</h2>
    <p>Bulbasaur is a grass/poison type Pokémon...</p>
  </li>
  ```
- Struktur CSS di [style.css](file:///Users/andri.dev.code/Coding/Html/andri-creative-live/3d/style.css) mengandalkan selector `#item-1` sampai `#item-20` dan `--items: 20;`. Karena jumlah item yang diberikan pengguna tepat 20 item, struktur radio button (`#item-1` s.d `#item-20`), loop index CSS, dan transisi 3D carousel tidak perlu diubah, hanya konten HTML-nya saja.

---

## 3. Rincian Pemetaan Data Baru (20 Item)

| No | ID Radio | Nama (`data-name` & `<h2>`) | Image URL (Thumb & Main Preview) | Deskripsi (`<p>`) |
|:---|:---|:---|:---|:---|
| 1 | `item-1` | React.js | `https://cdn.simpleicons.org/react` | Library JavaScript untuk membangun antarmuka pengguna berbasis komponen. |
| 2 | `item-2` | Next.js | `https://cdn.simpleicons.org/nextdotjs` | Framework React untuk membangun aplikasi web dengan SSR, SSG, dan routing. |
| 3 | `item-3` | Vue.js | `https://cdn.simpleicons.org/vuedotjs` | Framework JavaScript untuk membangun antarmuka web yang reaktif. |
| 4 | `item-4` | Angular | `https://cdn.simpleicons.org/angular` | Framework TypeScript untuk membangun aplikasi web berskala besar. |
| 5 | `item-5` | Laravel | `https://cdn.simpleicons.org/laravel` | Framework PHP untuk membangun aplikasi backend dan web. |
| 6 | `item-6` | Express.js | `https://cdn.simpleicons.org/express` | Framework Node.js minimalis untuk membangun REST API dan server. |
| 7 | `item-7` | NestJS | `https://cdn.simpleicons.org/nestjs` | Framework Node.js berbasis TypeScript dengan arsitektur modular. |
| 8 | `item-8` | Django | `https://cdn.simpleicons.org/django` | Framework Python untuk membangun aplikasi web backend. |
| 9 | `item-9` | FastAPI | `https://cdn.simpleicons.org/fastapi` | Framework Python untuk membangun API berkinerja tinggi. |
| 10 | `item-10` | Gin | `https://cdn.simpleicons.org/gin` | Framework Go minimalis untuk membangun HTTP API. |
| 11 | `item-11` | Fiber | `https://cdn.simpleicons.org/go` | Framework Go yang terinspirasi dari Express.js untuk membangun API. |
| 12 | `item-12` | PostgreSQL | `https://cdn.simpleicons.org/postgresql` | Database relasional open-source yang mendukung SQL dan transaksi. |
| 13 | `item-13` | MongoDB | `https://cdn.simpleicons.org/mongodb` | Database NoSQL berbasis dokumen JSON-like. |
| 14 | `item-14` | Redis | `https://cdn.simpleicons.org/redis` | Penyimpanan data in-memory untuk caching dan pengelolaan data cepat. |
| 15 | `item-15` | Git | `https://cdn.simpleicons.org/git` | Sistem version control untuk melacak perubahan kode. |
| 16 | `item-16` | GitHub | `https://cdn.simpleicons.org/github` | Platform hosting repository dan kolaborasi pengembangan software. |
| 17 | `item-17` | Docker | `https://cdn.simpleicons.org/docker` | Platform containerization untuk menjalankan aplikasi dalam lingkungan terisolasi. |
| 18 | `item-18` | Kubernetes | `https://cdn.simpleicons.org/kubernetes` | Sistem orkestrasi container untuk deployment dan scaling aplikasi. |
| 19 | `item-19` | Nginx | `https://cdn.simpleicons.org/nginx` | Web server dan reverse proxy untuk mengelola trafik aplikasi. |
| 20 | `item-20` | GitHub Actions | `https://cdn.simpleicons.org/githubactions` | Platform otomatisasi workflow CI/CD untuk testing dan deployment. |

---

## 4. Rencana Perubahan Berkas
- **File target**: [index.html](file:///Users/andri.dev.code/Coding/Html/andri-creative-live/3d/index.html)
  - Mengubah baris 179 - 505 (seluruh anak dari `ul.cards-container.cards`).
  - Memastikan atribut `style="--i: X"`, `id="item-X"`, `name="gallery-item"`, dan status `checked` pada item 1 tetap terjaga.
  - Mengganti thumbnail icon dan main image dengan URL ikon SVG dari CDN Simple Icons.
  - Memperbarui title tag di `<title>` bila perlu atau membiarkan sesuai format yang rapi.

- **File styling (opsional bila diperlukan penyesuaian visual ikon SVG)**: [style.css](file:///Users/andri.dev.code/Coding/Html/andri-creative-live/3d/style.css)
  - Gambar Simple Icons berformat SVG transparan mono/warna bawaan. Jika diperlukan filter atau background agar kontras di latar belakang hitam, dicek setelah implementasi. Berdasarkan CSS saat ini, ada `filter: drop-shadow(0px 0px 5px rgba(255 255 255 / 0.25))` yang akan membuat ikon terlihat jelas di atas background gelap.

---

## 5. Langkah Verifikasi
1. Periksa berkas `index.html` untuk memastikan seluruh 20 item telah terpasang dengan nomor `--i` dari 0 hingga 19.
2. Pastikan tidak ada tag HTML yang rusak atau tidak tertutup.
3. Pastikan radio input `item-1` sampai `item-20` berfungsi dan terhubung dengan `label for="item-X"`.
4. Lakukan inspeksi rendering browser untuk memastikan gambar SVG Simple Icons termuat dengan baik di layar.
