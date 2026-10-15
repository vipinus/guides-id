# 10 · Apakah NAS, printer, dan kamera di belakang router akan terpengaruh?

Begitu router VPN dipasang, kekhawatiran pertama biasanya soal perangkat lain di rumah: apakah NAS, printer, dan kamera masih jalan, dan apakah NAS akan menyeret semua lalu lintasnya lewat VPN?

## Jawaban singkat

Tidak. Split routing menyala secara bawaan: **lalu lintas antarperangkat di rumah, dan lalu lintas ke layanan di Tiongkok, tidak pernah masuk terowongan. Hanya situs yang butuh VPN yang lewat sana.**

## Tiga jenis lalu lintas, tiga jalur

| Lalu lintas | Jalur | Contoh |
|---|---|---|
| Antarperangkat di rumah | Tetap di jaringan lokal, tidak menyentuh terowongan | Menyalin file ke NAS, cast ke TV, mencetak |
| Ke layanan di Tiongkok | Langsung, lewat internet rumah Anda sendiri | NAS sinkronisasi ke cloud drive Tiongkok, kamera mengunggah ke cloud Tiongkok, unduhan domestik |
| Ke situs yang diblokir | Lewat terowongan | YouTube, mesin pencari, alat AI |

Jadi menyalin file ke NAS di rumah tetap secepat jaringan lokal, dan cadangan ke cloud storage Tiongkok memakai seluruh bandwidth internet Anda tanpa menyentuh VPN.

Kalau Anda berada di luar negeri dan memakai rute ke Tiongkok, arahnya terbalik: situs Tiongkok yang ada di daftar lewat terowongan dan sisanya langsung. Lihat [03 · Apa itu split routing](03-router-split-routing.md).

## Tiga situasi umum

**Mengakses NAS dari luar (file jarak jauh, cadangan foto dari HP)**
Dua cara:
- Pakai Privat (Tailscale): login NAS dan HP ke akun yang sama, lalu akses NAS lewat nama perangkatnya dari mana saja. Tanpa IP publik dan tanpa port forwarding. Lihat [Jaringan Privat vs VPN](../network/03-private-network-vs-vpn.md).
- Tetap pakai cara lama (akses jarak jauh dari vendor, port forwarding). Router tidak memblokirnya.

**Unduhan yang berjalan di NAS**
Unduhan dari sumber Tiongkok langsung dan tidak terpengaruh. Unduhan dari situs luar negeri yang memang bisa dibuka dari Tiongkok (misalnya unduhan Apple dan Microsoft) juga langsung secara bawaan; hanya unduhan dari situs yang diblokir yang lewat terowongan dan berjalan dengan kecepatan terowongan. Kalau tidak ingin unduhan memakai terowongan, colokkan NAS ke router di atasnya atau ke modem, maka NAS sepenuhnya melewati router ini.

**Laptop kantor yang butuh VPN perusahaan**
Sambungkan ke Wi-Fi router di atasnya atau modem, terpisah dari router ini. Dua VPN yang ditumpuk biasanya merusak akses ke jaringan kantor.

## Kalau ada satu perangkat yang bermasalah

- Perangkat itu menyalakan "DNS Pribadi" atau "DNS aman". Akibatnya perangkat mencari nama sendiri, memutari router, dan split routing tidak bisa melihatnya. Matikan pengaturan itu.
- Cek perangkat itu tersambung ke Wi-Fi mana. Kalau ke Wi-Fi modem, perangkat itu sama sekali tidak lewat router ini.

## Tanya jawab

**Apakah NAS memakai jatah perangkat di akun saya?** Tidak. Router memakai satu jatah, dan semua yang di belakangnya tidak dihitung terpisah.

**Kalau seisi rumah memakainya, apakah kuota akan habis?** Akun punya kuota tanpa batas, dan lalu lintas domestik memang tidak masuk terowongan sejak awal.

**Bisakah satu perangkat selalu di luar VPN?** Bisa, sambungkan ke router di atasnya atau ke modem. Halaman admin juga bisa mengalihkan seluruh router ke mode "Direct" (langsung), tetapi itu berlaku untuk semua orang sekaligus.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-10) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-10) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, berlaku jangka panjang
