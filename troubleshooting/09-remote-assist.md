# 09 · Minta dukungan memeriksa komputer dan router Anda dari jarak jauh

Ada masalah yang tetap tidak jelas meski sudah belasan kali bertukar tangkapan layar di grup, padahal dukungan bisa menemukannya dalam dua menit dengan melihat layarnya langsung. Artikel ini membahas kapan bantuan jarak jauh layak diminta, software apa yang dipakai di komputer, cara mengimpor konfigurasi server situs ini, cara menyerahkan data koneksi ke dukungan dengan aman, apa yang tetap Anda kendalikan selama sesi, cara mencabut akses setelahnya, dan apa yang perlu Anda lakukan untuk router yang memakai firmware situs ini.

## Kapan bantuan jarak jauh layak diminta

- Anda sudah menjalani [01 · Daftar periksa: tidak bisa tersambung, lambat, dan sering putus](01-cannot-connect-slow-drops.md) sekali, dan sudah bertanya dengan menyebutkan cara koneksi, wilayah, teks error persisnya atau tangkapan layar, serta waktu masalahnya terjadi, tapi tetap belum terselesaikan.
- Anda sendiri tidak bisa menjelaskan langkah-langkahnya: pengaturannya tersembunyi jauh, Anda tidak bisa membaca bahasa sistemnya, atau pesan error-nya muncul terlalu cepat untuk ditangkap.
- Anda sedang membantu komputer anggota keluarga, tidak berada di sampingnya, dan tidak bisa menjelaskannya lewat telepon.

Dalam kasus berikut **jangan pakai bantuan jarak jauh**; berkomunikasilah lewat teks di grup:

- Komputer yang dikelola terpusat oleh kantor. Kebijakan grup biasanya melarang menjalankan program seperti ini, dan bisa melanggar aturan perusahaan.

## Software yang dipakai: RustDesk

Situs web merekomendasikan [RustDesk](https://rustdesk.com): open source (AGPL-3.0), jadi kodenya bisa diaudit siapa saja; dan kapan sesi dimulai dan kapan berakhir, keduanya ditentukan oleh klik Anda sendiri. Tersedia untuk Windows, macOS, Linux, Android, dan iOS (iPhone / iPad hanya bisa mengendalikan perangkat lain, tidak bisa dikendalikan).

Unduh dari [halaman kontak](https://www.leotun.com/id/contact#downloads) di "Pusat unduhan" → "Bantuan jarak jauh", atau dari situs resmi rustdesk.com. Jangan pakai situs unduhan pihak ketiga dari hasil pencarian. Kedua pihak dalam sesi perlu memasangnya.

## Izin yang diberikan setelah memasang

| Sistem | Yang dilakukan |
|---|---|
| macOS | Di "Pengaturan Sistem → Privasi & Keamanan" (System Settings → Privacy & Security), centang RustDesk di "Perekaman Layar" (Screen Recording) dan "Aksesibilitas" (Accessibility), lalu tutup sepenuhnya dan buka lagi. Kalau hanya salah satu yang diberi, hasilnya "bisa melihat tapi tidak bisa mengendalikan" atau layar hitam sama sekali. Kalau muncul pesan "rusak", lihat [06](06-antivirus-false-positive.md) |
| Android | Saat dibantu, ketuk "Start service" (mulai layanan) di RustDesk dan izinkan perekaman layar; agar dukungan bisa mengetuk layar Anda, nyalakan juga RustDesk di "Aksesibilitas" sistem |
| Windows / Linux | Biasanya langsung jalan setelah dipasang |

## Menyambung ke server kami sendiri

Bantuan jarak jauh berjalan lewat server RustDesk milik situs ini, yang juga tersambung andal dari dalam Tiongkok. **Kedua pihak dalam sesi perlu mengimpornya sekali**; kedua ujung hanya bisa saling menemukan kalau memakai server yang sama:

1. Login ke situs web dulu, lalu di [halaman kontak](https://www.leotun.com/id/contact#downloads) buka "Pusat unduhan" → "Bantuan jarak jauh" → bagian konfigurasi server kami, lalu klik tombol salin.
2. Di komputer, buka RustDesk "Settings → Network" (pengaturan → jaringan), klik "Unlock network settings" (buka kunci pengaturan jaringan) dulu, lalu klik "ID/Relay server"; di HP letaknya di "Settings → ID/Relay server".
3. Di jendela yang muncul, klik ikon papan klip di kanan atas (di HP ketuk "Import"). Konfigurasinya terisi otomatis; klik "OK".

**Jangan tempel konfigurasinya ke kolom isian**; hasilnya justru "failed to lookup address". Konfigurasi ini hanya untuk dipakai dengan akun di situs ini. Jangan diteruskan ke orang lain.

## Menyerahkan ID dan kata sandi sekali pakai ke dukungan

Buka RustDesk, dan layar utamanya menampilkan ID perangkat ini dan kata sandi sekali pakai. Sebelum menyerahkannya, pastikan tiga hal:

1. **Anda yang bertanya lebih dulu.** Anda sudah menjelaskan masalahnya di grup resmi yang tercantum di [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-09), dan dukungan memutuskan bantuan jarak jauh diperlukan, baru lanjut ke langkah berikutnya. Staf dukungan kami tidak akan mendekati Anda duluan, menyuruh Anda memasang software jarak jauh, atau meminta kode koneksi; siapa pun yang datang meminta, verifikasi dulu di grup resmi.
2. **Kirim hanya lewat jalur dukungan resmi**: kontak dukungan manusia yang tercantum di halaman kontak. Chat pribadi di luar grup yang mengaku "dukungan LeoTun" bukan kami.
3. **Jangan kirim di grup.** Grup bisa dilihat banyak orang; ID ditambah kata sandi sama saja dengan menempelkan kunci komputer Anda di pintu.

## Selama sesi

- Sepanjang sesi Anda bisa melihat apa yang dikerjakan di layar, dan bisa memutus sambungan di jendela RustDesk kapan saja.
- Kalau ada yang meminta Anda meminimalkan jendela, meninggalkan komputer, atau membuka internet banking atau aplikasi pembayaran, **segera putuskan sambungan**.
- Saat kata sandi akun perlu dimasukkan, ketik sendiri; jangan bacakan ke dukungan.

## Mencabut akses setelahnya

1. Klik putuskan di jendela RustDesk dan pastikan pihak lain sudah offline.
2. Perbarui kata sandi sekali pakai agar yang tadi Anda kirim tidak berlaku lagi.
3. Tutup RustDesk. Kalau tidak dibutuhkan lagi, Anda bisa langsung menghapusnya dan mengunduh lagi lain kali.

## Router: apa yang perlu Anda lakukan

Untuk router yang memakai firmware situs ini, Anda tidak perlu memasang software jarak jauh apa pun di router maupun komputer, dan tidak perlu mengirim kata sandi admin router ke dukungan. Yang perlu Anda lakukan hanya:

- Biarkan router menyala dengan kabel jaringan tercolok, dan akun tetap login di router.
- Sampaikan akun, model router, dan gejalanya ke dukungan di grup resmi; sisanya diurus dukungan.
- Jangan berulang kali mencabut dan menyalakan ulang router saat sedang dikerjakan, kecuali diminta dukungan.

## Tanya jawab

**Apakah dukungan akan mengirim pesan pribadi duluan dan menyuruh saya memasang software jarak jauh?** Tidak. Setiap kali ada yang mendekati Anda tanpa diminta, selalu verifikasi identitasnya dulu di grup resmi.

**Muncul "failed to lookup address" saat mengimpor?** Kemungkinan besar konfigurasinya ditempel ke kolom isian. Kosongkan kolom-kolom itu, kembali ke jendela "ID/Relay server", lalu impor dengan mengklik ikon papan klip di kanan atas.

**Sudah tersambung di macOS tapi layarnya hitam, atau bisa melihat tapi tidak bisa mengendalikan?** Izinnya belum lengkap. Centang "Perekaman Layar" dan "Aksesibilitas" sekaligus, lalu tutup sepenuhnya dan buka lagi.

**Apa lagi yang perlu dilakukan setelah sesi selesai?** Putuskan sambungan, perbarui kata sandi sekali pakai, tutup programnya. Setelah tiga langkah ini, pihak lain tidak akan bisa tersambung lagi.

## Bacaan lanjutan

- [Cara memakai bantuan jarak jauh RustDesk (panduan di situs web)](https://www.leotun.com/id/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Kalau Mac Anda bilang aplikasi "rusak"](https://www.leotun.com/id/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [Halaman kontak: grup dukungan, dukungan manusia, dan email](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · Cara menghubungi kami, dan cara agar tidak putus kontak](05-how-to-reach-us.md)
- [01 · Daftar periksa: tidak bisa tersambung, lambat, dan sering putus](01-cannot-connect-slow-drops.md)

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=troubleshooting-09) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-09) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
