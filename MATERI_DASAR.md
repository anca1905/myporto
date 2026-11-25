# Modul Pembelajaran: HTML5 & CSS3 Dasar (Basic)

Selamat datang di materi praktek pembelajaran web dasar! Dokumen ini dirancang sebagai panduan lengkap untuk memahami konsep fundamental **HTML** (kerangka website) dan **CSS** (tata rias dan tata letak website), yang diimplementasikan langsung pada proyek website portofolio di `index.html` dan `style.css`.

---

## Bagian 1: HTML Dasar (HyperText Markup Language)

HTML adalah bahasa markup standar yang digunakan untuk membuat dan menyusun struktur halaman web.

### 1. Struktur Dokumen Standar HTML5
Setiap file HTML diawali dengan kerangka dasar berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Judul Halaman di Tab Browser</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Konten yang dilihat pengunjung ditaruh di sini -->
</body>
</html>
```

* **`<!DOCTYPE html>`**: Mendeklarasikan bahwa dokumen ini menggunakan standar HTML5 terbaru.
* **`<html lang="id">`**: Elemen pembungkus paling luar (root) dengan atribut bahasa (`id` = Indonesia).
* **`<head>`**: Bagian kepala dokumen yang memuat metadata, konfigurasi layar/viewport, tautan stylesheet, dan judul halaman.
* **`<body>`**: Bagian tubuh dokumen tempat semua elemen visual (teks, gambar, tombol, formulir) diletakkan.

---

### 2. Elemen Semantik HTML5
Tag semantik memberikan makna jelas pada browser, mesin pencari (SEO), dan pembaca layar (accessibility).

| Tag Semantik | Fungsi | Contoh di Proyek |
| :--- | :--- | :--- |
| `<header>` | Bagian kepala halaman atau pengantar | Navigasi atas dan logo |
| `<nav>` | Wadah untuk tautan navigasi | Menu menu Home, About, Skills |
| `<main>` | Konten utama dan unik dari sebuah halaman | Seluruh isi utama portofolio |
| `<section>` | Bagian mandiri atau bab dari sebuah topik | `#home`, `#about`, `#skills` |
| `<article>` | Konten independen yang dapat berdiri sendiri | Kartu proyek (`.project-card`) |
| `<footer>` | Bagian kaki dokumen (hak cipta, info kontak) | Bagian paling bawah website |

---

### 3. Elemen Teks & Tipografi
* **Heading (`<h1>` sampai `<h6>`)**: Menandakan hierarki judul, dari yang paling penting (`<h1>`) hingga sub-judul terendah (`<h6>`). *Catatan: Biasanya hanya ada 1 buah `<h1>` per halaman.*
* **Paragraf (`<p>`)**: Untuk blok teks atau paragraf.
* **Penekanan & Format**:
  * `<strong>`: Teks tebal yang bermakna penting.
  * `<em>`: Teks miring untuk penekanan (emphasis).
  * `<mark>`: Teks dengan sorotan stabilo kuning.
  * `<span>`: Wadah teks sebaris (inline) untuk diberi gaya spesifik via CSS.
  * `<br>`: Pindah ke baris baru (line break).

---

### 4. Tautan (Hyperlink) & Gambar (Image)
* **Link (`<a href="...">`)**:
  * Tautan internal halaman (Anchor Link): `<a href="#about">Tentang Saya</a>`
  * Tautan eksternal: `<a href="https://google.com" target="_blank" rel="noopener noreferrer">Buka Google</a>`
* **Gambar (`<img>` & `<figure>`)**:
  ```html
  <figure>
      <img src="gambar.jpg" alt="Deskripsi gambar jika gagal dimuat" class="foto">
      <figcaption>Keterangan gambar</figcaption>
  </figure>
  ```
  * Atribut `src`: Alamat file gambar (URL atau path lokal).
  * Atribut `alt`: Teks alternatif untuk aksesibilitas dan SEO.

---

### 5. Daftar (Lists)
* **Unordered List (`<ul>`)**: Daftar bertitik (bullet points), cocok untuk menu navigasi atau daftar keahlian.
  ```html
  <ul>
      <li>HTML5</li>
      <li>CSS3</li>
  </ul>
  ```
* **Ordered List (`<ol>`)**: Daftar bernomor berurutan (1, 2, 3), cocok untuk langkah-langkah atau tahapan proses.
  ```html
  <ol>
      <li>Pelajari HTML</li>
      <li>Pelajari CSS</li>
  </ol>
  ```

---

### 6. Tabel HTML (`<table>`)
Digunakan untuk menyajikan data tabular secara rapi:
* `<table>`: Elemen tabel utama.
* `<thead>`: Bagian kepala tabel.
* `<tbody>`: Bagian isi data tabel.
* `<tr>`: Baris tabel (*Table Row*).
* `<th>`: Sel judul kolom (*Table Heading*).
* `<td>`: Sel data isi (*Table Data*).

---

### 7. Formulir Input (`<form>`)
Digunakan untuk menerima masukan dari pengguna:
```html
<form action="#" method="POST">
    <label for="nama">Nama Lengkap:</label>
    <input type="text" id="nama" name="nama" placeholder="Tuliskan nama" required>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>

    <label for="kategori">Pilihan:</label>
    <select id="kategori" name="kategori">
        <option value="1">Pilihan Pertama</option>
        <option value="2">Pilihan Kedua</option>
    </select>

    <label for="pesan">Pesan:</label>
    <textarea id="pesan" name="pesan" rows="4"></textarea>

    <button type="submit">Kirim</button>
</form>
```
* Atribut `required`: Memastikan input wajib diisi sebelum form dapat dikirim.
* Atribut `placeholder`: Teks petunjuk abu-abu sebelum pengguna mengetik.

---

## Bagian 2: CSS Dasar (Cascading Style Sheets)

CSS digunakan untuk mengatur tampilan, warna, spasi, ukuran font, dan tata letak elemen HTML.

### 1. Cara Menghubungkan CSS
1. **Eksternal (Rekomendasi Terbaik)**: Menggunakan file terpisah (`style.css`) lalu dipanggil via `<link rel="stylesheet" href="style.css">`.
2. **Internal**: Ditulis di dalam tag `<style>` di dalam `<head>`.
3. **Inline**: Ditulis langsung di atribut tag HTML, misalnya `<p style="color: blue;">`.

---

### 2. Anatomi Sintaks & Selektor CSS
```css
selektor {
    properti: nilai;
}
```

* **Selektor Universal (`*`)**: Memilih semua elemen di halaman.
* **Selektor Elemen / Tag**: Contoh `p`, `h1`, `body`.
* **Selektor Class (`.nama-class`)**: Memilih elemen berdasarkan atribut `class="..."`. Dapat dipakai berulang kali.
* **Selektor ID (`#nama-id`)**: Memilih elemen berdasarkan atribut `id="..."`. Harus unik dalam satu halaman.
* **Pseudo-Class (`:hover`, `:focus`, `:nth-child`)**: Mengatur gaya saat terjadi interaksi pengguna.

---

### 3. Konsep CSS Box Model (Sangat Penting!)
Setiap elemen di halaman web diperlakukan sebagai sebuah kotak (box) yang terdiri dari 4 lapisan:

```
+------------------------------------------+
|                 MARGIN                   |  <-- Jarak luar elemen ke elemen lain
|  +------------------------------------+  |
|  |              BORDER                |  |  <-- Garis batas tepi elemen
|  |  +------------------------------+  |  |
|  |  |           PADDING            |  |  |  <-- Ruang jarak dalam (isi ke border)
|  |  |  +------------------------+  |  |  |
|  |  |  |      KONTEN (ISI)      |  |  |  |  <-- Teks, gambar, dsb (width x height)
|  |  |  +------------------------+  |  |  |
|  |  +------------------------------+  |  |
|  +------------------------------------+  |
+------------------------------------------+
```

* **`box-sizing: border-box;`**: Memastikan `padding` dan `border` dihitung ke dalam lebar total elemen sehingga layout tidak melar atau rusak.

---

### 4. Display & Layout Dasar

#### A. Block vs Inline vs Inline-Block
* **`display: block`**: Mengambil lebar penuh (1 baris sendiri), contoh: `<div>`, `<p>`, `<h1>`.
* **`display: inline`**: Mengalir bersama teks, tidak bisa diatur width dan height, contoh: `<span>`, `<a>`.
* **`display: inline-block`**: Mengalir sebaris tetapi bisa diatur margin, padding, width, dan height, contoh tombol `.btn`.

#### B. CSS Flexbox (1 Dimensi)
Sangat ideal untuk baris navigasi, tombol sejajar, atau tata letak satu dimensi:
```css
.container-flex {
    display: flex;
    justify-content: space-between; /* Pengaturan horizontal */
    align-items: center;            /* Pengaturan vertikal */
    gap: 20px;                      /* Jarak antar anak elemen */
}
```

#### C. CSS Grid (2 Dimensi)
Sangat ideal untuk galeri kartu (cards), portofolio, dan tata letak kolom berulang:
```css
.container-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
}
```

---

### 5. Media Queries & Desain Responsif
Agar website nyaman dibaca di smartphone maupun laptop:
```css
@media (max-width: 768px) {
    /* Perubahan tampilan saat layar 768px atau lebih kecil */
    .navbar {
        flex-direction: column;
    }
    .about-grid {
        grid-template-columns: 1fr;
    }
}
```

---

## Bagian 3: Checklist Praktek Latihan

Untuk menguji pemahaman, cobalah latihan-latihan berikut pada kode proyek Anda:
1. [ ] Ganti nama dan deskripsi pada bagian `#home` dengan identitas Anda sendiri.
2. [ ] Tambahkan baris baru pada tabel biodata di section `#about` (misalnya: "Bahasa Pemrograman Favorit").
3. [ ] Ubah palet warna utama di file `style.css` (misalnya ganti warna `#2563eb` dengan warna kesukaan Anda seperti hijau `#16a34a` atau ungu `#7c3aed`).
4. [ ] Tambahkan 1 kartu proyek baru di bagian `#projects`.
5. [ ] Coba jalankan file `index.html` di browser menggunakan web server Laragon (`http://localhost/msc` atau klik kanan `Open with Live Server / Browser`).
