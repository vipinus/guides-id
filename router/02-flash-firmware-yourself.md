# 02 · Flash firmware sendiri: dari sistem bawaan ke firmware kami, langkah demi langkah (ada videonya)

> Video tutorial (sekitar dua setengah menit, narasi bahasa Inggris atau Mandarin): https://www.leotun.com/id/video/router-flash?utm_source=github&utm_content=router-02
>
> Versi situs web: https://www.leotun.com/id/guides/router-flash?utm_source=github&utm_content=router-02

Panduan ini untuk Anda yang sudah punya router dengan model yang ada di daftar dukungan. Router Anda masih memakai sistem bawaan pabrik, dan kita akan berjalan dari membuka situs sampai seluruh rumah tersambung: apa yang diklik di tiap langkah, apa yang akan Anda lihat, dan di mana orang sering keliru. Demonstrasinya memakai GL.iNet GL-MT3000. Model lain mengikuti langkah yang sama; hanya tampilan panel admin bawaannya yang berbeda. Kalau tidak mau repot mengerjakannya sendiri, router yang sudah terpasang firmware lebih praktis: lihat [01](01-plug-and-play-router.md). Untuk memilih model, lihat [07](07-which-router-to-buy.md).

## Sebelum mulai

- **Pastikan model Anda didukung.** Login, buka bagian **Router**, dan cari model Anda berdasarkan merek. Revisi hardware di belakang nama model (v1, v2, dan seterusnya) juga harus cocok.
- **Akun Anda harus aktif.** Paket Pribadi, Keluarga, dan Perusahaan semuanya bisa memakai router.
- **Siapkan kabel LAN.** Port WAN router disambungkan ke modem atau router di atasnya. Saat flash, sebaiknya komputer juga disambungkan ke router dengan kabel; lebih stabil daripada Wi-Fi.
- **Simpan salinan firmware bawaan.** Unduh firmware bawaan untuk model Anda dari situs pabrikannya, berjaga-jaga kalau suatu saat ingin kembali.

## Langkah 1: Build firmware di situs

1. Login lalu klik **Router** di bilah navigasi.
2. Cari model Anda dan klik **Firmware**, atau gulir ke bawah ke "Build Firmware" dan pilih model dari daftar merek.
3. Klik **Mulai Build**.

Beberapa hal yang perlu diketahui dulu:

- **Build memakan waktu 3 sampai 5 menit.** Firmware dibuat khusus untuk akun Anda saat itu juga, bukan file siap pakai. Saat ramai, build bisa masuk antrean. Halaman akan memberi tahu kalau itu terjadi; tunggu saja, tidak perlu klik lagi.
- **Anda akan dapat email saat sudah siap.** Entri di "Build Terbaru" berubah menjadi "Selesai", dan pemberitahuan masuk ke kotak surat Anda.
- **Bahasa antarmuka firmware mengikuti bahasa situs.** Kalau Anda memakai situs dalam bahasa Indonesia, halaman admin router akan berbahasa Indonesia. Untuk bahasa lain, ganti dulu bahasa situs, lalu build.
- **Link unduhan berlaku satu hari.** Kalau sudah kedaluwarsa, build ulang saja.

## Langkah 2: Unduh dan ekstrak

1. Di "Build Terbaru", klik **Unduh**. Anda akan mendapat file zip.
2. Buka folder Unduhan lalu **ekstrak** file itu.
3. Folder hasil ekstrak berisi file firmware.

File mana yang dipakai:

| Router Anda saat ini memakai | Pakai file |
|---|---|
| Sistem bawaan GL.iNet (seperti di video) | yang berakhiran `sysupgrade.bin` |
| Sistem bawaan merek lain | yang namanya mengandung `factory` |
| Sudah firmware kami, dan Anda sedang memperbarui | yang namanya mengandung `sysupgrade` |

Kalau zip-nya hanya berisi satu file, itulah yang dipakai.

> ⚠️ **Firmware ini hanya untuk Anda.** Di dalamnya ada data akun Anda supaya router bisa login sendiri setelah di-flash. Jangan kirim file ini ke orang lain atau membagikannya secara publik.

## Langkah 3: Flash dari panel admin bawaan

Contohnya GL.iNet:

1. Sambungkan komputer ke router, buka panel admin bawaan di browser (`http://192.168.8.1` di GL.iNet) dan login dengan kata sandi admin.
2. Di menu kiri, buka **System** → **Upgrade** (sistem → pembaruan).
3. Pindah ke tab **Firmware Local Upgrade** (pembaruan firmware lokal).
4. Klik area unggah dan pilih file firmware yang sudah diekstrak.
5. Tunggu sampai verifikasi menunjukkan **Pass** (lolos).
6. **Matikan "Keep Settings"** (simpan pengaturan). Langkah inilah yang paling sering terlewat. Kedua sistem tidak memakai format konfigurasi yang sama, dan menyimpan pengaturan lama menimbulkan berbagai masalah aneh.
7. Klik **Install** (pasang).

Halaman berubah menjadi "Upgrading and rebooting…" (memperbarui dan memulai ulang) dengan lingkaran progres. **Prosesnya dua sampai tiga menit. Selama itu jangan cabut router dan jangan tutup halamannya.** Wajar kalau halaman berhenti memuat setelah progres selesai: router kini menjalankan sistem lain, dan alamat serta Wi-Fi-nya sudah berubah. Lihat langkah berikutnya.

Merek lain: cari "Firmware Upgrade", "System Upgrade", atau "Local Upgrade" di panel admin bawaan, unggah file-nya, dan sekali lagi jangan simpan pengaturan.

## Langkah 4: Sambungkan ke Wi-Fi baru

Setelah di-flash, nama Wi-Fi lama hilang dan muncul yang baru:

- **Nama Wi-Fi: `www.anyfq.com`**
- **Kata sandi Wi-Fi: `www.anyfq.com`** (sama dengan namanya)

Komputer dan HP harus **pindah ke Wi-Fi ini** dulu sebelum bisa online atau membuka halaman admin router. Komputer yang tersambung ke router lewat kabel tidak perlu pindah.

Alamat admin yang baru adalah `http://192.168.11.1` (ketik sendiri `http://` di depannya).

## Langkah 5: Tunggu sampai tersambung sendiri

Tidak perlu login, tidak perlu memilih wilayah. **Selama akun Anda aktif, router tersambung sendiri dalam 10 menit.** Setelah itu, semua perangkat di Wi-Fi ini otomatis lewat layanan, termasuk TV, set-top box, dan konsol game.

Untuk memastikan sudah tersambung, buka situs yang biasanya tidak bisa Anda akses dari perangkat yang terhubung ke router, atau lihat statusnya di halaman admin.

## Dua hal yang sebaiknya dilakukan sesudahnya

1. **Ganti kata sandi bawaan.** Kata sandi Wi-Fi dan kata sandi admin bawaan diketahui umum. Ganti keduanya di halaman admin.
2. **Sinyal Wi-Fi lemah tepat setelah flash itu wajar.** Router perlu online sekali dan mengenali wilayahnya dulu, baru menaikkan daya nirkabel ke batas yang diizinkan di sana. Pasang kabel LAN dan biarkan router online dulu.

## Mengganti router lama dengan yang baru

Satu akun hanya tertaut ke satu router pada satu waktu. Kalau akun Anda sebelumnya dipakai di router lain:

1. Login, buka bagian **Router**, dan di bawah judul "Build Firmware" Anda akan melihat model yang **Tertaut**, dengan tombol **Lepas tautan** di sampingnya.
2. Klik Lepas tautan. Ini bisa dilakukan meski router lama rusak atau tidak ada di tangan.
3. Di router baru tidak ada yang perlu dilakukan: router itu **tersambung otomatis** dan tertaut ke akun Anda.

Kalau router baru sudah telanjur di-flash sebelum melepas tautan, tidak apa-apa. Router baru akan terus menunggu dan tersambung sendiri begitu tautannya dilepas.

Aturan lengkapnya ada di [05 · Pengikatan MAC dan mengganti router](05-mac-binding-and-replacing.md).

## Kalau akun saya kedaluwarsa

Setelah kedaluwarsa, router berhenti mengalirkan lalu lintas lewat layanan, sementara jaringan rumah tetap berjalan seperti biasa. **Begitu Anda memperpanjang, router pulih sendiri: tidak perlu login ulang, tidak perlu flash ulang.**

## Tidak tersambung sendiri: cara memeriksanya

Kalau setelah sekitar sepuluh menit masih belum jalan, periksa urutan berikut:

1. **Apakah internet rumahnya sendiri jalan?** Dari perangkat yang terhubung ke router, buka situs biasa apa saja. Kalau gagal, masalahnya di kabel atau modem: pastikan kabel di port WAN terpasang dengan benar.
2. **Apakah akunnya kedaluwarsa?** Login di situs dan cek tanggal berakhirnya. Setelah memperpanjang, tunggu beberapa menit.
3. **Apakah akun masih tertaut ke router lama?** Di bagian Router, lihat model yang tertaut. Kalau bukan router ini, klik Lepas tautan.
4. **Mulai ulang router sekali.** Cabut, tunggu sepuluh detik, pasang lagi, dan beri waktu dua sampai tiga menit.
5. **Login manual.** Buka `http://192.168.11.1` dan login ke router dengan nama pengguna `root` dan kata sandi `www.anyfq.com`. Lalu buka **Services** → **VPN** (layanan → VPN), masukkan email dan kata sandi akun Anda, lalu simpan.

Masih belum bisa? Tanyakan di grup, sebutkan model router dan sampai langkah mana di daftar atas Anda sudah mencoba.

## Kapan sebaiknya tidak flash sendiri

Modelnya tidak ada di daftar, revisi hardware-nya tidak cocok, atau router lama tanpa mode pemulihan. Dalam tiga kasus ini, router yang sudah terpasang firmware lebih praktis.

## Kalau flash-nya gagal

Sebagian besar router punya mode pemulihan: cabut daya, tahan tombol reset sambil memasang daya lagi, terus tahan beberapa detik, lalu sambungkan komputer dengan kabel dan unggah firmware bawaan sesuai petunjuk pabrikan. Untuk GL.iNet, cari "uboot" di dokumentasinya. Untuk inilah firmware bawaan yang Anda simpan tadi.

## Pertanyaan umum

**Apakah flash membatalkan garansi?** Tergantung pabrikannya. Router GL.iNet sejak awal dibangun di atas sistem open source dan bisa di-flash kembali ke bawaan.

**Bisakah kembali ke firmware bawaan?** Bisa. Pakai mode pemulihan yang dijelaskan di "Kalau flash-nya gagal" untuk mengunggah firmware bawaan.

**Bisakah satu file firmware dipakai di dua router?** Tidak. Firmware dibuat per akun, dan satu akun hanya tertaut ke satu router pada satu waktu.

**Kalau ganti akun, perlu build baru?** Tidak. Logout di halaman admin lalu login dengan akun baru.

**Apakah pembaruan nanti perlu flash ulang?** Pembaruan rutin diambil router sendiri; Anda tidak perlu melakukan apa-apa. Hanya versi besar yang butuh build baru dan sekali flash file sysupgrade, dan situs akan mengumumkannya saat itu tiba.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-02) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-02) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, berlaku jangka panjang
