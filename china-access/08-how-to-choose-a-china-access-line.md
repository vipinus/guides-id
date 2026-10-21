# 08 · Cara memilih jalur ke Tiongkok: dari mana IP Tiongkok berasal dan di mana yang gratis bermasalah

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Jalur ke Tiongkok hanya melakukan satu hal: membuat permintaan yang Anda kirim dari luar negeri sampai ke Tencent Video, NetEase Cloud Music, atau bank online Anda dari IP **Tiongkok daratan**. Jadi lihat dua hal dulu: apakah exit-nya benar-benar IP Tiongkok daratan, dan apakah ada lalu lintas di perangkat yang melewatinya. Kecepatan, harga, dan klien semuanya urusan belakangan.

## Dari mana IP Tiongkok berasal

Penyedianya harus punya server sendiri di Tiongkok daratan. Penyedia cloud di Tiongkok mewajibkan pendaftaran nama asli untuk menyalakan mesin dan menagih bandwidth sesuai pemakaian, jadi biayanya jauh lebih tinggi daripada mesin di luar negeri. Itulah sebabnya hampir semua layanan ke Tiongkok yang sah berbayar, dan jumlah exit Tiongkok terbatas.

Pengganti yang umum adalah mesin di Hong Kong, Taiwan, atau Jepang yang diaku-aku sebagai "jalur ke Tiongkok". Alamat-alamat ini bisa dipakai untuk sebagian konten Bilibili khusus Hong Kong, Makau, dan Taiwan, tetapi Tencent Video, iQIYI, dan Youku tetap menampilkan pembatasan hak cipta, dan internet banking serta 12306 juga tetap menganggap Anda di luar negeri. **Cara membedakannya: setelah tersambung, cek lokasi terdaftar IP-nya; baru dihitung kalau tertulis "Tiongkok · nama provinsi".**

## Lima hal yang diperiksa sebelum memilih

| Hal | Cara memeriksa | Tanda gagal |
|---|---|---|
| Wilayah exit | Cek lokasi terdaftar IP setelah tersambung | Alamat Hong Kong, Taiwan, Jepang, atau Korea |
| IPv6 dan DNS | Cari "test ipv6" dan buka halaman tesnya | Kolom IPv6 menunjukkan negara tempat Anda berada → situs video tetap memblokir Anda, lihat [Pemecahan masalah 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| Klien | Apakah memakai protokol standar (AnyConnect, OpenVPN, Hiddify) | Hanya ada satu aplikasi khusus, dan begitu diturunkan dari toko aplikasi Anda tidak punya apa-apa lagi |
| Bandwidth | Putar 1080p antara pukul 20.00 dan 23.00 waktu Beijing | Cepat di siang hari, loading terus di malam hari |
| Banyak perangkat dan router | Berapa perangkat per akun, dan apakah router bisa menyambungkan seisi rumah | Setiap perangkat harus dibeli terpisah |

## Kenapa jalur gratis ke Tiongkok sering putus

Masalahnya bukan "gratis", tapi struktur biayanya. Bandwidth exit di Tiongkok daratan dibayar sesuai pemakaian, dan layanan gratis hanya bisa memilih satu dari tiga: menjejalkan beberapa ribu orang ke satu mesin, sehingga semua tersendat di jam sibuk; membatasi kuota dan waktu, sehingga ajakan membayar muncul di tengah jalan; atau mencari uang dengan cara lain, misalnya menyisipkan iklan, mengumpulkan riwayat penjelajahan, atau memakai perangkat Anda sebagai exit untuk orang lain.

Ekstensi browser "ke Tiongkok" yang gratis punya satu titik buta lagi: ekstensi itu hanya mem-proxy permintaan web dari browser, sedangkan pemutar video, aplikasi, dan DNS sistem tidak lewat situ, itulah sebabnya "halaman web terbuka tapi videonya tidak mau diputar" begitu sering terjadi.

Untuk sesekali mencari sesuatu, yang gratis sudah cukup. Untuk mengikuti serial, mendengarkan musik, dan internet banking, waktu yang dihemat jalur berbayar yang stabil jauh lebih berharga daripada biaya langganannya. Klaim dulu uji coba 4 jam, coba sekali di jam sibuk malam, lalu putuskan.

## Cara mahasiswa di luar negeri, pelancong, dan keluarga masing-masing mengaturnya

- **Mahasiswa di luar negeri**: jaringan asrama kebanyakan punya IPv6, jadi pakai klien yang memblokir IPv6; untuk internet banking, CHSI, dan 12306, sambungkan ke jalur Tiongkok hanya saat diperlukan dan putuskan setelah selesai, agar mengurangi pemicu sistem pengendalian risiko akun.
- **Perjalanan singkat**: pasang klien Cisco atau Hiddify di HP dan impor dengan memindai kode QR; begitu mendarat langsung bisa dipakai.
- **Seluruh keluarga yang tinggal lama di luar Tiongkok**: sambungkan satu router yang sudah di-flash firmware ke jalur, dan TV, set-top box, serta HP orang tua tidak perlu diatur apa pun; lihat [Membuka situs video Tiongkok dengan router](../router/06-unlock-chinese-video-with-router.md).

## Tes mandiri 5 menit

1. Sambungkan ke jalur Tiongkok; hasil cek IP menunjukkan sebuah provinsi di Tiongkok daratan.
2. Halaman tes IPv6 menunjukkannya tidak tersedia, atau juga berupa alamat Tiongkok daratan.
3. Buka serial apa pun yang eksklusif untuk Tiongkok di Tencent Video; bisa diputar.
4. Putar lagi 1080p setelah pukul 20.00 waktu Beijing; tidak berulang kali buffering.
5. Ganti ke exit Tiongkok lain dan ulangi tiga langkah pertama.

## Tanya jawab

**Apakah ada bedanya VPN ke Tiongkok dan akselerator ke Tiongkok?** Pada dasarnya tidak. "Akselerator" biasanya aplikasi yang dibuat khusus oleh vendor game atau video dan hanya mencakup aplikasi tertentu; VPN adalah terowongan untuk seluruh perangkat.

**Bisakah menonton Tencent Video dengan node Hong Kong?** Tidak, lisensinya hanya mencakup Tiongkok daratan.

**Berapa perangkat per akun?** Di LeoTun, koneksi bersamaan mengikuti paket: Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat. Router dihitung satu perangkat, dan perangkat di belakangnya tidak dihitung terpisah. Kalau jumlah yang online bersamaan melebihi batas paket, Anda bisa menaikkan paket akun sementara (sisa masa aktif dikonversi senilai menurut harga) lalu kembali lagi sesudahnya.

**Bisakah memakai Clash?** Bisa. LeoTun menyediakan langganan sing-box, langganan Clash, dan link berbagi hysteria2. Dengan Clash Meta, Clash Verge, FlClash, Stash, dan sejenisnya, klik tombol "langganan Clash" lalu tempel URL-nya ke daftar langganan klien; tidak perlu konverter langganan, dan jangan pakai link berbagi. Clash asli dan Clash for Windows tidak bisa dipakai, karena intinya tidak punya hysteria2. Langganan ini secara bawaan mengirim semua lalu lintas kecuali jaringan lokal Anda lewat node, jadi tidak ada yang perlu diubah untuk video Tiongkok; kalau Anda menambah aturan sendiri, jangan atur domain Tiongkok ke "direct" (langsung).

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-08) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-08) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
