# 03 · Sudah tersambung, tapi situs video masih menampilkan pemberitahuan hak cipta: IPv6 dan DNS yang bocor

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

Anda sudah lolos langkah 1 di [02 · Sudah tersambung ke Tiongkok tapi tetap tidak bisa menonton](02-still-blocked-after-connecting.md) (IP exit sudah terdeteksi Tiongkok daratan), tetapi situsnya masih bilang "tidak dapat diputar karena pembatasan hak cipta". Sembilan dari sepuluh kasus, masih ada jalur di perangkat yang tidak lewat VPN: **IPv6** atau **DNS**. Situs video menentukan lokasi Anda dari alamat yang dilihatnya, dan selama ada satu jalur yang bocor, yang dilihatnya tetap luar negeri.

## Kenapa bisa bocor

- Perangkat modern punya alamat IPv4 sekaligus IPv6, dan browser mendahulukan IPv6. Kalau VPN hanya mengambil alih IPv4, permintaan IPv6 langsung keluar lewat internet rumah Anda.
- "DNS aman" bawaan browser, "DNS Pribadi" di Android, atau alat mesh networking lain yang sedang jalan (Tailscale dan sejenisnya) akan mengambil alih resolusi nama lebih dulu dari VPN.

"Tersambung" hanya berarti terowongannya sudah terbentuk. Bukan berarti semua lalu lintas lewat terowongan itu.

## Pemeriksaan lima langkah

1. **Cek IPv6.** Setelah tersambung, cari "test ipv6" dan buka halaman pengujian. Kalau kolom IPv6 menunjukkan alamat di negara tempat Anda berada → masalahnya di sini, lanjut ke langkah 2. Kalau kedua kolom menunjukkan Tiongkok daratan, atau IPv6 tidak tersedia → lanjut ke langkah 3.
2. **Matikan IPv6, atau pakai klien yang memblokir IPv6.** Windows: di properti adaptor jaringan, hilangkan centang "Internet Protocol Version 6". macOS: pengaturan Jaringan → TCP/IP → atur IPv6 ke "Hanya link-local". HP: matikan Wi‑Fi dan coba sekali dengan data seluler; internet rumah biasanya punya IPv6, sedangkan data seluler operator sering tidak.
3. **Cek DNS.** Setelan Chrome → Privasi dan keamanan → matikan "Gunakan DNS aman"; di Android matikan "DNS Pribadi"; tutup VPN lain, alat mesh networking, dan ekstensi proxy.
4. **Tutup aplikasinya sepenuhnya lalu buka lagi; untuk versi web, hapus data situsnya.** Platform menyimpan hasil pengecekan wilayah sebelumnya.
5. **Ganti ke titik masuk lain lalu coba lagi.** Alamat exit tertentu mungkin baru saja ditandai oleh platform.

## Cara LeoTun menanganinya

Sejak September 2026, ketiga cara koneksi LeoTun (Hiddify, Cisco AnyConnect, OpenVPN) langsung menolak IPv6 di dalam terowongan dan mengirim pengaturan DNS yang memaksa resolusi di dalam terowongan; tidak ada pengaturan yang perlu diubah di perangkat Anda. **Konfigurasi Hiddify yang diimpor sebelum September belum punya aturan ini. Hapus, lalu pindai kode QR untuk mengimpor ulang.**

Pilihan router memang tidak bocor sejak awal: seluruh LAN keluar lewat router, jadi IPv6 dan DNS perangkat tidak pernah sampai ke luar.

## Kasus yang tetap memicu pemberitahuan

| Kasus | Gejala | Solusi |
|---|---|---|
| Exit-nya bukan Tiongkok daratan | Cek IP menunjukkan Hong Kong / Taiwan / Jepang | Ganti ke titik masuk Tiongkok; alamat Hong Kong dan Taiwan juga dianggap luar negeri oleh Tencent dan iQIYI |
| Aturan routing khusus mengatur domain video ke "direct" | Halaman web terbuka, tetapi video tidak bisa diputar | Ubah domain Tiongkok supaya lewat node; pengguna di luar Tiongkok tidak perlu menyalakan "langsung untuk Tiongkok" |
| Anda memakai Proxy Web | Jalan di browser, tidak di aplikasi | Menonton video butuh terowongan untuk seluruh perangkat; Proxy Web hanya mencakup browser |

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=troubleshooting-03) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-03) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, berlaku jangka panjang
