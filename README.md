<h1 align="center">NEWS_PORTAL</h1>

<p align="center"><em>Transforming News into Impactful Stories Daily</em></p>

<p align="center">
  <img src="https://img.shields.io/badge/last%20commit-last%20monday-bluegray" />
  <img src="https://img.shields.io/badge/javascript-57.7%25-blue" />
  <img src="https://img.shields.io/badge/languages-6-blue" />
</p>

---

### 📌 Built with the tools and technologies:

<p>
  <img src="https://img.shields.io/badge/JSON-black?logo=json&logoColor=white" />
  <img src="https://img.shields.io/badge/Markdown-black?logo=markdown&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-yellow?logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/PHP-777BB4?logo=php&logoColor=white" />
</p>

## 🗂️ Struktur Proyek

```
newsportal/
├── admin/                  # Panel admin (manajemen berita, kategori, dll.)
├── includes/               # File konfigurasi & koneksi database
├── images/                 # Folder untuk gambar (logo, artikel, dll.)
├── news-images/            # Gambar yang diunggah untuk artikel
├── user/                   # Halaman user (pembaca berita)
├── index.php               # Beranda utama portal berita
├── contact.php             # Halaman kontak
├── about-us.php            # Tentang portal
├── live-news.php           # Berita live streaming atau update real-time
├── news-details.php        # Halaman detail artikel
└── ...
```

## ⚙️ Kebutuhan Sistem

### Server
- Web Server: Apache/Nginx
- PHP: Versi 7.x atau 8.x
- MySQL/MariaDB

### Tools Tambahan
- Text Editor: VS Code / Sublime Text
- phpMyAdmin (opsional untuk mempermudah kelola database)

## 💾 Instalasi dan Konfigurasi

### 1. Ekstrak Proyek
Ekstrak `newsportal.zip` ke direktori root server web Anda:
- Untuk **XAMPP**: `htdocs/newsportal/`
- Untuk **Laragon**/**WAMP**: `www/newsportal/`

### 2. Buat Database
Buat database dengan nama (misalnya) `newsportal` melalui phpMyAdmin.

### 3. Import SQL
Cari file `.sql` di dalam folder proyek (biasanya di `newsportal/database/newsportal.sql`) dan import ke database.

### 4. Konfigurasi Koneksi Database
Edit file:
```php
includes/config.php
```
Contoh:
```php
<?php
define('DB_SERVER','localhost');
define('DB_USER','root');
define('DB_PASS','');
define('DB_NAME','newsportal');
$con = mysqli_connect(DB_SERVER, DB_USER, DB_PASS, DB_NAME);
if (mysqli_connect_errno()) {
    echo "Failed to connect to MySQL: " . mysqli_connect_error();
}
?>
```

### 5. Akses Portal
- **User Portal**: `http://localhost/newsportal/index.php`
- **Admin Panel**: `http://localhost/newsportal/admin/`

## 🔐 Login Admin

Masuk ke panel admin menggunakan akun default yang ada di database. Jika tidak ada, Anda dapat membuat akun admin langsung melalui phpMyAdmin di tabel `tbladmin`.

## 🧩 Fitur Utama

### Untuk Admin:
- Login dan otorisasi
- Manajemen kategori berita
- Tambah/Edit/Hapus artikel berita
- Kelola komentar pengguna

### Untuk User:
- Melihat daftar berita terbaru
- Membaca detail artikel
- Filter berita berdasarkan kategori
- Menghubungi admin melalui form kontak

## 🛠️ Catatan Pengembangan

- Semua halaman PHP telah dipisahkan untuk manajemen dan pengguna.
- Penggunaan Bootstrap dan font Google untuk UI responsif.
- Upload gambar artikel disimpan di folder `news-images/`.

## 🧪 Troubleshooting

| Masalah                        | Solusi                                                  |
|-------------------------------|----------------------------------------------------------|
| Koneksi database gagal        | Periksa `config.php` dan pastikan kredensial benar.     |
| Gambar artikel tidak muncul   | Pastikan folder `news-images/` memiliki izin write.     |
| Login admin gagal             | Reset password langsung melalui database (MD5 hash).    |
