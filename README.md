1. Nama Proyek:
Sistem Informasi Manajemen Dipo Laundry
2. Deskripsi Proyek:
Dipo Laundry adalah sebuah aplikasi berbasis web yang dirancang untuk memudahkan manajemen operasional usaha laundry. Aplikasi ini melayani dua jenis pengguna utama: pelanggan (user) dan administrator (admin). Pelanggan dapat melakukan pemesanan layanan laundry secara online, melihat riwayat transaksi, dan memantau status pesanan mereka. Sementara itu, administrator memiliki akses penuh untuk mengelola pesanan yang masuk, memperbarui status pengerjaan laundry, melihat laporan transaksi, dan mengelola data pengguna serta layanan.
3. Tools dan Teknologi yang Digunakan:
Berikut adalah daftar tools dan teknologi yang digunakan dalam pengembangan proyek ini:
•	Front-end:
- HTML5: Sebagai bahasa markup standar untuk membuat struktur halaman web.
-	CSS3: Digunakan untuk mengatur tampilan dan layout halaman web, termasuk penggunaan Flexbox dan Grid untuk desain yang responsif.
-	JavaScript (ES6): Digunakan untuk membuat halaman web menjadi interaktif, seperti validasi form, kalkulasi estimasi harga, dan fitur live chat.
-	Bootstrap 5.3.3: Framework CSS yang digunakan untuk mempercepat proses pengembangan tampilan (UI) yang responsif dan modern.
-	Font Awesome 6.5.1: Library ikon yang digunakan untuk mempercantik tampilan antarmuka dengan berbagai pilihan ikon.
-	Google Fonts (Pacifico & Poppins): Digunakan untuk memberikan tipografi yang menarik dan mudah dibaca pada website.
-	Swiper.js: Library JavaScript untuk membuat slider atau carousel testimoni pelanggan yang interaktif.
•	Back-end:
-	PHP: Sebagai bahasa pemrograman sisi server yang utama untuk mengelola logika bisnis, interaksi database, dan manajemen sesi pengguna.
-	MySQL (melalui mysqli): Digunakan sebagai sistem manajemen database untuk menyimpan semua data aplikasi seperti informasi pengguna, pesanan, layanan, dan transaksi.
-	Database (db_dipo_laundry):
yang berisi 3 tabel yaitu:
1.orders: yang mengatur menyimpan semua data pesan user
2.service: data jenis jenis layanan laundry seperti ( Cuci Kering Lipat, Cuci Kering Setrika, Setrika saja, Semua Layanan (express 1 Hari siap). )
3.users: yang meyimapan semua data akun (Admin dan user pengguna)

4. Cara Kerja Website:
A. Halaman Utama (Index)
•	Tampilan Awal: Halaman utama (index.php) adalah gerbang pertama bagi pengunjung. Halaman ini menampilkan informasi umum tentang Dipo Laundry, termasuk keunggulan layanan, testimoni pelanggan, dan informasi kontak.
•	Navigasi: Terdapat menu navigasi yang mengarahkan pengunjung ke halaman login dan registrasi.
•	Fitur Live Chat: Sebuah gelembung obrolan tersedia di pojok kanan bawah yang memungkinkan pengunjung untuk langsung terhubung dengan admin melalui WhatsApp untuk bertanya atau meminta bantuan.
B. Registrasi dan Login Pengguna
•	Registrasi:
1.	Pengguna baru dapat mendaftarkan akun melalui halaman register.php.
2.	Formulir registrasi meminta data seperti nama lengkap, email, dan password.
3.	Sistem akan melakukan validasi untuk memastikan email belum terdaftar dan konfirmasi password sudah benar.
4.	Password pengguna akan di-hash menggunakan password_hash() sebelum disimpan ke database untuk keamanan.
•	Login:
1.	Pengguna yang sudah memiliki akun dapat masuk melalui halaman login.php.
2.	Sistem akan memverifikasi email dan password yang dimasukkan dengan data yang ada di database menggunakan password_verify().
3.	Setelah berhasil login, sistem akan membuat sebuah sesi (session) dan mengarahkan pengguna ke halaman dashboard yang sesuai dengan rolenya (admin atau user).
C. Dashboard Pengguna (User)
•	Halaman Utama Dashboard: Setelah login, pengguna akan diarahkan ke user/index.php. Halaman ini menampilkan sapaan selamat datang dan riwayat pesanan yang pernah dibuat oleh pengguna, lengkap dengan detail layanan, berat, total harga, dan status pesanan.
•	Membuat Pesanan Baru:
1.	Pengguna dapat membuat pesanan baru dengan mengklik tombol "Buat Pesanan Baru" yang akan mengarahkannya ke halaman user/pesan.php.
2.	Di halaman ini, pengguna harus mengisi formulir pemesanan yang meliputi jenis layanan, berat cucian (dalam Kg), tanggal pengambilan, dan catatan tambahan (opsional).
3.	Terdapat fitur kalkulator otomatis yang akan menampilkan estimasi total harga secara real-time berdasarkan jenis layanan dan berat yang diinput.
4.	Setelah formulir dikirim, data pesanan akan disimpan ke dalam database dengan status awal "Proses".
•	Kontak Kami: Jika Anda memiliki pertanyaan atau ingin menghubungi pihak Dipo Laundry, klik menu "Kontak Kami" pada bar navigasi di bagian atas.
•	Logout: Pengguna dapat keluar dari akunnya dengan mengklik tombol "Logout" yang akan menghancurkan sesi dan mengarahkannya kembali ke halaman login.
D. Panel Admin
•	Halaman Utama Admin: Admin yang berhasil login akan diarahkan ke admin/index.php. Halaman ini berfungsi sebagai pusat pengelolaan pesanan.
•	Manajemen Pesanan:
1.	Admin dapat melihat seluruh daftar pesanan yang masuk dari semua pengguna, lengkap dengan detail pelanggan, layanan, berat, total harga, tanggal masuk, dan tanggal pengambilan.
2.	Admin dapat mengubah status setiap pesanan (Proses, Selesai, Diambil) melalui menu dropdown. Perubahan status akan langsung tersimpan ke database secara otomatis.
3.	Admin juga memiliki hak untuk menghapus data pesanan jika diperlukan melalui tombol hapus yang disertai konfirmasi.
•	Laporan Transaksi:
1.	Admin dapat mengakses halaman admin/laporan_transaksi.php untuk melihat rekapitulasi semua transaksi yang pernah terjadi.
2.	Laporan ini ditampilkan dalam bentuk tabel yang rapi dan di bagian bawahnya terdapat total pendapatan dari seluruh transaksi yang tercatat.
5. Akun Dummy (Contoh)
Untuk keperluan demonstrasi dan pengujian, Anda bisa menggunakan data berikut untuk dimasukkan ke dalam database MySQL Anda (misalnya melalui phpMyAdmin).
A. Akun Admin
•	Nama Lengkap: Naca Dipo (Admin)
•	Email: nacadipo@gmail.com
•	Password: naca123
•	Role: admin
B. Akun User
•	Nama Lengkap: Ancaa
•	Email: nacasuhada@gmail.com
•	Password: naca123
•	Role: user

