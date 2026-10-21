# 02 · Cara mengimpor link langganan (Hiddify, Clash, Shadowrocket)

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/singbox-subscription?utm_source=github&utm_content=client-02

"Link langganan" yang diberikan penyedia jalur proxy sebenarnya hanyalah alamat HTTPS tempat klien mengunduh konfigurasi lengkap: server, port, dan kredensial semuanya ada di dalamnya, jadi tidak ada yang perlu diketik manual. Halaman Hiddify di LeoTun memberi hal yang sama, dan langsung dalam tiga format, sehingga Hiddify, Clash, dan Shadowrocket masing-masing mengambil formatnya sendiri tanpa perlu konversi apa pun.

## Tiga tombol di jendela pop-up

Login ke situs web → halaman Hiddify → klik bendera sebuah wilayah. Kode QR muncul, dengan tiga tombol di bawahnya. Tombol-tombol itu dikelompokkan **menurut jenis langganan**, bukan menurut sistem operasi, jadi di HP dan komputer yang tampil sama:

| Klien yang tertulis di tombol | Subjudul | Yang tersalin saat diklik |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | Langganan sing-box | Di HP, link impor `sing-box://import-remote-profile?url=…` yang langsung membuka aplikasinya; di komputer, URL konfigurasi `https://…` biasa untuk ditempel. Konfigurasinya sudah berisi aturan routing dan aturan yang menolak IPv6, jadi tidak perlu dibungkus dengan "template langganan" |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Langganan Clash | URL langganan berformat Clash (YAML), untuk ditempel ke daftar langganan / profil di klien |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Tautan berbagi | Satu baris `hysteria2://…` yang hanya memuat node, tanpa aturan routing |

- Kalau nama-namanya tidak muat dalam satu baris, teksnya bergulir berulang; itu normal.
- **Mengklik tombol juga mengganti kode QR di atasnya ke jenis tersebut**, supaya klien yang cocok bisa memindainya. Saat pop-up pertama terbuka, kode QR-nya untuk Hiddify / sing-box, dan klien lain yang langsung memindainya akan mendapat "Invalid QR code" (kode QR tidak valid): klik dulu tombol klien Anda, baru pindai atau tempel.
- Pop-up "Impor semua wilayah · pilih otomatis" di bagian atas halaman hanya punya dua tombol pertama, tanpa tautan berbagi.

**Konversi langganan**: situs pihak ketiga yang mengubah satu format menjadi format lain. LeoTun langsung memberi ketiga format, jadi **tidak perlu konversi**; menyerahkan link yang berisi kredensial Anda ke situs konversi sama saja menyerahkan akun Anda ke pihak ketiga, jadi jangan lakukan.

## Keluarga Hiddify / sing-box: tombol pertama

1. Pasang Hiddify (Android: halaman unduhan situs web atau Google Play; iOS: App Store; aplikasi desktop mencakup Windows / macOS / Linux). Inti sing-box sudah terpasang di dalamnya.
2. Klik bendera sebuah wilayah, dan kode QR muncul.
3. HP: ketuk tombol pertama lalu pindah ke Hiddify, yang akan menawarkan untuk menambahkannya dari papan klip; atau pakai "Scan QR code" (pindai kode QR) di Hiddify pada perangkat lain. Komputer: klik tombol yang sama, yang menyalin alamat https://, lalu di Hiddify pilih "+" → "Add from clipboard" (tambah dari papan klip), dan simpan.
4. Ketuk sambungkan dan izinkan akses VPN saat pertama kali. Untuk menambah wilayah, klik bendera lain; setiap wilayah menjadi profil terpisah.

## Keluarga Clash: tombol kedua

Untuk Clash Meta (mihomo), Clash Verge, FlClash, Stash, dan sejenisnya, klik tombol "Langganan Clash" lalu tempel URL yang tersalin ke daftar langganan / profil di klien. Tidak perlu konverter langganan.

**Klien keluarga Clash tidak boleh memakai tautan berbagi**: klien itu tidak bisa mengimpor satu baris `hysteria2://` sebagai profil.

## Klien lain: tombol ketiga

Klik tombol "Tautan berbagi", lalu pakai "Import from clipboard" (impor dari papan klip) di NekoBox / Shadowrocket / v2rayN / v2rayNG dan sejenisnya, atau pindai kode QR di atas setelah mengklik tombolnya. Tautan berbagi tidak membawa aturan, jadi Anda harus mengatur routing dan IPv6 sendiri: kalau Anda di luar negeri dan ingin menonton konten dari Tiongkok, arahkan domain Tiongkok lewat node dan matikan IPv6.

Klien yang tercantum setelah v2rayN di tombol itu semuanya mendukung hysteria2, tetapi tautan berbagi memakai format hysteria2 yang diperluas yang tidak bisa dibaca oleh beberapa klien; kalau impor gagal atau tidak mau tersambung, pindah ke Hiddify.

## Klien yang tidak bisa dipakai

| Klien | Alasannya |
|---|---|
| Surge | Mendukung hysteria2 tetapi hanya membaca format konfigurasinya sendiri, jadi ketiga jenis tidak ada yang cocok |
| Quantumult X | Tidak mendukung jenis jalur ini |
| Clash asli, Clash for Windows | Intinya tidak punya hysteria2; pakai klien dengan inti mihomo |

## Apakah langganannya kedaluwarsa?

- **Tidak kedaluwarsa karena waktu.** Token di URL langganan terikat ke akun Anda dan tetap berlaku selama akun aktif; memperpanjang atau ganti paket tidak perlu impor ulang.
- **Mengganti kata sandi langsung membatalkan URL lama.** Inilah cara mencabut akses kalau HP hilang atau link bocor; setelah menggantinya, pindai kode lagi.
- **Setelah akun kedaluwarsa** URL-nya membalas 401; begitu diperpanjang, profil yang ada tidak perlu diganti.
- **Profil yang diimpor sebelum September 2026** tidak punya aturan penolak IPv6; hapus lalu impor ulang.

Kalau sudah diimpor tapi tidak mau tersambung, lihat [Pemecahan masalah 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Tanya jawab

**Apa bedanya langganan Hiddify dan langganan Clash?** Formatnya berbeda (JSON vs YAML), dan masing-masing klien tidak mengenali langganan milik yang lain, tetapi node-nya sendiri bisa dipakai keduanya. LeoTun langsung memberi keduanya: klien keluarga Clash klik tombol "Langganan Clash" dan tidak boleh memakai tautan berbagi.

**Bisakah satu profil berisi semua wilayah?** Impor dari bendera menghasilkan satu profil per wilayah, dan Anda berpindah di antaranya lewat daftar profil di klien; dengan begitu, perubahan alamat di satu wilayah hanya memengaruhi wilayah itu. Untuk mengimpor semua wilayah di luar Tiongkok sekaligus dan membiarkan klien memilih otomatis, klik "Impor semua wilayah · pilih otomatis" di bagian atas halaman (hanya ada tombol Langganan sing-box dan Langganan Clash).

**Bisakah kode QR dikirim ke keluarga?** Kode QR berisi kredensial akun Anda; siapa pun yang menerimanya mendapat akun Anda. Berbagi dengan keluarga boleh (perangkat bersamaan sesuai paket: Pribadi 2, Keluarga 4, Perusahaan 8), tetapi jangan pasang di tempat umum; kalau bocor, ganti kata sandi dan kodenya tidak berlaku lagi.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-02) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-02) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
