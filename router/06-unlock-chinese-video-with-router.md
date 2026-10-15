# 06 · Membuka situs video Tiongkok dari luar negeri dengan router

## Kenapa pakai router, bukan memasang klien di tiap perangkat

- TV, set-top box, proyektor, dan konsol game tidak bisa dipasangi klien, jadi router adalah satu-satunya cara.
- Kalau orang di rumah banyak, mengatur setiap perangkat milik setiap orang tidak realistis; atur router sekali saja, dan pengaturannya langsung berlaku begitu perangkat tersambung ke Wi-Fi.
- Split routing dikerjakan di router, jadi situs web lokal dan perangkat lokal tetap tersambung langsung; hanya domain video Tiongkok yang lewat jalur ke Tiongkok, dan kecepatan tidak terpengaruh.

## Yang Anda butuhkan

| Item | Keterangan |
|---|---|
| Router yang didukung | Yang sudah terpasang firmware langsung bisa dipakai; kalau Anda flash sendiri, lihat [Cara flash firmware](02-flash-firmware-yourself.md) |
| Akun | Akun Pribadi, Keluarga, dan Perusahaan semuanya mendukung fitur router. Setelah mendaftar, klaim dulu uji coba gratis untuk mencoba seluruh prosesnya: akun baru memakai paket Pribadi, dengan uji coba 24 jam |
| Jaringan di atasnya | Modem atau router yang sudah ada di rumah; router baru dipasang di belakangnya |

## Selesai dalam lima langkah

1. Sambungkan port WAN router baru ke jaringan di atasnya, colokkan listrik, dan tunggu satu menit.
2. Sambungkan HP ke Wi-Fi router baru, buka alamat admin `http://192.168.11.1`, lalu login ke akun Anda.
3. Pilih mode **Split routing**. Domain video Tiongkok ada di daftar dan otomatis lewat jalur ke Tiongkok.
4. Pindahkan TV dan set-top box ke Wi-Fi ini, atau sambungkan dengan kabel ke port LAN router baru.
5. Buka iQIYI, Tencent Video, atau Yangshipin (CCTV); kalau bisa diputar dengan normal, selesai.

## Daftarnya terbuka untuk umum

Domain video di daftar split routing dikelola di repositori publik: <https://github.com/vipinus/openwrt-2026-video-domains>. Kalau ada platform yang tidak mau diputar, Anda bisa memeriksa apakah domainnya ada di daftar, dan mengusulkannya kalau belum ada.

## Kualitas gambar dan bandwidth

1080p butuh 5 Mbps yang stabil, dan 4K butuh 25 Mbps atau lebih. Kalau tersendat di jam sibuk malam hari, pilih wilayah berlampu hijau; kalau masih tersendat, penyebab biasanya internet rumah setempat. Untuk wilayah titik masuk, pilih yang dekat dengan Anda dan punya rute bagus ke Tiongkok daratan; coba beberapa, lalu nilai dari tersendat atau tidaknya pemutaran.

## Tanya jawab

- **Bisa diputar di HP, tapi tidak di TV**: TV masih tersambung ke Wi-Fi lama, atau aplikasi di TV versi internasional.
- **Sebagian platform bisa diputar, sebagian tidak**: domain platform itu belum ada di daftar split routing. Pindah sementara ke "Global" untuk memastikan, lalu usulkan ke repositori daftarnya.
- **Seluruh rumah jadi lambat dengan router lama**: CPU-nya tidak sanggup mengolah lalu lintas terenkripsi; ganti ke model yang performanya lebih baik, lihat [Memulai dengan router yang sudah terpasang firmware](01-plug-and-play-router.md).

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-06) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-06) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
