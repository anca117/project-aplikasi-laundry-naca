# Sistem Informasi Manajemen Dipo Laundry

## 1. Nama Proyek
Sistem Informasi Manajemen Dipo Laundry

## 2. Deskripsi Proyek
Dipo Laundry adalah sebuah aplikasi berbasis web yang dirancang untuk memudahkan manajemen operasional usaha laundry.
Aplikasi ini melayani dua jenis pengguna utama: pelanggan (user) dan administrator (admin).
Pelanggan dapat melakukan pemesanan layanan laundry secara online, melihat riwayat transaksi, dan memantau status pesanan mereka.
Sementara itu, administrator memiliki akses penuh untuk mengelola pesanan yang masuk, memperbarui status pengerjaan laundry, melihat laporan transaksi, dan mengelola data pengguna serta layanan.

## 3. Tools dan Teknologi yang Digunakan
Berikut adalah daftar tools dan teknologi yang digunakan dalam pengembangan proyek ini:

### Front-end:
- **HTML5:** Sebagai bahasa markup standar untuk membuat struktur halaman web.
- **CSS3:** Digunakan untuk mengatur tampilan dan layout halaman web, termasuk penggunaan Flexbox dan Grid untuk desain yang responsif.
- **JavaScript (ES6):** Digunakan untuk membuat halaman web menjadi interaktif, seperti validasi form, kalkulasi estimasi harga, dan fitur live chat.
- **Bootstrap 5.3.3:** Framework CSS yang digunakan untuk mempercepat proses pengembangan tampilan (UI) yang responsif dan modern.
- **Font Awesome 6.5.1:** Library ikon yang digunakan untuk mempercantik tampilan antarmuka dengan berbagai pilihan ikon.
- **Google Fonts (Pacifico & Poppins):** Digunakan untuk memberikan tipografi yang menarik dan mudah dibaca pada website.
- **Swiper.js:** Library JavaScript untuk membuat slider atau carousel testimoni pelanggan yang interaktif.

### Back-end:
- **PHP:** Sebagai bahasa pemrograman sisi server yang utama untuk mengelola logika bisnis, interaksi database, dan manajemen sesi pengguna.
- **MySQL (melalui `mysqli`):** Digunakan sebagai sistem manajemen database untuk menyimpan semua data aplikasi seperti informasi pengguna, pesanan, layanan, dan transaksi.

### Database (`db_dipo_laundry`):
Berisi 3 tabel utama:
1.  **orders:** Menyimpan semua data pesanan dari pengguna.
2.  **services:** Menyimpan data jenis-jenis layanan laundry (contoh: Cuci Kering Lipat, Cuci Kering Setrika, dll).
3.  **users:** Menyimpan semua data akun untuk Admin dan User.

## 4. Cara Kerja Website

### A. Halaman Utama (Index)
- **Tampilan Awal:** Halaman utama (`index.php`) adalah gerbang pertama bagi pengunjung, menampilkan informasi umum, keunggulan layanan, testimoni, dan kontak.
- **Navigasi:** Terdapat menu yang mengarahkan ke halaman login dan registrasi.
- **Fitur Live Chat:** Gelembung obrolan di pojok kanan bawah untuk terhubung langsung dengan admin melalui WhatsApp.

### B. Registrasi dan Login Pengguna
- **Registrasi:**
    - Pengguna baru mendaftar melalui `register.php`.
    - Formulir meminta nama lengkap, email, dan password.
    - Sistem memvalidasi email agar tidak duplikat dan memastikan konfirmasi password cocok.
    - Password di-hash menggunakan `password_hash()` untuk keamanan sebelum disimpan.
- **Login:**
    - Pengguna masuk melalui `login.php`.
    - Sistem memverifikasi email dan password menggunakan `password_verify()`.
    - Setelah berhasil, sebuah sesi (`session`) dibuat dan pengguna diarahkan ke dashboard sesuai rolenya (admin atau user).

### C. Dashboard Pengguna (User)
- **Halaman Utama Dashboard:** Setelah login, pengguna diarahkan ke `user/index.php` yang berisi sapaan selamat datang dan riwayat pesanan.
- **Membuat Pesanan Baru:**
    - Pengguna mengklik tombol "Buat Pesanan Baru" untuk ke halaman `user/pesan.php`.
    - Mengisi formulir yang meliputi jenis layanan, berat (Kg), tanggal pengambilan, dan catatan.
    - Terdapat kalkulator otomatis untuk estimasi total harga secara real-time.
    - Data pesanan disimpan ke database dengan status awal "Proses".
- **Kontak Kami:** Pengguna dapat mengakses halaman kontak dari menu navigasi untuk menghubungi pihak laundry.
- **Logout:** Mengklik tombol "Logout" akan menghancurkan sesi dan mengembalikan pengguna ke halaman login.

### D. Panel Admin
- **Halaman Utama Admin:** Admin diarahkan ke `admin/index.php` yang berfungsi sebagai pusat pengelolaan pesanan.
- **Manajemen Pesanan:**
    - Admin dapat melihat seluruh daftar pesanan yang masuk.
    - Admin dapat mengubah status setiap pesanan (Proses, Selesai, Diambil) yang akan langsung tersimpan ke database.
    - Admin memiliki hak untuk menghapus data pesanan.
- **Laporan Transaksi:**
    - Admin dapat mengakses `admin/laporan_transaksi.php` untuk melihat rekapitulasi semua transaksi.
    - Laporan ditampilkan dalam bentuk tabel lengkap dengan total pendapatan.

## 5. Akun Dummy (Contoh)
Untuk keperluan demonstrasi dan pengujian, Anda bisa menggunakan data berikut.

### A. Akun Admin
- **Nama Lengkap:** Naca Dipo (Admin)
- **Email:** nacadipo@gmail.com
- **Password:** naca123
- **Role:** admin

### B. Akun User
- **Nama Lengkap:** Ancaa
- **Email:** nacasuhada@gmail.com
- **Password:** naca123
- **Role:** user
