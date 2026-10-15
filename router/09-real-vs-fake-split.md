# 09 · Cara kerja split routing di router

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/router-smart-split?utm_source=github&utm_content=router-09

Semuanya disebut "smart split routing", tapi ada router yang tetap terasa merepotkan. Apa itu split routing dijelaskan di [03](03-router-split-routing.md); artikel ini hanya membahas apa yang seharusnya dikerjakan split routing, gejala yang muncul kalau sebagian tidak dikerjakan, dan bagaimana router kami melakukannya.

## Dalam satu kalimat

Yang seharusnya dikerjakan split routing: setiap situs, **beserta gambar, video, dan login-nya**, lewat VPN atau tersambung langsung menurut lokasinya, dan **semua perangkat di rumah mengikuti aturan yang sama**. Kalau hanya sebagian yang dikerjakan, Anda akan melihat gejala di bawah ini.

## Perbandingan gejala

| Yang Anda lihat | Yang terjadi di baliknya |
|---|---|
| Setelah split routing dinyalakan, situs Tiongkok malah jadi lebih lambat | Situs Tiongkok dikira situs luar negeri, sehingga seluruhnya memutar ke luar negeri lalu kembali |
| Halaman web terbuka, tapi video terus berputar, gambar tidak muncul, dan login macet | Daftarnya hanya berisi situs utama, sementara video, gambar, dan login dari situs yang sama lewat jalan lain |
| Anda di luar negeri dengan jalur ke Tiongkok menyala, tapi aplikasi video tetap bilang "仅限中国大陆" (hanya Tiongkok daratan) | Sebagian lalu lintas tidak masuk VPN, dan situs itu melihat alamat luar negeri |
| Bisa diputar di HP tapi tidak di TV atau TV box; satu komputer sama sekali tidak mau lewat VPN | Perangkat itu punya pengaturan jaringan sendiri dan melewati router |
| Aplikasi bank dan pembayaran sesekali memperingatkan "login dari lokasi lain" | Lalu lintas dari aplikasi yang sama sebentar keluar dari Tiongkok, sebentar dari luar negeri |
| Split routing hilang di tengah pemakaian (setelah reboot atau sambung ulang, entah semuanya lewat VPN atau tidak ada sama sekali) | Pengaturannya tidak diingat |

Tidak satu pun dari gejala ini **menampilkan pesan error**. Router terus menunjukkan "Connected" (tersambung), yang membuatnya paling sulit dilacak, dan banyak orang akhirnya mengira jalurnya yang jelek.

## Yang seharusnya dikerjakan split routing

- Satu situs lewat satu jalan bersama halaman web, gambar, video, dan login-nya, tanpa dipecah
- Saat memutuskan "Tiongkok atau luar negeri", berdiri di sisi yang benar, dan situs Tiongkok tidak memutar
- Semua perangkat di rumah mengikuti aturan yang sama, dan pengaturan jaringan yang diubah di perangkat itu sendiri tidak bisa mengakalinya
- Arahnya berganti otomatis mengikuti wilayah yang dipilih (mengakses Tiongkok dari luar negeri dan mengakses layanan luar negeri dari Tiongkok adalah dua set aturan yang berlawanan)
- Daftarnya diperbarui sendiri, tanpa perlu flash ulang
- Pengaturan diingat: tidak berubah setelah reboot atau sambung ulang; dan kalau sudah dimatikan, tidak diam-diam menyala lagi

## Smart split routing di router kami

| | Cara kerjanya |
|---|---|
| Sakelar | Menyala secara bawaan; memilih wilayah di Tiongkok = arah mengakses Tiongkok dari luar negeri, memilih wilayah luar negeri = arah mengakses layanan luar negeri dari Tiongkok, diterapkan otomatis. Arah mengakses layanan luar negeri dari Tiongkok juga punya kotak centang "Blocked sites only" (hanya situs yang diblokir) ("VPN settings" → smart split routing), tercentang secara bawaan; tanpa centang = situs Tiongkok langsung, sisanya lewat VPN. Firmware yang di-flash sebelum Oktober 2026 belum menampilkan kotak centang ini; hubungi layanan pelanggan untuk mengubahnya dari jauh |
| Daftar | Disusun per "situs utuh": halaman web ikut bersama sumber video, gambar, dan login yang dipakainya |
| Mengakses layanan luar negeri dari Tiongkok | Secara bawaan hanya situs dan layanan yang diblokir yang lewat VPN (berdasarkan daftar situs terblokir yang diperbarui otomatis setiap hari, ditambah layanan seperti Telegram yang tersambung ke alamat tetap); situs Tiongkok, dan situs asing yang memang bisa dibuka dari Tiongkok (situs perusahaan asing, unduhan Apple dan Microsoft, platform game), tersambung langsung tanpa memutar, dengan kecepatan sama seperti tanpa router |
| Perangkat di rumah | Diambil alih seragam; pengaturan jaringan yang diubah di perangkat itu sendiri tetap mengikuti aturan; tidak ada "pintu belakang" untuk melewati router |
| Pembaruan | Daftar dan aturan diperbarui otomatis saat router boot; daftar situs terblokir juga diperbarui otomatis setiap hari |
| Ingatan | Tetap tersimpan setelah sambung ulang atau reboot; kalau dimatikan, tetap mati |
| Jaringan lokal | Printer, NAS, dan kamera tetap diakses langsung seperti biasa |

**Satu-satunya kasus yang butuh bantuan Anda**: kalau HP atau browser menyalakan pengaturan terenkripsi seperti "DNS Pribadi" atau "DNS Aman", perangkat mengenkripsi pencariannya sendiri dan router tidak bisa melihatnya. Kalau sebuah perangkat berperilaku aneh, atau situs yang diblokir tidak terbuka padahal yang lain lancar, matikan dulu pengaturan semacam ini.

## Periksa sendiri

1. Anda di Tiongkok (mengakses layanan luar negeri): Baidu dan Taobao, serta situs asing yang memang bisa dibuka dari Tiongkok seperti unduhan Apple dan Microsoft, kecepatannya normal; situs luar negeri yang diblokir bisa terbuka dan video bisa diputar.
2. Anda di luar negeri (mengakses Tiongkok): pilih episode apa saja di Tencent Video atau iQIYI dan bisa diputar, tanpa pesan "仅限中国大陆" (hanya Tiongkok daratan); situs bank dan belanja lokal tetap jalan seperti biasa.
3. Coba di setiap perangkat, terutama TV dan TV box; untuk yang bermasalah, cek "DNS Pribadi / DNS Aman" dulu, lalu pastikan perangkat itu tersambung ke Wi‑Fi router ini, bukan Wi‑Fi modem.
4. Sebuah situs tidak bisa dibuka dalam mode split routing: pindah sementara ke "Global". Kalau di Global terbuka tapi di split routing tidak, situs itu belum ada di daftar; kirim alamatnya ke layanan pelanggan untuk ditambahkan, dan perubahannya akan sampai lewat pembaruan otomatis. Di Tiongkok, Anda juga bisa menghilangkan centang "Blocked sites only" di bagian smart split routing lalu mencoba lagi; kalau kemudian terbuka, situs itu juga diblokir tetapi belum ada di daftar.

## Tanya jawab

**Apakah saya harus menyalakan smart split routing sendiri?** Tidak. Fitur ini sudah menyala begitu Anda login ke akun dan memilih wilayah.

**Apakah mengakses Tiongkok dari luar negeri dan mengakses layanan luar negeri dari Tiongkok perlu diatur terpisah?** Tidak. Arahnya ditentukan otomatis oleh wilayah yang dipilih.

**Apakah ini memengaruhi printer atau NAS?** Tidak. Perangkat di jaringan rumah tetap diakses langsung seperti biasa.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-09) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-09) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
