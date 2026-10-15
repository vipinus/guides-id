# 07 · Melihat kamera rumah di Tiongkok dari luar negeri

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/home-camera?utm_source=github&utm_content=china-access-07

## Tiga kasus, masing-masing dengan solusi berbeda

| Jenis sistem kamera di rumah Anda | Bisakah dilihat langsung dari luar negeri | Solusi |
|---|---|---|
| Aplikasi vendor dengan cloud (EZVIZ, Xiaomi, TP-Link, Imou, dan lainnya) | Umumnya bisa; di sebagian wilayah dibatasi atau sangat lambat | Pindah ke IP Tiongkok dan pakai edisi Tiongkok aplikasinya |
| Perekam video jaringan (NVR) yang hanya bisa dilihat di LAN rumah | Tidak bisa, tidak ada titik masuk publik | Masukkan satu perangkat di rumah ke jaringan privat, lalu biarkan perangkat di luar negeri masuk ke LAN rumah lewat jaringan privat itu |
| Aplikasi vendor, tapi versi di toko aplikasi luar negeri adalah sistem terpisah dengan server sendiri | Akunnya tidak cocok | Pasang edisi Tiongkok aplikasinya dan pakai akun Tiongkok |

## Kasus pertama: cloud vendor

Kamera mengirim gambar ke server vendor, lalu aplikasi mengambilnya dari server. Jalur dari jaringan luar negeri ke server vendor Tiongkok buruk, sehingga gejalanya loading lambat dan streaming terputus-putus. Setelah pindah ke IP Tiongkok, Anda memakai jalur di dalam Tiongkok, dan hasilnya jauh lebih baik.

Perhatikan bahwa aplikasi bernama sama di toko aplikasi luar negeri biasanya tersambung ke server luar negeri, dan akunnya tidak bisa dipakai bergantian. Pasang edisi Tiongkok aplikasinya; untuk masalah wilayah toko aplikasi, lihat [panduan pemecahan masalah dan instalasi](../client/06-ios-app-store.md).

## Kasus kedua: perekamnya hanya ada di LAN

Ini kasus yang paling umum dan juga yang paling sulit. NVR tidak punya IP publik, dan port forwarding umumnya tidak bisa dilakukan di internet rumah di Tiongkok. Pendekatan yang bisa dipakai adalah **jaringan privat**:

1. Siapkan satu perangkat yang selalu menyala di rumah; komputer, NAS, Raspberry Pi, atau router yang didukung semuanya bisa. Pasang klien jaringan privat di perangkat itu, masukkan ke jaringan privat Anda, lalu nyalakan "bagikan LAN".
2. Masukkan juga HP atau komputer Anda di luar negeri ke jaringan privat yang sama.
3. Sejak itu perangkat di luar negeri bisa langsung menjangkau NVR lewat alamat LAN rumah, persis seperti saat Anda di rumah.

Cara koneksi "Privat" LeoTun adalah jaringan privat semacam ini. Jumlah perangkat yang bisa dipasang dengan satu akun tidak dibatasi, dan jumlah yang online bersamaan mengikuti paket: Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat. Satu perangkat di rumah ditambah beberapa di luar negeri pas sekali dengan paket Keluarga.

## Kasus ketiga: akunnya tidak cocok

Perangkat yang dibeli di Tiongkok tertaut ke akun Tiongkok, dan aplikasi dari toko luar negeri tidak bisa login ke situ. Satu-satunya solusi adalah memasang edisi Tiongkok aplikasinya. Jangan menautkan ulang perangkatnya, karena itu akan mengeluarkan akun keluarga Anda.

## Pengingat privasi

Gambar dari kamera rumah Anda seharusnya hanya mengalir antara perangkat Anda dan rumah Anda. Cara jaringan privat mengutamakan koneksi langsung antarperangkat (peer-to-peer) dan hanya meneruskan lewat relay kalau koneksi langsung tidak bisa dibuat, dan gambarnya tidak disimpan di server mana pun; sedangkan cara cloud vendor melewati server vendor. Dalam kedua kasus, jangan memakai "alat tunneling" yang asal-usulnya tidak jelas, karena itu sama saja dengan menyerahkan kamera rumah Anda ke orang lain.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-07) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-07) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
