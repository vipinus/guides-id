# 08 · Cara memastikan Anda benar-benar tersambung, dan dari wilayah mana Anda keluar

Klien yang menampilkan "Connected" (tersambung) belum tentu berarti situs yang Anda kunjungi melihat alamat VPN. Cara paling mudah untuk memeriksanya ada di bilah atas situs ini: kolom "Jaringan saat ini" menunjukkan **Anda seperti yang dilihat situs ini saat ini**: dari negara mana, provinsi/negara bagian mana, dan jaringan mana Anda keluar. Artikel ini membahas cara membaca kolom itu, cara membandingkan sebelum dan sesudah tersambung, cara mengetahui apakah masing-masing dari enam cara koneksi sudah tersambung, arti lampu merah, kuning, dan hijau di daftar wilayah, serta beberapa hal yang bisa Anda periksa sendiri saat "sudah tersambung tapi masih menunjukkan lokasi setempat".

## Yang ditampilkan "Jaringan saat ini" di bilah atas

| Posisi | Isi |
|---|---|
| Di depan | Bendera negara tempat exit berada; diganti ikon Wi‑Fi kalau negaranya tidak bisa dikenali |
| Di tengah | Nama provinsi/negara bagian, ditampilkan dalam bahasa antarmuka (AS, Kanada, Australia, dan sejenisnya memakai singkatan umum seperti CA, ON, NSW); Hong Kong, Makau, dan Singapura langsung menampilkan nama wilayahnya |
| Di akhir | Nama jaringan: tiga operator besar Tiongkok, jaringan pendidikan, dan sejenisnya ditampilkan di antarmuka berbahasa Mandarin dengan nama pendek seperti 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom), dan 教育网 (jaringan pendidikan); sisanya menampilkan nama merek bahasa Inggrisnya (misalnya Comcast, Bell) |

- **Kalau provinsi/negara bagian tidak ditemukan, hanya "bendera · nama jaringan" yang ditampilkan.** Nama negara tidak dipakai sebagai pengisi; benderanya sudah menunjukkan negaranya.
- Di komputer, arahkan kursor ke kolom ini dan akan muncul nama organisasi lengkap, provinsi/negara bagian, kode negara, dan **IP exit**. IP ini hanya ditampilkan kepada Anda, dan paling berguna saat Anda menghubungi dukungan.
- Chrome / Edge di Windows tidak punya font bendera, jadi bendera tampil sebagai dua huruf (misalnya JP, US). Artinya sama.
- Di komputer, kolom ini baru muncul di bilah atas setelah Anda login; di HP ditampilkan tanpa login.

## Bandingkan sebelum dan sesudah tersambung, langsung kelihatan

1. **Dengan VPN mati**, buka situs ini dan lihat: seharusnya yang tampil operator internet rumah atau data seluler Anda, dan benderanya negara tempat Anda berada.
2. **Sambungkan VPN** lalu kembali ke browser: benderanya berubah ke wilayah yang Anda pilih, dan nama jaringannya biasanya berubah menjadi nama pusat data atau penyedia cloud, bukan operator rumah Anda.
3. Kalau keduanya sama, browser ini tidak lewat VPN saat mengunjungi situs ini. Lihat "Sudah tersambung, tapi masih menunjukkan lokasi setempat" di bawah.

**Tidak perlu terus me-refresh halaman.** Kolom ini mengecek ulang otomatis saat Anda kembali ke jendela browser, mengecek beberapa kali lagi dalam beberapa detik setelah mendeteksi perubahan jaringan, dan juga diperbarui setiap sepuluh sampai dua puluh detik selama halaman terbuka. Kalau tepat setelah tersambung masih tampil nilai lama, tunggu sepuluh sampai dua puluh detik atau ganti jendela; kalau tetap belum berubah, refresh manual.

**Kalau Anda di Tiongkok dan memilih "titik masuk Tiongkok"**, wajar kalau bilah atas menampilkan negara asing: titik masuk Tiongkok memakai split routing, jadi situs Tiongkok keluar dari dalam Tiongkok dan situs luar negeri keluar lewat rute luar negeri. Situs ini ada di luar negeri, jadi tentu yang ditampilkan adalah ujung luar negerinya.

## Cara mengetahui apakah tiap cara koneksi sudah tersambung

| Cara | Yang dilihat di klien | Apakah bilah atas situs ini berubah |
|---|---|---|
| Cisco (AnyConnect) | Klien menampilkan "Connected" | Ya. Begitu Cisco tersambung, semua lalu lintas lewat VPN |
| Hiddify | Klien menampilkan tersambung | Berubah di mode global; dengan "auto routing" (routing otomatis) tergantung daftar |
| OpenVPN | Klien menampilkan tersambung | Ya. Secara bawaan semua lalu lintas lewat VPN |
| Privat (Tailscale) | Klien online, **dan** sebuah wilayah dipilih sebagai Exit Node | Hanya berubah kalau exit dipilih; kalau None (tidak ada) yang dipilih, perangkat hanya bisa saling menjangkau dan lalu lintas tidak lewat VPN |
| Proxy Web | Tidak ada status "tersambung"; lihat mode wilayah mana yang dipilih di ikon ekstensi | Hanya browser yang dipasangi ekstensi yang berubah; aturan "auto switch" (ganti otomatis) bisa membuat situs ini tersambung langsung |
| Router | Di halaman admin, status akun normal dan tanggal berakhir ditampilkan | Lihat dari perangkat yang tersambung ke Wi‑Fi router ini; di mode split routing tergantung daftar |

Split routing berarti situs yang ada di daftar lewat VPN dan sisanya tersambung langsung. Kalau bilah atas menunjukkan lokasi setempat saat split routing menyala, belum tentu Anda tidak tersambung: **pindah sementara ke "global" lalu lihat lagi**. Kalau berubah, VPN berfungsi dan situs ini memang tidak ada di daftar.

## Lampu merah, kuning, dan hijau di daftar wilayah

Di halaman Cisco, Hiddify, Proxy, dan OpenVPN ada lampu kecil di bawah bendera tiap wilayah, dan lampu yang sama muncul di depan nama exit di klien Privat. Lampu ini dinilai otomatis dari rata-rata bandwidth real-time tiap server di wilayah itu, dan diperbarui kira-kira sekali per menit:

| Lampu | Artinya |
|---|---|
| Hijau (menyala tetap) | Senggang |
| Kuning (berkedip) | Sedang dipakai |
| Merah (berkedip) | Sibuk |
| Tidak ada lampu | Data belum didapat saat itu; bukan berarti servernya mati |

Di komputer, arahkan kursor ke lampu untuk melihat rata-rata beban wilayah itu.

**Yang dilakukan saat melihat lampu merah:**

- Merah bukan berarti rusak; hanya berarti sedang banyak orang. Kalau Anda sudah tersambung dan kecepatannya cukup, biarkan saja.
- Kalau terasa lambat, pindah ke wilayah berlampu hijau. Untuk Cisco, klik bendera lain di halaman web untuk menyalin alamat baru; untuk Hiddify, impor konfigurasi wilayah lain; untuk Privat, ganti di Exit Node; untuk Proxy, klik wilayah lain di ikon ekstensi.
- Satu wilayah punya beberapa mesin di belakangnya, dan yang paling senggang dipilih otomatis saat Anda tersambung. Tidak perlu memilih mesin sendiri.
- Pukul 20.00 sampai 23.00 adalah jam sibuk. Pada jam itu, pilih wilayah berlampu hijau atau ganti cara koneksi; kalau masih lambat, penyebab biasanya internet rumah setempat (internet bersama di kompleks perumahan, atau operator dan wilayah yang tidak cocok). Cara memilih wilayah menurut operator, lihat Bacaan lanjutan.

## Sudah tersambung, tapi masih menunjukkan lokasi setempat

Diurutkan dari yang paling sering:

1. **Aturan routing membuat situs ini tersambung langsung.** Routing otomatis Hiddify, "auto switch" di ekstensi Proxy, dan mode split routing di router semuanya bisa membuat situs ini tidak lewat VPN. Pindah sementara ke global untuk memastikan; pengguna Proxy juga bisa menambahkan situs ini ke aturannya.
2. **Proxy Web hanya mencakup satu browser itu.** Melihat dari browser lain atau aplikasi HP tentu masih menunjukkan lokasi setempat.
3. **Tidak ada exit yang dipilih di Privat.** Online ≠ lewat VPN; kalau Exit Node-nya None, perangkat hanya bisa saling menjangkau.
4. **Anda melihat dari perangkat yang salah.** Untuk opsi Router, Anda perlu melihat dari perangkat yang tersambung ke Wi‑Fi router itu, bukan HP yang tersambung ke Wi‑Fi modem atau memakai data seluler.
5. **Ada VPN atau alat mesh networking lain yang menyala bersamaan.** VPN kantor atau akselerator penyedia lain akan berebut rute. Sisakan satu saja.
6. **Belum diperbarui.** Tunggu sepuluh sampai dua puluh detik, ganti jendela, atau refresh manual sekali.

## Bilah atas memeriksa IP; IPv6 dan DNS diperiksa terpisah

Bilah atas melihat alamat IPv4 dari koneksi yang diterima situs ini. Kalau yang tampil sudah benar, artinya hanya browser ini yang lewat VPN saat mengunjungi situs ini:

- **IPv6 dan DNS tidak terlihat dari situ.** Kalau browser mengunjungi situs ini lewat IPv6, kolomnya tidak ditampilkan sama sekali; ia tidak akan menyodorkan jaringan yang salah seolah-olah benar. Kalau situs video masih menampilkan pemberitahuan pembatasan hak cipta, kemungkinan besar IPv6 atau DNS melewati VPN; lihat [03 · IPv6 dan DNS yang bocor](03-ipv6-and-dns-leak.md).
- **Aplikasi menyimpan hasil pengecekan wilayah.** Bilah atas selalu dicek ulang dan tidak terpengaruh cache; tetapi aplikasi video dan musik mengingat wilayah sebelumnya. Tutup sepenuhnya lalu buka lagi; lihat [02 · Sudah tersambung ke Tiongkok tapi tetap tidak bisa menonton](02-still-blocked-after-connecting.md).

## Tanya jawab

**Kolom "Jaringan saat ini" di bilah atas hilang?** Di komputer, login dulu. Kalau setelah login masih tidak tampil, kemungkinan besar koneksi ini lewat IPv6 atau untuk sementara tidak bisa dicek; tunggu sepuluh sampai dua puluh detik atau refresh. Kolom ini lebih memilih tidak menampilkan apa-apa daripada menampilkan yang salah.

**Wilayah sama, tapi IP-nya berbeda di dua kali sambungan?** Normal. Satu wilayah punya beberapa mesin di belakangnya, dan setiap sambungan memilih yang paling senggang saat itu. Sambungan yang sudah terbentuk tidak dipindah ke tempat lain di tengah jalan.

**Provinsi yang tampil tidak sesuai dugaan?** Bilah atas menampilkan provinsi/negara bagian tempat IP exit berada dan hanya akurat sampai tingkat itu. Kalau benderanya cocok, exit-nya ada di negara atau wilayah yang Anda pilih.

**Apa yang perlu dilaporkan saat menghubungi dukungan?** Arahkan kursor ke kolom itu di bilah atas dan kirim apa yang muncul (termasuk IP exit) bersama cara koneksi, wilayah yang Anda pilih, dan waktu masalahnya terjadi.

## Bacaan lanjutan

- [Cara memeriksa masalah tidak bisa tersambung, lambat, dan sering putus](https://www.leotun.com/id/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Wilayah mana yang paling cepat dari dalam Tiongkok](https://www.leotun.com/id/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Cara koneksi mana yang cocok untuk situasi apa](https://www.leotun.com/id/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Apa itu Proxy Web dan kapan memakainya](https://www.leotun.com/id/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Apa saja yang bisa dilakukan firmware router](https://www.leotun.com/id/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Kalau Tencent Video menampilkan pemberitahuan pembatasan hak cipta di luar negeri](https://www.leotun.com/id/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=troubleshooting-08) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-08) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
