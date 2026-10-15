# 06 · Cara mengalirkan NAS Synology atau QNAP lewat jalur

NAS adalah perangkat di rumah yang paling butuh jalur tapi paling jarang diperhatikan: pengunduh harus menjangkau sumber di luar negeri, Docker harus menarik image, Cloud Sync harus menyinkronkan cloud drive luar negeri, dan Plex harus mengambil metadata. NAS tidak bisa menjalankan Hiddify, tetapi Synology dan QNAP sama-sama punya klien OpenVPN bawaan: unduh file .ovpn dari halaman OpenVPN situs ini, impor, dan langsung tersambung, serta tersambung ulang otomatis saat boot. Artikel ini membahas letak menu impor di Synology dan QNAP, opsi penting "Use default gateway", apa yang dilakukan setelah ganti kata sandi, dan kenapa "mengakses NAS dari luar" adalah urusan lain yang butuh jaringan Privat.

## Pertama, bedakan dua hal

Mengalirkan NAS itu sendiri lewat jalur (mengunduh, menarik image, menyinkronkan cloud drive luar negeri): pakai OpenVPN, yang dibahas di artikel ini.

Mengakses NAS dari luar (membuka folder bersama saat dinas, melihat kamera): pakai jaringan Privat (Tailscale), yang memasukkan NAS dan HP Anda ke jaringan privat yang sama; lihat "Melihat kamera dan NAS rumah di Tiongkok dari luar negeri". Serahkan tugas ini ke jaringan Privat: OpenVPN menyambungkan NAS ke jalur kami, sedangkan jaringan Privat menyambungkan Anda ke rumah.

## Synology

1. Login ke situs ini dan, di halaman OpenVPN, klik bendera sebuah wilayah untuk mengunduh file .ovpn wilayah itu.
2. Control Panel → Network → Network Interface → Create → Create VPN profile → OpenVPN (via importing a .ovpn file), lalu masukkan email akun dan kata sandi Anda di situs ini.
3. "Use default gateway" (pakai gateway bawaan): kalau dicentang, semua lalu lintas keluar NAS lewat jalur (unduhan, Docker, dan Cloud Sync semuanya ikut terbantu); kalau tidak dicentang, hanya terowongannya yang dibuat dan lalu lintas keluar tetap lewat jaringan lokal. Hampir selalu sebaiknya dicentang.
4. Centang "Reconnect when the VPN connection is lost" (sambung ulang kalau koneksi VPN terputus) supaya pulih otomatis setelah NAS restart atau jalur tersendat. Sambungkan, lalu coba sekali menarik sesuatu di sebuah paket.

## QNAP

1. Unduh file .ovpn dengan cara yang sama.
2. QVPN Service → VPN Client → Add → OpenVPN, impor filenya, lalu masukkan akun dan kata sandi.
3. Di pengaturan koneksi, centang "Use VPN as the default gateway of the NAS" (jadikan VPN gateway bawaan NAS) dan sambung ulang otomatis, lalu sambungkan.

## Lalu lintas mana yang lewat dan mana yang tidak

- Lewat: tugas BT dan HTTP di Download Station (Synology) / Download Station (QNAP), penarikan image Docker, Cloud Sync yang menyinkronkan Google Drive / Dropbox / OneDrive, pengambilan metadata Plex dan Emby, serta pembaruan Package Center.
- Tidak lewat: lalu lintas saat Anda mengakses NAS di dalam LAN; itu memang di dalam LAN dan tidak terpengaruh.
- Anda di Tiongkok dan ingin situs Tiongkok tersambung langsung: NAS tidak punya skrip split routing, dan begitu OpenVPN tersambung, semua lalu lintas keluar NAS lewat jalur. Kalau sumber unduhan Tiongkok jadi lambat, pakai alamat mirror Tiongkok di tugas unduhan, atau sambungkan jalur hanya saat dibutuhkan.

## Yang perlu diketahui

- File konfigurasi membawa akun Anda, dan kolom kata sandi di NAS tidak berlaku lagi setelah Anda mengganti kata sandi: unduh ulang file .ovpn dan ganti, atau cukup ubah kata sandinya di profil VPN.
- Saat akun kedaluwarsa, NAS terputus; setelah perpanjangan, NAS tersambung ulang otomatis, dan konfigurasinya tidak perlu diganti.
- NAS dihitung satu perangkat dan berbagi jatah online bersamaan dengan perangkat Anda yang lain (Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat).
- Jalurnya berjalan di atas UDP; NAS di internet rumah hampir tidak pernah terkena pembatasan UDP.

## Tanya jawab

**Setelah mencentang "Use default gateway", apakah NAS masih bisa diakses di LAN?** Bisa. Lalu lintas LAN tidak melewati gateway; folder bersama, pemutaran Plex, dan halaman admin semuanya tidak terpengaruh.

**Pemutaran jarak jauh Plex jadi lebih lambat setelah NAS lewat jalur?** Pemutaran jarak jauh Plex memakai lalu lintas keluar NAS, jadi begitu gateway bawaan dicentang, lalu lintasnya memutar lewat jalur. Untuk pemutaran jarak jauh, mengakses NAS lewat jaringan Privat lebih langsung; atau sambungkan OpenVPN hanya saat perlu mengunduh.

**Bisakah hanya Download Station yang lewat jalur?** Synology dan QNAP tidak punya split routing per aplikasi. Untuk kontrol yang lebih rinci, jalankan container unduhan dengan OpenVPN di Docker (seperti qbittorrent + gluetun) dan alirkan hanya container itu lewat jalur.

**Bagaimana dengan NAS yang menjalankan sistem Linux (TrueNAS, Unraid)?** Lakukan dengan cara Linux: paket openvpn ditambah file konfigurasi yang diletakkan di /etc/openvpn/client/; lihat "Cara mengalirkan server Linux dan alat baris perintah lewat jalur".

## Bacaan lanjutan

- [Halaman OpenVPN: unduhan klien dan file konfigurasi](https://www.leotun.com/id/openvpn?utm_source=github&utm_content=overseas-access-06)
- [Cara memakai OpenVPN dan kapan memilihnya](https://www.leotun.com/id/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Melihat kamera dan NAS rumah di Tiongkok dari luar negeri](https://www.leotun.com/id/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Cara mengalirkan server Linux dan alat baris perintah lewat jalur](https://www.leotun.com/id/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-06) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-06) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
