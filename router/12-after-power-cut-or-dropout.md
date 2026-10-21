# 12 · Apakah router pulih sendiri setelah listrik padam atau koneksi terputus?

Siapa pun yang pernah memakai router VPN rakitan sendiri mungkin pernah mengalami ini: listrik padam sekali, atau internet rumah putus sebentar, dan setelah router menyala lagi semuanya tampak normal, tetapi terowongan VPN-nya tidak pernah tersambung lagi sampai Anda masuk ke halaman admin dan mengaturnya ulang.

## Jawaban singkat

Ya, router pulih sendiri. Setelah listrik padam lalu menyala lagi, internet rumah putus, atau terowongan terputus di tengah pemakaian, firmware akan menyambung ulang sendiri. Tidak perlu membuka halaman admin, tidak perlu login lagi.

## Cara kerjanya

Firmware menjalankan pemeriksa yang terus aktif dan mengecek terowongan kira-kira setiap setengah menit. Begitu terowongan ketahuan terputus, pemeriksa menyambungkannya ulang dan memasang kembali split routing.

Selama jeda singkat sebelum terowongan tersambung lagi, situs Tiongkok tetap bisa dibuka. Internet rumah tidak ikut mati hanya karena terowongannya belum tersambung.

Pengaturan Anda juga tetap tersimpan: wilayah, mode split routing, dan sakelar "Pilih jalur tercepat secara otomatis" tidak berubah setelah restart atau sambung ulang. Kalau Anda mematikan split routing, ia tetap mati.

## Apa yang terjadi di tiap kasus

| Kejadian | Sesudahnya |
|---|---|
| Listrik menyala lagi setelah padam | Router menyala dan terowongan tersambung ulang sendiri |
| Internet rumah putus lalu kembali | Terowongan tersambung ulang begitu internet kembali |
| Terowongan terputus di tengah pemakaian | Pemeriksa mendeteksinya lalu menyambung ulang |
| Akun kedaluwarsa | Lalu lintas berhenti lewat terowongan, internet rumah tetap jalan. Setelah diperpanjang, otomatis jalan lagi tanpa perlu login ulang |
| Kami mengganti alamat server | Router ikut menyesuaikan. Tidak ada yang perlu diatur ulang |

## Masih belum pulih setelah beberapa menit? Periksa ini

1. **Apakah internet rumahnya sendiri jalan?** Buka situs Tiongkok. Kalau tidak bisa, masalahnya ada di jaringan atau modem, bukan di terowongan.
2. **Apakah akun sudah kedaluwarsa?** Terowongan tidak akan tersambung setelah masa aktif habis. Login ke situs web dan periksa.
3. **Coba wilayah lain.** Ganti wilayah di halaman admin. Kadang ada wilayah yang sedang bermasalah sementara.
4. **Restart router.** Cabut kabel listriknya, tunggu sepuluh detik, lalu colokkan lagi.
5. Kalau semua itu tidak membantu, kirim tangkapan layar status di halaman admin ke dukungan.

## Penyalaan pertama setelah flash

Penyalaan pertama lebih lambat dari biasanya: firmware memeriksa pembaruan komponen dan mendeteksi negara untuk mengatur daya pancar Wi-Fi. **Colokkan kabel jaringan untuk penyalaan pertama itu.** Wi-Fi yang lemah sebelum router pernah online sekali itu normal.

## Tanya jawab

**Apakah bisa dipakai di tempat yang sering mati listrik?** Bisa. Setiap kali listrik menyala lagi, router menyambung ulang.

**Perlukah router di-restart secara terjadwal?** Tidak perlu.

**Apakah pembaruan komponen akan memutus koneksi saya?** Tidak. Pembaruan diperiksa dan diunduh saat router menyala, dan baru berlaku pada penyalaan berikutnya. Router tidak akan tiba-tiba restart saat sedang dipakai.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-12) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-12) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
