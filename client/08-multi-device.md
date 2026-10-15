# 08 · Atur banyak perangkat sekali saja, dan ganti HP tanpa mulai dari nol

Bagi yang punya banyak perangkat, bagian paling merepotkan adalah mengatur satu per satu, mengulang semuanya setelah ganti HP, dan mengetuk sambungkan di tiap perangkat saat bepergian. Jaringan Privat menghilangkan semua itu: setiap perangkat cukup login sekali dengan akun Anda di situs ini lalu tetap online, tanpa perlu apa-apa lagi setelah restart atau ganti Wi‑Fi; setiap perangkat memilih wilayah exit-nya sendiri, jadi laptop bisa memakai Jepang dan HP memakai wilayah Tiongkok tanpa saling mengganggu; perangkat dalam satu akun bisa saling mengakses, jadi laptop yang sedang di luar rumah bisa langsung membuka folder bersama di NAS rumah. HP baru cukup login. Artikel ini menjelaskan cara memasukkan semua perangkat di rumah, cara jatahnya dihitung, dan cara menangani masa aktif habis serta ganti perangkat.

## Yang dilakukan sekali saja per perangkat

1. Pasang klien Tailscale (Android, Windows, macOS, dan Linux dari bagian unduhan di halaman Privat situs ini; iPhone / iPad dari App Store, yang butuh Apple ID wilayah selain Tiongkok).
2. Kalau Anda pernah login ke akun Tailscale resmi, logout dulu, lalu arahkan login ke server kontrol situs ini (HP: "⋯" di layar yang belum login → Use custom server (pakai server khusus); komputer: salin perintah dari halaman; macOS: Account Settings → Accounts → panah di samping "Add Account…" → Add Account Using Alternate Server (tambah akun dengan server alternatif)).
3. Konfirmasi di browser dengan akun Anda di situs ini. Sejak itu perangkat sudah masuk jaringan Privat dan tidak perlu diurus lagi.
4. Pilih exit: setiap perangkat memilih di menunya sendiri, tidak bergantung pada yang lain. Kalau tidak ingin memakai exit, pilih None (tidak ada), yang hanya menyisakan akses antarperangkat.

## Cara menghitung perangkat yang online bersamaan

Satu akun boleh dipasang di berapa pun perangkat; yang dibatasi hanya jumlah yang online pada saat yang sama: Pribadi 2, Keluarga 4, Perusahaan 8, berbagi satu jatah dengan Cisco, Hiddify, dan cara lainnya. Kalau melebihi batas paket, Anda bisa menaikkan paket akun sementara (sisa masa aktif dikonversi senilai menurut harga) lalu kembali lagi setelah selesai.

Router dihitung satu perangkat, dan perangkat di belakangnya tidak dihitung. Satu router atau NAS di rumah ditambah HP dan laptop yang Anda bawa biasanya sudah cukup.

## Perangkat bisa saling mengakses

- Setiap perangkat dalam satu akun punya alamat jaringan privat dan juga bisa diakses lewat nama perangkat, tanpa perlu IP publik atau port forwarding.
- Membuka folder bersama di NAS rumah dari laptop di luar rumah, melihat perekam CCTV rumah dari HP, atau remote desktop ke komputer rumah, semuanya tersambung langsung lewat alamat jaringan privat.
- Router rumah yang memakai firmware situs ini bisa membagikan seluruh LAN ke jaringan Privat, sehingga perangkat yang tidak bisa menjalankan klien, seperti printer dan TV, juga bisa diakses dari luar.
- Perangkat pelanggan lain sama sekali tidak ada di jaringan Privat Anda; bukan sekadar tidak terlihat.

## Masa aktif habis, ganti perangkat, uninstall

- Akun kedaluwarsa: semua perangkat offline dalam beberapa menit; setelah memperpanjang, login sekali lagi di tiap perangkat, dan pengaturan exit tetap tersimpan.
- Ganti HP: login di HP baru dengan langkah di atas; kalau muncul pesan batas sudah tercapai, logout di HP lama, atau naikkan paket akun sementara lalu kembalikan setelah selesai.
- Kalau tidak ingin sebuah perangkat tetap di jaringan Privat: logout di kliennya; untuk memaksa perangkat offline, hubungi dukungan.
- Jangan menjalankan VPN lain di perangkat yang sama pada saat bersamaan (klien Cisco kantor, software mesh networking lain); keduanya akan berebut DNS dan rute.

## Tanya jawab

**Bisakah setiap perangkat memilih wilayah exit berbeda?** Bisa, setiap perangkat memilih exit-nya sendiri. Laptop bisa memakai Jepang untuk video sementara HP memakai wilayah Tiongkok untuk mobile banking, tanpa saling mengganggu.

**Apakah jaringan Privat yang selalu nyala menguras baterai?** Kalau tidak memilih exit, hampir tidak ada lalu lintas; hanya dipakai saat berkomunikasi dengan perangkat di jaringan Privat. Pemakaian baterainya setara dengan VPN sistem.

**Bagaimana memasangnya di NAS rumah?** Synology dan QNAP punya paket Tailscale, dan sistem Linux memakai skrip instalasi resmi; saat login, arahkan ke server kontrol situs ini dengan cara yang sama. Router yang memakai firmware situs ini tidak perlu dipasangi: login ke akun Anda dan router itu sudah masuk jaringan Privat.

**Kenapa tidak memasang Cisco di semua perangkat saja?** Bisa, tetapi dengan Cisco Anda harus mengetuk sambungkan setiap kali, menyambung ulang setelah putus, dan mengganti alamat untuk ganti exit; dengan banyak perangkat, jaringan Privat jauh lebih praktis. Pengecualiannya perangkat di jaringan kampus yang membatasi UDP; pakai Cisco di perangkat itu.

## Bacaan lanjutan

- [Halaman Privat: unduhan dan langkah login](https://www.leotun.com/id/mesh?utm_source=github&utm_content=client-08)
- [Apa itu jaringan Privat (Tailscale)](https://www.leotun.com/id/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Melihat kamera dan NAS rumah di Tiongkok dari luar negeri](https://www.leotun.com/id/guides/home-camera?utm_source=github&utm_content=client-08)
- [Apa saja yang bisa dilakukan firmware router](https://www.leotun.com/id/guides/router-firmware?utm_source=github&utm_content=client-08)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/multi-device?utm_source=github&utm_content=client-08

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-08) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-08) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
