# 04 · OpenVPN: unduh profil .ovpn, impor, lalu sambungkan; bisa dipakai di router, NAS, dan Linux

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN adalah protokol open source yang sudah lama dipakai, dan hampir semua sistem operasi, firmware router, dan NAS punya klien untuknya. File profil LeoTun sudah berisi akun, kata sandi, dan bahan enkripsi Anda, jadi begitu diimpor langsung bisa tersambung. Untuk pemakaian sehari-hari di HP dan komputer, AnyConnect atau Hiddify lebih praktis; nilai OpenVPN ada di **tempat yang hanya menerima OpenVPN**: router OpenWrt, NAS Synology / QNAP, server Linux, dan perangkat lama.

## Tiga langkah

1. Dari tabel di [halaman OpenVPN di situs](https://www.leotun.com/id/openvpn?utm_source=github&utm_content=client-04), pasang klien untuk sistem Anda (semua platform punya OpenVPN Connect resmi; di Windows bisa juga OpenVPN GUI, dan di macOS Tunnelblick).
2. Setelah login, **klik bendera wilayah** untuk mengunduh .ovpn wilayah itu. Satu file per wilayah.
3. Buka file-nya di klien lalu sambungkan.

| Platform | Keterangan |
|---|---|
| Windows / macOS / Android / iOS | Profil sudah berisi akun dan kata sandi; impor lalu sambungkan |
| Linux | Pengaturan VPN sistem → impor dari file, lalu masukkan email dan kata sandi situs saat pertama kali tersambung; baris perintah `openvpn --config file`; untuk jalan saat boot, letakkan di `/etc/openvpn/client/` |
| Router OpenWrt | Pasang luci-app-openvpn, unggah .ovpn, lalu aktifkan; tidak perlu kalau firmware situs ini sudah terpasang |
| NAS Synology | Control Panel → Network → Network Interface → Create → VPN → OpenVPN (impor .ovpn); untuk mengalirkan lalu lintas keluar NAS lewat jalur, centang "Use default gateway on remote network" (pakai gateway default di jaringan jarak jauh) |
| NAS QNAP | QVPN → VPN Client → Add → OpenVPN, lalu impor |

## Pengguna di Tiongkok: situs Tiongkok tersambung langsung

Setelah tersambung, lalu lintas ke situs Tiongkok jadi memutar. Situs menyediakan "alat rute langsung Tiongkok": klik dua kali untuk menjalankannya, maka IP Tiongkok tersambung langsung sementara sisanya lewat jalur. Alat ini bekerja dengan Cisco maupun OpenVPN. Pengguna di luar Tiongkok tidak perlu memakainya.

## Kalau tidak tersambung, periksa dengan urutan ini

| Kata kunci di log / gejala | Penyebab | Yang harus dilakukan |
|---|---|---|
| AUTH_FAILED | Akun atau kata sandi salah, atau sudah kedaluwarsa | Login ke situs dan cek tanggal berakhirnya; kalau Anda mengganti kata sandi, unduh ulang profilnya |
| UDP timeout dulu, lalu tersambung lewat TCP | Jaringan saat ini membatasi UDP, dan otomatis beralih ke TCP | Bisa dipakai tapi lebih lambat; kalau terlalu lambat, ganti jaringan atau pakai AnyConnect |
| UDP dan TCP sama-sama melaporkan TLS handshake failed / key negotiation failed | Jalur jaringan ke server terputus | Ganti wilayah atau jaringan |
| Error saat impor | Kliennya terlalu lama (sebelum OpenVPN 2.5) | Perbarui klien |
| Tiba-tiba putus saat tersambung | Akun kedaluwarsa dan server memutus koneksi | Perpanjang lalu sambungkan lagi; profil tidak perlu diganti |

## UDP atau TCP

Keduanya tersedia dan Anda tidak perlu memilih. UDP ada di urutan pertama dalam profil, jadi klien mencoba UDP dulu; kalau UDP dibatasi atau tidak bisa tersambung, klien beralih ke TCP secara otomatis setelah beberapa detik. UDP latensinya lebih rendah dan lebih cepat; TCP hanya cadangan dan terasa jauh lebih lambat untuk koneksi lintas negara. Di jaringan yang selalu membatasi UDP (sebagian jaringan kampus dan kantor), kami sarankan langsung memakai AnyConnect.

> Profil yang diunduh sebelum 15 September 2026 hanya berisi UDP; unduh ulang kalau ingin peralihan otomatis.

## Keamanan

File profil berisi akun dan kata sandi Anda, jadi nilainya sama dengan akun itu sendiri; jangan diberikan ke orang lain. Kalau bocor, ganti kata sandi di situs dan file lama langsung tidak berlaku. Handshake-nya sendiri juga terenkripsi: tanpa kunci di profil, handshake bahkan tidak bisa dimulai, dan server tidak terlihat oleh pemindai.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-04) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-04) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
