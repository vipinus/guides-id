# 01 · Cara kerja mengakses Tiongkok dari luar negeri

## Yang Anda alami

Anda berada di luar negeri lalu membuka iQIYI, Bilibili, atau NetEase Cloud Music, dan muncul pesan "Konten ini hanya tersedia di Tiongkok daratan"; internet banking dan 12306 sama sekali tidak mau terbuka, atau kode verifikasinya tidak pernah sampai.

## Penyebabnya cuma satu: IP Anda terdaftar di mana

Saat perangkat Anda online, operator memberinya alamat IP publik. Ada daftar alamat tingkat dunia yang mencatat negara dan operator pemilik setiap alamat. Platform video dan musik Tiongkok hanya membeli hak siar untuk **Tiongkok daratan** dan secara hukum tidak boleh menayangkannya di luar wilayah itu, jadi begitu melihat IP luar negeri, mereka langsung menolak.

Bank dan situs tiket memakai logika lain. Bagi mereka ini bukan soal hak cipta, melainkan manajemen risiko: login dari IP luar negeri dianggap berisiko tinggi dan langsung diblokir.

## Cara mengatasinya

Buat IP yang dilihat server menjadi IP Tiongkok daratan. Caranya, kirim dulu lalu lintas Anda ke server yang berada di Tiongkok daratan, lalu server itu yang mengunjungi situs tujuan atas nama Anda. Situs tujuan melihat IP server tersebut dan membiarkannya masuk.

Itulah fungsi "jalur ke Tiongkok": mengirim lalu lintas Anda keluar dari IP Tiongkok daratan.

## Tiga salah kaprah yang umum

- **Ganti DNS tidak membantu.** DNS hanya menerjemahkan nama domain menjadi alamat; situs tujuan melihat IP asal Anda, bukan DNS yang Anda pakai.
- **Beberapa platform juga melihat wilayah sistem.** Selain IP, sebagian platform juga memeriksa bahasa perangkat dan wilayah toko aplikasi; dalam kasus itu, ganti juga wilayah sistemnya.
- **Kecepatan tergantung kualitas jalur antara kedua titik.** Sambungan lintas negara dari luar negeri ke Tiongkok daratan adalah titik hambatnya, jadi memilih titik masuk yang dekat dengan Anda dan punya jalur yang dioptimalkan ke Tiongkok daratan lebih penting daripada spesifikasi servernya sendiri.

## Bacaan lanjutan

- [Cara koneksi mana yang cocok untuk situasi apa](02-choose-your-connection-method.md)
- [Daftar periksa untuk tidak bisa tersambung, lambat, dan sering putus](../troubleshooting/01-cannot-connect-slow-drops.md)

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=network-01) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=network-01) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; setiap teman undangan yang membayar memberi Anda berdua masing-masing 20 hari paket Pribadi, promo tanpa batas waktu
