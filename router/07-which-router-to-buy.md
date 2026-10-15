# 07 · Perlukah membeli router, dan cara memilih di antara empat model

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/router?utm_source=github&utm_content=router-07

Cara router menyelesaikan masalah "perangkatnya terlalu banyak, dan sebagian tidak bisa dipasangi klien": VPN diatur sekali di router, lalu TV, konsol game, speaker pintar, dan HP anggota keluarga yang sudah sepuh semuanya otomatis lewat router itu, tanpa memasang apa pun. Yang dibutuhkan hanya router yang bisa di-flash dan sepuluh menit untuk flash. **Akun Pribadi, Keluarga, dan Perusahaan semuanya bisa memakai router.**

## Kapan perlu dan kapan tidak

| Perlu | Tidak perlu |
|---|---|
| Ada perangkat di rumah yang tidak bisa dipasangi klien, seperti TV box, konsol game, Apple TV, atau speaker pintar | Anda hanya punya satu HP dan satu komputer dan lebih sering bepergian untuk kerja; memasang klien lebih ringkas |
| Anggota keluarga banyak dan Anda tidak mau mengajari mereka satu per satu | Anda tinggal di asrama atau kos dan tidak memegang kendali atas jaringannya |
| Ada perangkat yang harus tersambung 24 jam sehari (NAS, unggahan kamera) | Router utama Anda adalah modem yang dikunci operator dan tidak bisa ditambah router kedua; pakai router portabel sebagai jalan tengah |
| Kantor di Tiongkok atau satu keluarga yang rutin mengakses layanan luar negeri dari Tiongkok, dengan split routing di router dan perangkat tidak perlu tahu apa-apa | |

## Flash firmware sendiri atau beli unit siap pakai

Kedua cara akhirnya menjalankan firmware yang sama. Bedanya siapa yang melakukan flash dan siapa yang bertanggung jawab kalau ada masalah.

- **Flash sendiri**: Anda sudah punya router yang didukung OpenWrt (lebih dari 1000 model). Firmware dikompilasi online di situs, dan link-nya Anda terima lewat email dalam 3 sampai 5 menit; lalu ikuti [02 · Flash firmware sendiri](02-flash-firmware-yourself.md) langkah demi langkah (ada videonya). Cocok untuk yang terbiasa mengatur hal teknis sendiri dan ingin menghemat biaya perangkat.
- **Beli unit siap pakai**: kami mengirim GL.iNet yang firmware-nya sudah di-flash; tiga langkah setelah dikeluarkan dari kotak ada di [01](01-plug-and-play-router.md). Cocok untuk yang tidak mau repot, atau untuk anggota keluarga yang tidak paham teknis.

Dengan cara mana pun, firmware memperbarui komponennya sendiri tanpa perlu flash ulang; dan saat alamat jalur berubah, konfigurasinya juga tidak perlu diubah.

## Empat router, disesuaikan dengan cara pakai Anda

| Model | Jenis | Harga | Termasuk | Apa itu | Paling cocok untuk |
|---|---|---|---|---|---|
| GL-MT300N-V2 | Mini | $200 | Layanan 12 bulan | Seukuran telapak tangan dan bertenaga USB (bisa jalan dengan power bank); hanya Wi‑Fi 2,4 GHz, port 100 Mbps | Satu orang yang bepergian: LAN hotel atau Wi‑Fi hotel, HP dan laptop untuk browsing dan menonton 1080p. Tidak cocok jadi router utama di rumah |
| **GL-MT3000** | Portabel | $300 | Layanan 24 bulan | Wi‑Fi 6 dual-band dengan port 2.5G, sedikit lebih besar dari telapak tangan | Router utama untuk rumah tangga kecil (TV, streaming box, beberapa HP dan komputer), dan cukup kecil untuk masuk ransel |
| GL-MT6000 | Desktop | $400 | Layanan 24 bulan | Dua port 2.5G plus empat port gigabit, antena eksternal, prosesor paling bertenaga | Rumah besar, banyak perangkat (selusin atau lebih), internet di atas 1 Gbps, 4K dan game konsol, atau kantor kecil. Diam di satu tempat sebagai satu-satunya router |
| GL-XE3000 | Mobile | $400 | Layanan 24 bulan | 5G/4G dan baterai bawaan; dengan kartu SIM jadi jaringan mandiri, dan juga bisa menerima kabel LAN | Tempat tanpa internet kabel: campervan, lokasi proyek, pameran, sewa jangka pendek; atau cadangan untuk jaringan rumah |

Bulan yang termasuk dihitung menurut paket Pribadi; Keluarga mendapat separuhnya dan Perusahaan seperempatnya, nilainya sama. Gratis ongkos kirim ke seluruh dunia, biasanya 3–14 hari, bisa dikembalikan dalam 30 hari.

### Pilihan cepat menurut situasi

- Bepergian sendiri, menginap di hotel, anggaran terbatas → GL-MT300N-V2
- Apartemen atau rumah tangga kecil yang TV dan streaming box-nya butuh video Tiongkok atau luar negeri → GL-MT3000
- Lebih sering di rumah, tapi sesekali ingin dibawa bepergian → GL-MT3000
- Rumah besar, banyak perangkat, internet di atas 1 Gbps, atau kantor bersama → GL-MT6000
- Tidak ada internet kabel, atau Anda lebih sering di jalan → GL-XE3000
- Mengatur satu untuk orang tua yang tidak paham teknis → GL-MT3000, beli yang sudah terpasang firmware: colokkan dan langsung jalan

## Kenapa GL-MT3000 jadi rekomendasi pertama kami

- **Satu unit, dua peran.** Cukup bertenaga untuk jadi router utama rumah tangga kecil, cukup kecil untuk dibawa bepergian. Di antara keempatnya, hanya ini yang bisa keduanya.
- **Tidak cepat ketinggalan zaman.** Wi‑Fi 6 dan port 2.5G masih menyisakan ruang di atas kecepatan kebanyakan internet rumah. Versi mini hanya punya Wi‑Fi 2,4 GHz dan port 100 Mbps, yang jadi titik sempit di rumah.
- **Hitungan harganya masuk.** $300 dengan layanan paket Pribadi 24 bulan, dibandingkan $200 dengan 12 bulan untuk versi mini. Kalau layanan yang termasuk ikut dihitung, tambahan $100 itu membeli perangkat yang jelas lebih baik plus satu tahun lagi.
- **Model ini yang paling kami kenal.** Unit uji kami sendiri model ini, firmware baru diperiksa di sini lebih dulu, dan [video tutorial flash](02-flash-firmware-yourself.md) memakainya. Kalau Anda menemui masalah, kami punya perangkat yang sama di meja untuk dibandingkan.

Kapan tidak memilihnya: untuk rumah besar, banyak perangkat, atau internet di atas 1 Gbps, langsung pilih GL-MT6000; tanpa internet kabel, GL-XE3000; kalau hanya untuk satu orang yang bepergian dan harga paling penting, GL-MT300N-V2 sudah cukup.

## Tiga masalah paling umum setelah mulai dipakai

- **Sinyal Wi‑Fi lemah, hanya 20 dBm**: firmware mengatur daya nirkabel otomatis sesuai aturan negara tempat Anda berada, dan baru beralih ke level negara Anda setelah router pernah online sekali. Tepat setelah flash, colokkan kabel LAN dulu.
- **Situs Tiongkok jadi lambat** (saat Anda di Tiongkok): split routing mati dan semua lalu lintas lewat jalur. Kembalikan mode ke split routing: saat mengakses layanan luar negeri dari Tiongkok, secara bawaan hanya situs yang diblokir yang lewat jalur, sedangkan situs Tiongkok dan situs asing yang memang bisa dibuka dari Tiongkok tersambung langsung.
- **Di Tiongkok, sebuah situs asing tidak mau terbuka**: di "VPN settings" (pengaturan VPN), bagian smart split routing, hilangkan centang "Blocked sites only" (hanya situs yang diblokir), atau pindah sementara ke "Global", lalu coba lagi; kalau kemudian terbuka, situs itu diblokir tetapi belum ada di daftar, jadi kirim alamatnya ke layanan pelanggan.
- **Di luar negeri dan ingin konten Tiongkok**: pilih Reverse Split (split terbalik). Split terbalik membalik arahnya: hanya IP Tiongkok daratan yang lewat jalur ke Tiongkok, dan semua situs lain memakai internet lokal Anda secara langsung. Video, musik, dan aplikasi Tiongkok melihat alamat Tiongkok, sementara situs lokal dan streaming tidak memutar. Firmware memilih arahnya sesuai lokasi router, jadi jarang perlu diubah. Lihat [03 · Split routing di router](03-router-split-routing.md).
- **Satu perangkat tidak lewat VPN, atau situs yang diblokir tidak terbuka padahal yang lain lancar**: perangkat itu memakai DNS pribadinya sendiri ("DNS Pribadi" di Android, DNS aman di browser), sehingga router tidak bisa melihat situs mana yang dicari; matikan pengaturan itu.

## Tanya jawab

**Apakah router dihitung satu perangkat?** Router memakai satu jatah di akun (menurut paket: Pribadi 2, Keluarga 4, Perusahaan 8 perangkat online bersamaan), dan perangkat di belakangnya tidak dihitung terpisah.

**Bisakah dipakai menonton video dari Tiongkok saat di luar negeri?** Bisa, pilih wilayah Tiongkok untuk jalurnya. Router memasukkan seluruh jaringan lokal ke VPN, dan IPv6 serta DNS perangkat tidak bisa keluar sendiri, jadi pesan "pembatasan hak cipta" lebih jarang muncul dibandingkan HP yang tersambung sendiri. Lihat [06](06-unlock-chinese-video-with-router.md).

**Apakah firmware-nya punya pintu belakang?** Firmware dikompilasi dari OpenWrt, hanya ditambah komponen yang menyambung ke VPN dan aturan split routing; VPN hanya mencatat durasi koneksi dan total kuota untuk penagihan, dan tidak mencatat apa yang Anda kunjungi.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-07) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-07) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
