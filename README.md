# 🌊 Jaga Pesisir — Platform Edukasi Konservasi Laut & Pesisir Nusantara

> **Responsive Educational Website** mengenai Pelestarian Ekosistem Pesisir, Restorasi Mangrove, dan Perlindungan Keanekaragaman Hayati Laut Indonesia.
> Dibuat untuk memenuhi Tugas Proyek Ujian Tengah Semester (UTS) Mata Kuliah Pemrograman Web.

---

## 📌 Informasi Proyek & Tema SDGs

* **Judul Website:** Jaga Pesisir — Rawat Ombak, Lindungi Karang, Jaga Masa Depan Pesisir
* **Tema Utama:** **Tema 5 — Jaga Pesisir (Konservasi Laut dan Pantai)**
* **Target SDGs:**
  * **SDG 13 (Climate Action):** Penanganan perubahan iklim melalui penyerapan karbon biru (*Blue Carbon*) dan peredaman bencana abrasi.
  * **SDG 14 (Life Below Water):** Konservasi ekosistem bawah laut, perluasan Kawasan Konservasi Perairan (MPA), serta pencegahan pencemaran plastik.
* **Sasaran Pengguna:** Masyarakat umum, pelajar, mahasiswa, dan komunitas peduli lingkungan hidup.

---

## 👥 Identitas & Pembagian Tugas Kelompok (Kelompok 3)

| No. | Nama Mahasiswa | NIM | Tugas & Tanggung Jawab Utama |
| :---: | :--- | :---: | :--- |
| 1 | **Pande Komang Krisna Wahyudi** | `2515091001` | **Ketua Tim & Lead CSS**: Penanggung jawab `index.html` (Beranda), perancangan *Design System* (`style.css`), komponen global (*Header Navigasi* & *Footer*), serta animasi CSS murni (*Stacking Cards* & *Infinite Carousel*). |
| 2 | **Kadek Adi Yamika** | `2515091111` | **Content & Layout Specialist**: Penanggung jawab `edukasi.html` (Krisis & SDG), riset data ancaman pesisir, penyelarasan indikator SDG 13 & 14, serta struktur kartu ancaman (*Threat Cards*). |
| 3 | **Nyoman Shiva Arya Wiguna** | `2515091027` | **UX & Copywriter**: Penanggung jawab `panduan.html` (Pilar Konservasi), penyusunan materi 4 pilar strategis, dan kompilasi data statistik metrik konservasi. |
| 4 | **Gst A.A. Galuh Sasikirana Ambalika** | `2515091103` | **Asset & Media Research**: Penanggung jawab `ekspedisi.html` (Ekspedisi Bahari), kurasi aset media/ikonografi, dan materi 5 Zona Konservasi Nusantara. |
| 5 | **I Komang Putra Vivekananda** | `2515091011` | **Interactive CSS Developer**: Penanggung jawab `tentang.html` (Aksi Mandiri & Profil), pengembangan fitur *Kalkulator Kebiasaan Pesisir* murni CSS (`:checked`), dan penyusunan referensi. |

---

## 🌐 Deskripsi & Struktur Halaman Website

Platform ini terdiri dari **5 halaman HTML utama** yang saling terhubung secara konsisten melalui navigasi global:

1. **`index.html` (Beranda):**
   * *Hero Section* dengan kalimat ajakan (*Call-to-Action*) yang kuat dan *badge* melayang (*floating badges*).
   * Statistik fakta cepat (*Quick Stats*) mengenai panjang garis pantai dan potensi *Blue Carbon* Indonesia.
2. **`edukasi.html` (Krisis & SDG):**
   * Edukasi 4 krisis utama pesisir (Abrasi, Deforestasi Mangrove, Sampah Plastik, dan *Coral Bleaching*).
   * Komparasi peran konservasi pesisir terhadap ketercapaian target **SDG 13** dan **SDG 14**.
3. **`panduan.html` (Pilar Konservasi):**
   * 4 Pilar utama aksi pelestarian (Restorasi Mangrove, Transplantasi *Bio-Rock*, Bank Sampah Muara, dan Kearifan Adat *Sasi Laut*).
   * Ditampilkan dengan efek visual **Stacking Cards** bertumpuk yang interaktif saat di-scroll.
4. **`ekspedisi.html` (Ekspedisi Bahari):**
   * Eksplorasi 3 tingkatan kedalaman pesisir (0–5m, 5–20m, 20–50m) dengan efek *Glassmorphism*.
   * Komedi putar berjalan tanpa henti (**Infinite Carousel**) yang menampilkan 5 Zona Konservasi Nusantara (Pantura, Kepri, Wakatobi, Raja Ampat, dan Laut Banda).
5. **`tentang.html` (Aksi Mandiri, Profil & Referensi):**
   * *Kalkulator Kebiasaan Bahari* interaktif berbasis CSS `:checked` tanpa JavaScript.
   * Kartu profil anggota tim pengembang proyek.
   * Daftar rujukan data ilmiah (UN SDGs, KKP RI, BRIN) serta atribusi lisensi aset digital.

---

## 🛠️ Teknologi & Standar Pengembangan

* **HTML5 Semantik:** Menggunakan elemen semantik seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, dan `<footer>`demi struktur kode yang bersih dan terakses (*accessible*).
* **CSS3 Murni:** 
  * *Design Tokens* menggunakan **CSS Custom Properties / Variables** (`:root`).
  * Tata letak modern menggunakan **Flexbox** dan **CSS Grid**.
  * Animasi murni CSS (`@keyframes`, `transition`, `position: sticky`).
  * Efek visual modern (*Glassmorphism* & *Backdrop Filter*).
* **Tanpa Framework External:** Murni ditulis dari awal (*vanilla HTML/CSS*) tanpa Bootstrap, Tailwind, atau JavaScript sesuai ketentuan proyek.
* **Ikonografi & Tipografi:** Font Awesome 6 Free, Google Fonts (*Plus Jakarta Sans* & *Outfit*).

---

## 💻 Penjelasan Implementasi & Potongan Kode Penting

### 1. Animasi *Infinite Carousel*
Untuk menciptakan efek *carousel* yang berputar mulus tanpa jeda (*seamless*), digunakan teknik duplikasi 2 set kartu di HTML yang digeser sejauh `-50%` dari total panjang rantai track, ditambah kompensasi `-16px` untuk setengah dari *gap* Flexbox (`32px / 2 = 16px`).

```css
/* css/style.css */
.carousel-track {
  display: flex;
  gap: 32px;
  width: max-content;
  animation: infiniteCarouselSlide 40s linear infinite;
}

/* Pause saat kursor mouse diarahkan ke kartu */
.carousel-track:hover {
  animation-play-state: paused;
}

@keyframes infiniteCarouselSlide {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(-50% - 16px)); /* Kompensasi presisi gap */
  }
}
```

### 2. Efek Penumpukan Kartu (*Stacking Cards*) dengan `position: sticky`
Di halaman `panduan.html`, kartu-kartu pilar menumpuk secara berurutan di bawah header saat di-scroll menggunakan kombinasi `position: sticky` dan jarak `top` berjenjang.

```css
/* css/style.css */
.stack-card {
  position: sticky;
  background: #ffffff;
  border-radius: var(--radius-lg);
  box-shadow: 0 -12px 35px rgba(7, 25, 44, 0.08);
}

.stack-card-mangrove  { top: 100px; z-index: 1; }
.stack-card-coral     { top: 130px; z-index: 2; }
.stack-card-cleanup   { top: 160px; z-index: 3; }
.stack-card-community { top: 190px; z-index: 4; }
```

### 3. Menu Navigasi Responsif Seluler (*Checkbox Hack*)
Sesuai batasan proyek tanpa JavaScript, menu *hamburger* pada layar seluler dikendalikan murni menggunakan input `type="checkbox"` yang disembunyikan dan *pseudo-class* `:checked`.

```html
<!-- HTML -->
<input type="checkbox" id="nav-toggle" class="nav-toggle" aria-label="Buka navigasi menu">
<label for="nav-toggle" class="nav-toggle-label">
  <span class="hamburger-bar"></span>
  <span class="hamburger-bar"></span>
  <span class="hamburger-bar"></span>
</label>
```

```css
/* CSS */
@media (max-width: 768px) {
  .nav-toggle:checked ~ .main-navigation {
    display: flex; /* Buka menu saat checkbox dicentang */
  }
}
```

### 4. Responsivitas Layar (*CSS Media Queries*)
Pengaturan *responsive breakpoint* menggunakan prinsip **Desktop-First Standard** yang di-`scale down` untuk Tablet/Mobile dan di-`scale up` untuk Monitor Lebar.

```css
/* Monitor Ekstra Lebar / PC 2K */
@media (min-width: 1440px) {
  :root { --container-max: 1320px; }
  .hero-title { font-size: 3.75rem; }
}

/* Tablet & HP */
@media (max-width: 1024px) {
  .stats-grid, .threats-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 480px) {
  .stats-grid, .threats-grid { grid-template-columns: 1fr; }
}
```

---

## 📁 Struktur Direktori Repositori

```text
jaga-pesisir/
├── index.html              # Halaman Utama (Beranda & Quick Stats)
├── edukasi.html            # Halaman Krisis Pesisir & Harmonisasi SDG 13/14
├── panduan.html            # Halaman 4 Pilar Konservasi (Stacking Cards)
├── ekspedisi.html          # Halaman Ekspedisi Bahari (Kedalaman & Infinite Carousel)
├── tentang.html            # Halaman Kalkulator Aksi, Profil Tim, & Referensi
├── css/
│   └── style.css           # Stylesheet Utama (Design System & Media Queries)
├── images/                 # Berkas Gambar & Aset Visual (.jpg, .png)
└── README.md               # Dokumentasi Lengkap Proyek
```

---

## 🔗 Tautan Publikasi & Repositori

* **URL Website (GitHub Pages):** https://pndkrisna.github.io/jaga-pesisir-web
* **URL Repositori GitHub:** https://github.com/pndKrisna/jaga-pesisir-web

---

## 📚 Referensi Konten & Atribusi Aset

### 1. Sumber Data & Informasi Ilmiah
* **United Nations SDGs:** Target & Indikator [SDG 13]([suspicious link removed]) dan [SDG 14]([suspicious link removed]).
* **Kementerian Kelautan dan Perikanan (KKP RI):** Data statistik luas tutupan mangrove & terumbu karang nasional.
* **BRIN Oseanografi:** Riset ekosistem padang lamun, *Blue Carbon*, dan teknologi *Bio-Rock*.

### 2. Aset Digital & Lisensi
* **Google Fonts:** Font *Plus Jakarta Sans* & *Outfit* (Lisensi *SIL Open Font License*).
* **Font Awesome 6 Free:** Ikon UI/UX Vektor (Lisensi *CC BY 4.0*).
* **Unsplash & Pexels:** Gambar latar belakang & visual kartu (Lisensi Bebas Komersial).
```
