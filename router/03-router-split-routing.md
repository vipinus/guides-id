# 03 · Apa itu split routing di router

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/router-firmware?utm_source=github&utm_content=router-03

## Dalam satu kalimat

Pasang VPN di router, dan setiap perangkat di rumah otomatis lewat VPN begitu tersambung ke Wi-Fi. Perangkat yang tidak bisa dipasangi klien, seperti set-top box, konsol game, dan printer, juga ikut bisa memakainya.

## Masalah apa yang diselesaikan split routing

Kalau semua lalu lintas lewat VPN, Anda akan mengalami dua masalah: situs web lokal jadi lambat (rutenya memutar), dan perangkat lokal tidak bisa dijangkau (printer, NAS, dan halaman admin router semuanya ada di jaringan lokal, tapi lalu lintasnya malah dikirim keluar).

Split routing bekerja dengan memberi router sebuah daftar: domain yang ada di daftar lewat VPN, dan sisanya tersambung langsung. Arahnya tergantung di mana Anda berada dan sisi mana yang ingin dijangkau, dan ditentukan otomatis oleh wilayah yang Anda pilih:

- **Di luar negeri, dengan wilayah Tiongkok dipilih (menjangkau Tiongkok)**: situs web dan aplikasi Tiongkok lewat VPN, dan sisanya tersambung langsung.
- **Di Tiongkok, dengan wilayah luar negeri dipilih (menjangkau layanan luar negeri)**: secara bawaan hanya situs web dan layanan yang diblokir yang lewat VPN; situs web Tiongkok, dan situs luar negeri yang memang bisa dibuka dari Tiongkok (situs perusahaan asing, unduhan Apple dan Microsoft, platform game, dan sejenisnya), tersambung langsung tanpa memutar, secepat tanpa router.

## Tiga mode

| Mode | Ke mana lalu lintas pergi | Kapan dipakai |
|---|---|---|
| Global | Semuanya lewat VPN | Sementara, saat memeriksa masalah |
| Split routing | Domain di daftar lewat VPN, sisanya tersambung langsung | Sehari-hari |
| Direct (langsung) | Tidak ada yang lewat VPN | Saat Anda tidak membutuhkannya untuk sementara |

## Menjangkau layanan luar negeri dari Tiongkok: hanya situs yang diblokir

Sejak 14 Oktober 2026, split routing ke arah layanan luar negeri dari Tiongkok secara bawaan hanya mengirim situs web dan layanan yang diblokir lewat VPN. Dasarnya adalah daftar situs yang diblokir yang diperbarui otomatis setiap hari, ditambah layanan seperti Telegram yang tersambung ke alamat tetap tanpa mencari nama situs. Situs web yang memang bisa dibuka dari Tiongkok, baik situs Tiongkok maupun luar negeri, tersambung langsung.

Sakelarnya ada di halaman admin router, di "VPN settings" (pengaturan VPN) bagian smart split routing: kotak centang "Blocked sites only" (hanya situs yang diblokir), tercentang secara bawaan. Hapus centangnya untuk kembali ke perilaku sebelumnya: situs Tiongkok tersambung langsung, sisanya lewat VPN.

Firmware yang di-flash sebelum Oktober 2026 belum menampilkan kotak centang ini; bawaan baru sudah berlaku di router-router itu lewat pembaruan otomatis. Untuk mengubahnya, hubungi layanan pelanggan, yang bisa melakukannya dari jarak jauh.

Arah menjangkau Tiongkok dari luar negeri tidak berubah.

## Jebakan

- **Sebuah situs tidak terbuka dengan split routing**: periksa dulu apakah situs itu ada di daftar. Situs yang tidak ada di daftar tersambung langsung, dan kalau situs itu memang dari awal tidak bisa dibuka, split routing tidak akan membantu. Pindah sementara ke "Global" untuk memastikan.
- **Di Tiongkok, sebuah situs luar negeri tidak terbuka**: hapus centang "Blocked sites only" di bagian smart split routing (atau pindah sementara ke "Global") lalu coba lagi. Kalau kemudian terbuka, situs itu diblokir tapi belum masuk daftar; kirim alamatnya ke layanan pelanggan.
- **Situs yang diblokir tidak terbuka, tapi yang lain normal**: kemungkinan besar perangkat menyalakan pengaturan DNS terenkripsi ("DNS Pribadi" / Private DNS di Android, "DNS Aman" / Secure DNS di browser), sehingga router tidak bisa melihat situs apa yang sedang dicari. Matikan pengaturan itu.
- **Printer atau NAS tidak bisa dijangkau setelah tersambung**: artinya alamat jaringan lokal ikut dikirim keluar. Periksa apakah aturan split routing mengecualikan rentang privat seperti 192.168.x.x.
- **Performa router** menentukan batas atasnya. CPU router lama kewalahan mengolah lalu lintas terenkripsi, yang terasa sebagai seluruh rumah melambat. Dalam kasus itu, masalahnya bukan di jalur VPN.

## Satu akun, satu router

Kebanyakan layanan menautkan router ke akun (lewat alamat MAC). Satu akun ditautkan ke satu router, dan saat ganti router Anda harus melepas tautannya dulu. Dengan begitu akun tetap milik Anda seorang.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-03) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-03) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
