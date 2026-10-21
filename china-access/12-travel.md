# 12 · Persiapan untuk dinas dan perjalanan

Untuk perjalanan singkat ke luar negeri atau dinas ke Tiongkok, Anda tidak perlu router atau mempelajari protokol: pasang klien Cisco (Cisco Secure Client) di HP, coba sambungkan sekali sebelum berangkat, dan begitu mendarat langsung bisa dipakai. Kedua arahnya sama saja: di luar Tiongkok, saat butuh Google, email kantor, dan peta, pilih wilayah luar negeri yang dekat; saat berada di Tiongkok dan ingin menonton video Tiongkok atau login internet banking Tiongkok, pilih wilayah Tiongkok. Artikel ini membahas persiapan sepuluh menit sebelum berangkat, dua jebakan umum di jaringan hotel dan bandara, serta cara memakai internet banking dan aplikasi pembayaran.

## Sepuluh menit sebelum berangkat

1. Pasang Cisco Secure Client di HP (App Store / Google Play, atau file instalasi dari halaman Cisco situs ini), login ke situs ini dan klik bendera untuk menyalin alamat sebuah wilayah lalu masukkan ke klien, kemudian sambungkan sekali dengan akun dan kata sandi situs ini untuk memastikan berfungsi.
2. Salin alamat dua wilayah lagi dan simpan di klien: satu yang dekat dengan tujuan Anda dan satu sebagai cadangan. Jaringan di sana akan berbeda, dan wilayah terbaiknya sering tidak sama.
3. Catat empat domain (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) dan setidaknya satu jalan masuk ke grup dukungan, supaya Anda bisa menghubungi seseorang kalau ada masalah di tempat yang jaringannya belum Anda kenal.
4. Pasang juga di laptop, atau pakai ekstensi Proxy Web; kalau komputer kantor tidak bisa dipasangi klien, cara ini tetap jalan.

## Setelah mendarat

- Kalau Anda sudah ganti ke SIM lokal atau menyalakan roaming, klien langsung tersambung tanpa perlu diatur ulang; kalau data roaming-nya sendiri sudah keluar dari negara itu, menyambung ke jalur hanya untuk memastikan wilayah exit-nya.
- Di luar Tiongkok, saat butuh Google, Gmail, email kantor, dan peta: pilih wilayah luar negeri yang dekat agar kecepatannya terbaik.
- Saat berada di Tiongkok dan ingin menonton Tencent Video dan iQIYI, mendengarkan NetEase Cloud Music, atau login internet banking: pilih wilayah Tiongkok. Situs Tiongkok keluar dari IP Tiongkok dan situs luar negeri tetap keluar di luar negeri, jadi tersambung ke wilayah Tiongkok saat di Tiongkok tidak menghalangi Anda tetap memakai Gmail.
- Kalau wilayah luar negeri tidak bisa tersambung dari dalam Tiongkok: ganti wilayah, pindah ke data seluler, dan kalau masih gagal pindah ke Hiddify atau OpenVPN; pemblokiran ketiga protokol itu tidak saling terkait.

## Dua jebakan di jaringan hotel, bandara, dan kafe

- Halaman login (captive portal): setelah tersambung ke Wi‑Fi, selesaikan autentikasi di browser dulu, baru nyalakan jalur. Klien yang diatur tersambung otomatis akan mencoba sebelum autentikasi dan gagal; tunggu sebentar atau sambungkan ulang secara manual.
- Pembatasan UDP: cukup banyak jaringan hotel dan bandara yang memperlambat atau memblokir UDP. Cisco berjalan di atas TLS dan tidak terpengaruh, itulah sebabnya Cisco jadi rekomendasi utama untuk bepergian; kalau Anda memakai Hiddify atau jaringan Privat dan terasa lambat atau putus-putus, pindah ke Cisco.

## Internet banking, pembayaran, 12306

Aplikasi-aplikasi ini mencatat IP saat login, dan berpindah bolak-balik antara luar negeri dan Tiongkok paling mudah memicu sistem pengendalian risiko. Saat perlu mengurus sesuatu, sambungkan ke wilayah Tiongkok dulu baru buka aplikasinya; setelah selesai, tutup aplikasinya baru putuskan sambungan. Selama bepergian, jangan memakai internet banking yang sama sambil sering berganti di antara dua jenis jaringan itu.

Kode verifikasi SMS yang tidak pernah sampai tidak ada hubungannya dengan jalur; itu masalah roaming nomor telepon. Sebelum berangkat, aktifkan roaming untuk nomor Tiongkok Anda atau ganti ke paket yang bisa menerima kode di luar negeri.

## Tanya jawab

**Perjalanannya hanya beberapa hari. Perlu beli sebulan?** Tidak. Klaim uji coba gratis 4 jam, atau isi kredit dan bayar per hari: paket Pribadi memakai 1 kredit per hari, sekitar 0,32 dolar AS per hari, sangat pas untuk beberapa hari.

**Bisakah HP dan laptop tersambung bersamaan?** Bisa. Tergantung paketnya, satu akun bisa online di 2 / 4 / 8 perangkat bersamaan (Pribadi / Keluarga / Perusahaan), dan paket Pribadi pas untuk satu HP ditambah satu laptop.

**Kenapa untuk bepergian yang direkomendasikan Cisco, bukan Hiddify?** Di jaringan yang belum dikenal, kekhawatiran terbesar adalah UDP yang dibatasi. Cisco berjalan di atas TLS, sama seperti membuka situs HTTPS, dan bisa lewat hampir di mana saja; Hiddify lebih cepat di jaringan dengan packet loss tinggi, tetapi tidak jalan kalau UDP dibatasi. Memasang keduanya dan berpindah kalau salah satu tidak jalan adalah cara paling andal.

**Apakah memakai wilayah Tiongkok di luar negeri membuat situs lokal lebih lambat?** Situs lokal paling lancar lewat koneksi langsung: putuskan sambungan setelah selesai dengan konten Tiongkok, atau sambungkan hanya saat diperlukan.

## Bacaan lanjutan

- [Unduhan dan pengaturan Cisco AnyConnect](https://www.leotun.com/id/anyconnect?utm_source=github&utm_content=china-access-12)
- [Cara mahasiswa di luar negeri menyiapkan VPN ke Tiongkok](https://www.leotun.com/id/guides/students?utm_source=github&utm_content=china-access-12)
- [Cara menghubungi kami dan cara agar tidak putus kontak](https://www.leotun.com/id/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [VPN ke Tiongkok: gratis atau berbayar](https://www.leotun.com/id/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/travel?utm_source=github&utm_content=china-access-12

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-12) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-12) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
