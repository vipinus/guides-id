# 04 · Hiddify sudah diimpor tapi tidak mau tersambung

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Cocokkan error Anda dengan tabel di bawah. Cara mengimpor dari awal ada di [Cara mengimpor link langganan (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md).

| Gejala | Penyebab | Yang harus dilakukan |
|---|---|---|
| "Unable to fetch subscription" (gagal mengambil langganan), 401 | Akun sudah kedaluwarsa, atau kata sandi diganti (mengganti kata sandi langsung membatalkan konfigurasi lama; ini memang disengaja) | Login ke situs dan cek masa aktifnya; setelah memperpanjang atau mengganti kata sandi, pindai ulang kode QR |
| Impor berhasil, koneksi timeout | Alamat wilayah itu baru saja diganti, atau titik masuk itu sedang diganggu operator | Ketuk "Update subscription" (perbarui langganan) di klien untuk mengambil konfigurasi terbaru; ganti ke wilayah lain, karena tiap wilayah adalah konfigurasi terpisah dan tidak saling memengaruhi |
| Tersambung tapi tidak ada internet | Aturan routing klien sendiri mengirim lalu lintas ke "direct" | Ubah outbound bawaan ke node tersebut, atau hapus aturan yang Anda tambahkan sendiri |
| Pindai muncul "Invalid QR code" (kode QR tidak valid) | Saat popup pertama terbuka, kode QR-nya untuk Hiddify / sing-box, dan klien lain yang langsung memindainya akan mendapat error ini; atau kodenya dipindai dari tangkapan layar orang lain | Klik dulu tombol untuk klien Anda, yang mengganti kode QR ke jenis yang cocok, lalu pindai atau tempel: klien keluarga Clash klik "langganan Clash"; Shadowrocket / NekoBox / v2rayN dan sejenisnya klik "Link berbagi". Kode QR berisi kredensial Anda sendiri, dan milik orang lain tidak akan bisa dipakai |
| Kecepatan lambat | Wilayah yang dipilih sedang padat, atau internet lokal tidak cocok dengan wilayahnya | Lihat lampu merah, kuning, dan hijau di daftar wilayah di situs lalu pindah ke wilayah berlampu hijau; kalau masih lambat, ganti wilayah sesuai operator internet Anda |
| Klien keluarga Clash gagal mengimpor link berbagi | Clash Meta, Clash Verge, FlClash, Stash, dan sejenisnya tidak bisa mengimpor satu baris hysteria2:// sebagai profil | Klik tombol "langganan Clash" lalu tempel URL-nya ke daftar langganan klien; Clash asli dan Clash for Windows tidak punya hysteria2 di intinya, jadi pakai klien dengan inti mihomo |
| Link berbagi gagal diimpor atau tidak tersambung | Link berbagi memakai format tambahan yang tidak bisa dibaca beberapa klien | Pindah ke Hiddify |

## Apakah perlu impor ulang setelah memperpanjang, ganti paket, atau ganti kata sandi

- **Memperpanjang atau ganti paket (Pribadi / Keluarga / Perusahaan)**: Tidak. Konfigurasi yang ada tetap jalan.
- **Ganti kata sandi**: Konfigurasi lama langsung tidak berlaku; pindai ulang kode QR. Kalau HP hilang atau link-nya bocor, pakai cara ini untuk mencabut akses.
- **Akun kedaluwarsa**: Konfigurasi mengembalikan 401. Setelah memperpanjang, tidak perlu konfigurasi baru; cukup sambungkan lagi.
- **Diimpor sebelum September 2026**: Aturan yang menolak IPv6 belum ada, jadi menonton video Tiongkok dari luar negeri akan memunculkan pemberitahuan pembatasan hak cipta. Hapus lalu impor ulang; lihat [03](03-ipv6-and-dns-leak.md).

## Kapan menghubungi dukungan

Sampaikan tiga hal ke dukungan: nama dan versi klien, wilayah, dan teks error persisnya atau tangkapan layarnya.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=troubleshooting-04) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-04) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, berlaku jangka panjang
