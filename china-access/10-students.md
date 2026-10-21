# 10 · Cara mahasiswa di luar negeri menyiapkan VPN ke Tiongkok

Yang dibutuhkan mahasiswa di luar Tiongkok bukan "jalur ke Tiongkok yang tersambung terus", melainkan bisa mendapat IP Tiongkok dengan andal dalam beberapa situasi tertentu: menonton serial dan mendengarkan musik, login ke internet banking dan aplikasi layanan pemerintah, berebut tiket, dan sesekali mengecek perangkat keluarga di Tiongkok dari jauh. Setiap situasi menuntut hal yang berbeda dari jalurnya, dan jaringan kampus juga punya batasan sendiri. Artikel ini menjelaskan per situasi apa yang dibutuhkan, cara mengaturnya, dan kapan memutus koneksi, lalu ditutup dengan daftar periksa yang bisa diselesaikan dalam sepuluh menit sebelum semester dimulai.

## Serial, musik, siaran langsung: cukup IP Tiongkok, tapi IPv6 harus ditutup

Tencent Video, iQIYI, anime di Bilibili, NetEase Cloud Music, dan QQ Music semuanya menentukan wilayah dari IP asal, jadi cukup tersambung ke jalur Tiongkok. Jebakan yang paling sering menjerat mahasiswa adalah jaringan kampus dan asrama yang umumnya punya IPv6: perangkat lebih memilih IPv6, yang tidak lewat jalur, sehingga situs video tetap melihat alamat luar negeri dan menampilkan "pembatasan hak cipta".

Solusinya: pakai jalur atau klien yang menolak IPv6 di dalam terowongan, atau matikan IPv6 di perangkat. Ketiga cara koneksi LeoTun sudah memblokir IPv6 di sisi jalur, tanpa perlu mengubah perangkat; untuk pemeriksaan lebih rinci, lihat "Kalau Tencent Video menampilkan pemberitahuan pembatasan hak cipta di luar negeri".

Kualitas gambar tergantung bandwidth lintas negara. Pukul 20.00 sampai 23.00 waktu Beijing adalah jam sibuk, yang di Eropa dan Amerika Utara jatuh pada pagi sampai siang; kalau 1080p terus berputar-putar di jam itu, ganti ke exit Tiongkok yang lain.

## Internet banking, Alipay, aplikasi pemerintah: login lewat jalur Tiongkok, dan putuskan setelah selesai

Berbagai aplikasi bank, Alipay, CHSI, dan Platform Layanan Pemerintah Nasional memperlakukan IP luar negeri secara berbeda: ada yang langsung menolak login, ada yang menambah beberapa langkah verifikasi, dan ada yang membiarkan Anda login tapi memicu manajemen risiko saat transfer. Kesamaannya, semuanya mencatat IP login Anda, dan bolak-balik antara luar negeri dan Tiongkok adalah yang paling mudah membuat Anda ditandai.

Caranya: saat perlu melakukan hal-hal ini, sambungkan jalur Tiongkok dulu baru buka aplikasinya; setelah selesai, tutup aplikasinya lalu putuskan jalurnya. Jangan memakai aplikasi yang sama sambil sering berganti antara jalur Tiongkok dan jaringan lokal.

Kode verifikasi di HP yang tidak pernah sampai tidak ada hubungannya dengan jalur; itu urusan roaming nomor Tiongkok di luar negeri. Sebelum berangkat, aktifkan roaming internasional untuk nomor itu, atau ganti ke paket yang bisa menerima kode di luar negeri.

## 12306 dan tiket konser: sambungkan lebih awal, dan jangan berganti saat membayar

12306 kadang meminta verifikasi tambahan dari IP luar negeri, dan saat berebut tiket, satu verifikasi tambahan berarti tiketnya hilang. Beberapa menit sebelum penjualan dibuka, sambungkan ke jalur Tiongkok, login, dan pilih data penumpang, lalu kirim begitu waktunya tiba. Saat pembayaran dialihkan ke Alipay atau internet banking, biarkan jalurnya tetap.

Hal yang sama berlaku untuk platform tiket seperti Damai dan Maoyan.

## Tiga batasan jaringan kampus dan asrama

- IPv6: lihat di atas; pakai jalur yang memblokir IPv6.
- UDP dibatasi atau diperlambat: cukup banyak jaringan kampus yang memperlambat atau bahkan memblokir lalu lintas UDP. hysteria2 yang dipakai Hiddify berjalan di atas UDP, dan di jaringan seperti itu justru kurang stabil dibanding AnyConnect yang berjalan di atas TLS; satu akun bisa memakai keduanya, jadi kalau UDP tidak jalan, pindah ke AnyConnect.
- Halaman login (captive portal): setelah tersambung ke Wi‑Fi kampus, selesaikan autentikasi di browser dulu, baru nyalakan jalur. Kalau klien jalurnya diatur "sambung otomatis saat startup", klien akan mencoba tersambung sebelum autentikasi dan gagal; tunggu sebentar atau sambungkan ulang secara manual.

## Saat liburan ke Tiongkok: akun yang sama dipakai ke arah sebaliknya

Di Tiongkok Anda butuh Google, email kampus, dan database jurnal; cukup ganti wilayah jalur dari Tiongkok ke Jepang, Amerika Serikat, atau wilayah luar negeri terdekat, tanpa perlu ganti akun. Ke-24 wilayah LeoTun ada di akun yang sama, dan mengakses Tiongkok dari luar negeri serta mengakses luar negeri dari Tiongkok adalah dua arah dari hal yang sama.

Saat tersambung dari dalam Tiongkok, alamat AnyConnect dan Hiddify berganti otomatis untuk menghadapi pemblokiran, dan alamat yang tersimpan di klien tidak perlu diubah; kalau tidak mau tersambung, ganti wilayah atau ganti protokol.

## Daftar periksa sepuluh menit sebelum semester dimulai

1. Pasang satu klien (AnyConnect atau Hiddify) di HP dan satu di komputer, lalu login atau impor dengan memindai kode QR di masing-masing.
2. Sambungkan ke jalur Tiongkok lewat Wi‑Fi asrama dan buka halaman tes IPv6 untuk memastikan IPv6 tidak tersedia atau menampilkan alamat Tiongkok daratan.
3. Buka Tencent Video dan putar episode apa saja untuk memastikan tidak ada pembatasan hak cipta.
4. Login sekali ke aplikasi bank untuk memastikan bisa masuk, lalu tutup aplikasinya dan putuskan jalurnya.
5. Catat kontak dukungan penyedia layanan; kalau ada masalah, baca panduan pemecahan masalah dulu baru bertanya.

## Tanya jawab

**Apakah memakai VPN ke Tiongkok memengaruhi akun jaringan kampus?** Tidak. Jalur hanya mengirim lalu lintas Anda ke exit di Tiongkok, dan yang dilihat jaringan kampus hanyalah satu koneksi terenkripsi. Aturan pemakaian kebanyakan kampus hanya melarang unduhan yang melanggar hak cipta dan serangan, dan akses pribadi ke layanan di negara asal tidak termasuk; kalau ragu, baca kebijakan pemakaian jaringan (acceptable use policy) kampus Anda.

**Bisakah satu akun dipakai bersama teman sekamar?** Tergantung paketnya, satu akun bisa punya 2 (Pribadi), 4 (Keluarga), atau 8 (Perusahaan) perangkat online bersamaan, dan berbagi dengan keluarga atau teman sekamar masih dalam batas aturan. Tetapi untuk urusan seperti internet banking, lebih aman kalau masing-masing memakai akun sendiri, supaya beberapa orang tidak sering berganti di jalur yang sama dan memicu manajemen risiko.

**Kenapa Hiddify lambat di asrama sementara AnyConnect normal?** Kemungkinan besar jaringan kampus membatasi UDP. Protokol hysteria2 di Hiddify berbasis UDP, dan kalau diperlambat, gejalanya lambat atau putus-putus; AnyConnect berjalan di atas TLS, sama seperti membuka situs HTTPS, jadi tidak terpengaruh.

**Bisakah saya bermain game server Tiongkok lewat jalur ke Tiongkok?** Bisa login, tetapi latensinya tergantung jarak fisik Anda ke exit di Tiongkok. Bagian latensi itu tetap; masih bisa diterima untuk game turn-based dan MOBA, tapi terasa di game tembak-tembakan.

**Apakah akunnya masih berguna setelah lulus dan pulang ke Tiongkok?** Ya. Akun yang sama tetap bisa dipakai di dalam Tiongkok dengan wilayah luar negeri, untuk mengakses Google, GitHub, email kampus, dan database jurnal.

## Bacaan lanjutan

- [Kalau Tencent Video menampilkan pemberitahuan pembatasan hak cipta di luar negeri](https://www.leotun.com/id/guides/overseas-video?utm_source=github&utm_content=china-access-10)
- [Cara memilih VPN ke Tiongkok](https://www.leotun.com/id/guides/choose-china-vpn?utm_source=github&utm_content=china-access-10)
- [Unduh klien AnyConnect](https://www.leotun.com/id/anyconnect?utm_source=github&utm_content=china-access-10)
- [Klien Hiddify dan impor langganan](https://www.leotun.com/id/singbox?utm_source=github&utm_content=china-access-10)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/students?utm_source=github&utm_content=china-access-10

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-10) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-10) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
