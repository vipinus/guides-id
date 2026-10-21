# 01 · Cisco AnyConnect: memasang, menyambungkan, dan memperbarui di semua platform

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect adalah klien VPN perusahaan buatan Cisco. Nama resminya sekarang **Cisco Secure Client**; cara kerjanya sama. Anda tidak perlu file sertifikat atau mengimpor profil: masukkan alamat, akun, dan kata sandi, lalu langsung bisa tersambung. Apakah ini jalan di Tiongkok dan apa penggantinya kalau tidak bisa tersambung, lihat [Mengakses layanan luar negeri dari Tiongkok, panduan 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) (dalam bahasa Mandarin).

## Memasang

| Platform | Yang dipasang | Tempat mendapatkannya |
|---|---|---|
| Windows 10 dan yang lebih baru | Cisco Secure Client 5.x | [Halaman Cisco di situs](https://www.leotun.com/id/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (versi terakhir yang mendukungnya; tidak diperbarui lagi) | Sama seperti di atas |
| macOS | Cisco Secure Client 5.x | Sama seperti di atas |
| iOS | Cisco Secure Client | App Store; kalau tidak ada di toko, pasang OpenConnect yang open source, yang memakai protokol yang sama |
| Android | Cisco Secure Client | Google Play, atau APK di halaman situs |
| Linux | Penginstal di halaman situs, atau openconnect dari repositori distribusi Anda | Sama seperti di atas |

Di Windows juga ada OpenConnect-GUI yang open source; akun yang sama bisa dipakai di sana.

## Menyambungkan dalam empat langkah

1. Buka klien lalu masukkan alamat server di kolom alamat. Pengguna LeoTun bisa **mengklik bendera wilayah** di situs untuk menyalin alamat wilayah itu.
2. Masukkan akun (email yang Anda pakai untuk mendaftar) dan kata sandi.
3. Setelah muncul "Connected" (tersambung), buka halaman web yang menampilkan IP Anda untuk memastikan exit-nya ada di wilayah yang Anda pilih.
4. Untuk ganti wilayah, pakai alamat lain. Klien mengingat alamat yang pernah dipakai, jadi lain kali Anda bisa memilihnya dari daftar drop-down.

## Memperbarui

Tidak perlu uninstall dulu: pasang versi baru di atas versi lama, dan alamat yang tersimpan tetap ada. Di HP, perbarui dari toko aplikasi. Setelah pembaruan besar sistem operasi, perbarui klien dulu, baru periksa masalah koneksi.

## Pesan yang umum

| Pesan | Artinya |
|---|---|
| Login failed | Akun atau kata sandi salah, atau akun sudah kedaluwarsa |
| Untrusted server certificate | Kemungkinan besar jam sistem salah, atau jaringan saat ini menyadap koneksi terenkripsi; coba jaringan lain |
| Connection attempt has failed | Alamat ini sementara tidak bisa dijangkau; ganti wilayah |

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-01) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-01) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
