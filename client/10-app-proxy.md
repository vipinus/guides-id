# 10 · Kalau Dropbox dan software lain meminta proxy HTTP / SOCKS

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/app-proxy?utm_source=github&utm_content=client-10

**Pertama, kondisinya: proxy harus terenkripsi.** Proxy tanpa enkripsi (HTTP biasa, SOCKS4, SOCKS5) dikenali dan diganggu di jaringan Tiongkok; tak lama kemudian koneksinya melambat atau putus, dan akun serta kata sandi pun terkirim tanpa enkripsi. Hanya koneksi terenkripsi yang bisa dipakai dalam jangka panjang, karena itu Proxy Web situs ini selalu memakai koneksi terenkripsi; **untuk software yang hanya menerima HTTP / SOCKS5, biarkan Hiddify mengambil alih seluruh komputer** (lihat di bawah).

Software mandiri seperti Dropbox, Telegram Desktop, Steam, klien cloud drive, dan alat pengembang tidak membaca pengaturan browser, dan pengaturan proxy bawaannya hanya menerima HTTP / SOCKS5 tanpa enkripsi. Kedua sisi tidak cocok, jadi memasukkan proxy tidak membuatnya tersambung. Solusinya **bukan memasukkan proxy**: pakai Hiddify untuk mengalirkan seluruh komputer lewat jalur, lalu atur proxy di software itu ke "No proxy" (tanpa proxy).

## Kenapa tetap tidak tersambung setelah memasukkan proxy

| Penyebab | Penjelasan |
|---|---|
| Jenisnya tidak cocok | Software hanya menawarkan HTTP, SOCKS4, dan SOCKS5, semuanya tanpa enkripsi; proxy situs ini harus terenkripsi dan tidak bisa dimasukkan |
| Proxy tanpa enkripsi yang ditemukan di internet | Tersambung sebentar, lalu diganggu dan hanya jalan putus-sambung |
| Hanya menangani sebagian lalu lintas | Di banyak software, hanya login dan sinkronisasi yang memakai proxy, sementara pembaruan, panggilan, dan sinkronisasi LAN tetap tersambung langsung; proxy HTTP sama sekali tidak meneruskan lalu lintas UDP dari game dan panggilan |
| Diatur terpisah di tiap program | Ganti wilayah atau kata sandi berarti mengubahnya satu per satu, dan yang terlewat akan berhenti bekerja |

## Cara yang disarankan: biarkan Hiddify mengambil alih seluruh komputer

1. Pasang Hiddify dengan mengikuti [09 · Memasang Hiddify di semua platform](09-hiddify-install-all-platforms.md), lalu impor profil dengan mengikuti [02](02-singbox-subscription-links.md).
2. Sambungkan dalam mode "VPN" (bawaan). Di Windows, koneksi pertama butuh hak administrator.
3. Kembalikan proxy di software ke "No proxy": di Dropbox, pilih "No proxy" atau "Auto-detect" (deteksi otomatis) di "Preferences → Network → Proxies"; di Telegram Desktop, pilih "Disable proxy" (matikan proxy) di "Settings → Advanced → Connection type". Di software lain yang punya opsi proxy, matikan opsinya.
4. Periksa: ikon Dropbox di tray menunjukkan "Up to date" (sudah terbaru) dan sinkronisasi mulai berjalan; buka halaman web yang menampilkan IP Anda di browser, dan exit-nya ada di wilayah yang Anda pilih.

Dengan "routing otomatis" menyala, layanan luar negeri seperti Dropbox lewat jalur, sementara WeChat, mobile banking, dan situs Tiongkok tetap tersambung langsung seperti biasa.

## Software yang umum

| Software | Cara mengaturnya |
|---|---|
| Dropbox | Proxy "No proxy" atau "Auto-detect"; kalau dibiarkan di "Manual" dengan alamat lain, Dropbox tetap offline begitu Hiddify dimatikan |
| Telegram Desktop | Connection type "Disable proxy"; MTProto / SOCKS5 bawaan yang ditumpuk di atas terowongan hanya membuatnya lebih lambat |
| OneDrive, Google Drive, iCloud untuk desktop | Mengikuti jaringan sistem; tidak ada yang perlu diatur |
| Steam, Epic, Battle.net | Tidak perlu proxy; kalau unduhan lambat, pindah ke wilayah yang lebih dekat |
| Zoom, Teams, Slack, Discord | Suara dan video memakai UDP, yang hanya dibawa oleh cara yang mengambil alih seluruh komputer |
| VS Code, JetBrains, Cursor | Mengikuti jaringan sistem; hapus proxy yang diatur terpisah di dalam alatnya |

## Kalau tidak bisa memasang klien (komputer kantor)

- Pakai versi web Dropbox dan cloud drive: buka dropbox.com di browser dengan [Proxy Web](03-web-proxy-extension.md); Anda bisa mengunggah dan mengunduh, tetapi tidak ada sinkronisasi otomatis.
- Alat baris perintah (git, pip, npm, curl) menerima proxy terenkripsi: masukkan alamat Proxy Web ke `https_proxy`; lihat [Mengakses layanan luar negeri dari Tiongkok 05 · Linux dan baris perintah](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (dalam bahasa Mandarin).
- Software desktop lain yang hanya menerima HTTP / SOCKS5 sebaiknya dipakai di komputer atau HP pribadi; jangan memasang VPN untuk seluruh komputer di komputer kantor demi ini, karena akan memicu peringatan keamanan perusahaan.

## Tanya jawab

**Bisakah saya diberi alamat proxy SOCKS5 atau HTTP?** Proxy situs ini selalu memakai koneksi terenkripsi; yang tanpa enkripsi tak lama kemudian mulai putus-sambung. Membiarkan Hiddify mengambil alih seluruh komputer lebih stabil dan mencakup semua software sekaligus.

**Dengan Hiddify menyala, apakah masih perlu memasukkan proxy di software?** Tidak. Memasukkannya berarti memutar dua kali: paling ringan jadi lebih lambat, paling parah tidak tersambung.

**Bagaimana dengan Dropbox di HP?** Aplikasi HP tidak punya pengaturan proxy. Pasang Hiddify atau pakai Cisco (AnyConnect); setelah tersambung, semua aplikasi lewat jalur.

**Bisakah tanpa Hiddify?** Bisa. Cisco, Privat, dan OpenVPN juga mengambil alih seluruh komputer, dan software-nya juga diatur ke "No proxy". Kelebihan Hiddify adalah routing bawaan dan kecepatan lebih baik di jaringan dengan packet loss tinggi.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-10) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-10) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
