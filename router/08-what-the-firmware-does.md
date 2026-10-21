# 08 · Setelah firmware terpasang: apa yang dikerjakannya sendiri, dan beberapa sakelar yang perlu Anda tahu

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/router-firmware?utm_source=github&utm_content=router-08

Setelah flash firmware situs ini atau membeli unit yang sudah terpasang, yang perlu Anda lakukan hanya login ke akun di halaman admin. Artikel ini membahas hal-hal yang **dikerjakan firmware sendiri** dan beberapa sakelar yang mungkin perlu Anda sentuh; untuk memulai lihat [01](01-plug-and-play-router.md), untuk split routing lihat [03](03-router-split-routing.md), dan untuk menautkan serta mengganti router lihat [05](05-mac-binding-and-replacing.md).

## Yang dikerjakannya sendiri

| Apa | Cara kerjanya | Yang perlu Anda lakukan |
|---|---|---|
| Pembaruan komponen dan daftar split routing | Memeriksa saat boot dan mengunduh pembaruan, yang **berlaku pada boot berikutnya**; daftar situs terblokir untuk mengakses layanan luar negeri dari Tiongkok juga diperbarui otomatis setiap hari | Tidak ada; alamat jalur yang berubah dan situs yang ditambahkan ke daftar diambil otomatis |
| Kode negara Wi‑Fi | Mengenali negara tempatnya berada setelah online, lalu mengatur daya nirkabel dan kanal secara otomatis | Tepat setelah flash, **pasang kabel LAN dulu** supaya router online sekali; sinyal yang lebih lemah sebelum pernah online itu wajar |
| Penanganan masa aktif habis | Saat akun kedaluwarsa, berhenti lewat VPN; jaringan lokal tetap berjalan seperti biasa | Pulih otomatis setelah Anda memperpanjang, tanpa perlu login ulang |
| Penautan router | Login pertama mencatat router ini pada akun | Lepas tautan di situs sebelum ganti router |

Hanya pembaruan versi besar seluruh firmware yang butuh flash file sysupgrade. Itu hanya terjadi beberapa kali setahun, dan situs akan memberi tahu Anda.

## Yang mungkin perlu Anda sentuh

- **Mode split routing**: Split routing (bawaan) / Global / Direct (langsung). Kalau sebuah situs tidak bisa dibuka, pindah dulu ke Global untuk memastikan: kalau di Global bisa terbuka, situs itu belum ada di daftar, jadi kirim alamatnya ke layanan pelanggan untuk ditambahkan; kalau di Global pun tidak bisa, masalahnya ada di situs itu sendiri.
- **Wilayah**: dipilih di halaman admin. Pilih wilayah Tiongkok untuk menonton konten Tiongkok dari luar negeri, dan wilayah luar negeri untuk mengakses layanan luar negeri dari Tiongkok.
- **Blocked sites only** (hanya situs yang diblokir): kotak centang di "VPN settings" (pengaturan VPN), di bagian smart split routing, tercentang secara bawaan. Hanya berlaku untuk arah mengakses layanan luar negeri dari Tiongkok (Anda berada di Tiongkok dan memilih wilayah luar negeri). Kalau dicentang, hanya situs dan layanan yang diblokir yang lewat VPN (berdasarkan daftar situs terblokir yang diperbarui otomatis setiap hari, ditambah layanan seperti Telegram yang tersambung ke alamat tetap); situs Tiongkok, dan situs asing yang memang bisa dibuka dari Tiongkok (situs perusahaan asing, unduhan Apple dan Microsoft, platform game, dan sejenisnya) tersambung langsung tanpa memutar. Hilangkan centangnya untuk kembali ke perilaku sebelumnya: situs Tiongkok langsung, sisanya lewat VPN. Kalau sebuah situs asing tidak bisa dibuka selama Anda di Tiongkok, hilangkan centangnya (atau pindah sementara ke Global) lalu coba lagi; kalau kemudian terbuka, situs itu diblokir tetapi belum ada di daftar, jadi kirim alamatnya ke layanan pelanggan. Firmware yang di-flash sebelum Oktober 2026 belum menampilkan kotak centang ini (bawaan baru sudah berlaku lewat pembaruan otomatis); untuk mengubahnya, hubungi layanan pelanggan, yang bisa melakukannya dari jauh. Arah mengakses Tiongkok dari luar negeri tidak terpengaruh oleh sakelar ini.
- **Pilih jalur tercepat secara otomatis**: letaknya di bawah wilayah, mati secara bawaan, dan disarankan kalau kualitas jaringan buruk.

  | | Mati (bawaan) | Nyala |
  |---|---|---|
  | Jalur mana yang dipakai | Selalu wilayah yang Anda pilih | Otomatis memilih jalur dengan latensi terendah dan sedikit packet loss di antara jalur yang tersedia, lalu menguji ulang secara berkala dan berpindah otomatis kalau memburuk |
  | Negara exit | Wilayah yang dipilih | Kalau memilih wilayah Tiongkok: hanya memilih di antara jalur di Tiongkok, dan exit tetap di Tiongkok; kalau memilih wilayah luar negeri: memilih di antara semua jalur luar negeri, dan **negara exit bisa berbeda dari wilayah yang dipilih** (misalnya Anda memilih Jepang tetapi sebenarnya keluar dari Singapura) |
  | Cocok untuk | Situasi yang butuh negara tetap: menonton layanan streaming negara tertentu, bank dan akun yang peka terhadap wilayah | Jaringan rumah yang tidak stabil atau wilayah yang sering tersendat, kalau Anda hanya ingin cepat dan tidak peduli keluar dari negara mana |

  Saat Anda mengubah sakelar ini, halaman admin menampilkan pesan bahwa pemilihan otomatis sedang dialihkan dan mengunci halaman sampai selesai. Jaringan putus sebentar selama itu, dan itu wajar. "Exit saat ini" di halaman admin menunjukkan jalur mana yang sebenarnya dipakai.
- **Kata sandi admin dan kata sandi Wi‑Fi**: nilai pabriknya diketahui umum; ganti begitu login pertama kali.

## TV, TV box, dan perangkat anggota keluarga lansia

- Cukup sambungkan ke Wi‑Fi router ini atau lewat kabel, dan aplikasi edisi Tiongkok daratan langsung bisa memutar; edisi internasional (iQIYI, WeTV) punya koleksi konten berbeda, jadi pasang edisi Tiongkok daratan.
- Perangkat sudah tersambung tetapi tidak lewat VPN, atau situs yang diblokir tidak bisa dibuka sementara yang lain lancar: kemungkinan besar perangkat itu memakai DNS pribadinya sendiri (Android "DNS Pribadi", DNS aman di browser), sehingga router tidak bisa melihat situs mana yang dicari; matikan pengaturan itu.
- Anda ingin perangkat tertentu selalu tersambung langsung (komputer kantor yang perlu tersambung ke VPN perusahaan): sambungkan perangkat itu ke Wi‑Fi router di atasnya atau modem.

## Tanya jawab

**Bisakah paket Pribadi memakai router?** Bisa. Pribadi, Keluarga, dan Perusahaan semuanya mendukung router, tanpa perlu ganti paket.

**Berapa jatah perangkat yang dipakai router?** Satu; perangkat di belakangnya tidak dihitung.

**Apakah firmware-nya punya pintu belakang?** Firmware dikompilasi dari OpenWrt, hanya ditambah komponen yang tersambung ke VPN dan aturan split routing; VPN hanya mencatat durasi koneksi dan total lalu lintas untuk penagihan.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-08) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-08) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), berlaku jangka panjang
