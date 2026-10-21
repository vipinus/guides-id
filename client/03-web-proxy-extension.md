# 03 · Proxy Web: atur ekstensi ZeroOmega dalam dua langkah

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/web-proxy?utm_source=github&utm_content=client-03

Proxy Web hanya mengalirkan **browser ini** lewat jalur; program lain di sistem tidak tersentuh. Tidak ada klien yang perlu dipasang, tidak perlu hak administrator, dan tidak ada status "tersambung", jadi memang tidak ada koneksi yang bisa putus. Cocok untuk komputer kantor, komputer yang sudah tersambung ke VPN kantor, atau kalau Anda hanya ingin satu browser yang memakai jalur. Kapan memakainya dan kapan harus pakai VPN, lihat [Panduan jaringan 02](../network/02-choose-your-connection-method.md).

## Dua langkah

1. **Pasang ekstensi**: pasang ZeroOmega (penerus SwitchyOmega) di Chrome / Edge / Firefox. [Halaman Proxy di situs web](https://www.leotun.com/id/httpproxy?utm_source=github&utm_content=client-03) menyediakan link instalasi untuk tiap browser.
2. **Impor**: login ke situs web, lalu di halaman Proxy klik bendera wilayah yang Anda inginkan (atau klik "Salin tautan impor untuk semua wilayah" untuk mengimpor semua wilayah sekaligus); link pengaturannya akan tersalin. Buka "Import/Export" (impor/ekspor) di ekstensi, tempel link itu di "Restore from online" (pulihkan dari online), lalu klik "Restore" (pulihkan). Wilayah, alamat, dan metode enkripsi terimpor sekaligus, tanpa perlu mengetik apa pun.

Setelah itu, klik ikon ekstensi dan pilih wilayah, lalu masukkan akun dan kata sandi situs web di kotak login yang muncul dari browser. Untuk ganti wilayah, klik wilayah lain di menu ikon; untuk kembali tersambung langsung tanpa jalur, pilih "Direct" (langsung).

## Untuk kasus ini, pakai cara yang mencakup seluruh perangkat

- Aplikasi video dan musik serta pemutar media: kebanyakan tidak memakai proxy browser, jadi hasilnya "halaman web terbuka tapi video tidak mau diputar".
- Aplikasi HP, game, dan software desktop. Pengaturan proxy di software seperti Dropbox hanya menerima HTTP / SOCKS5 tanpa enkripsi, padahal dalam praktiknya proxy harus terenkripsi, jadi Proxy Web situs ini tidak bisa dimasukkan di sana. Pakai Hiddify untuk mengambil alih seluruh perangkat; lihat [10](10-app-proxy.md).
- Menonton Tencent Video atau iQIYI dari luar negeri: situs video juga memeriksa IPv6 dan DNS, yang tidak tercakup oleh Proxy Web; pakai VPN untuk seluruh perangkat.

## Tanya jawab

| Gejala | Penyebab |
|---|---|
| Kotak login terus muncul | Akun sudah kedaluwarsa atau kata sandinya salah |
| Sebagian situs tidak terbuka sementara yang lain normal | Aturan "auto switch" (ganti otomatis) di ekstensi membuat situs itu tersambung langsung; coba sekali dengan mode proxy global |
| Di Tiongkok, hanya situs HTTPS yang terbuka | HTTP biasa diubah di tengah jalan, dan hanya koneksi terenkripsi yang bisa lewat; hampir semua situs sekarang sudah HTTPS |
| Lambat | Ganti wilayah; proxy dan VPN memakai kumpulan server yang sama |

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-03) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-03) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
