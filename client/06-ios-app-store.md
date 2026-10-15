# 06 · Kalau iOS tidak mengizinkan Anda memasang aplikasi

Kalau Anda tidak menemukan Hiddify, Tailscale, atau Telegram di iPhone, atau muncul pesan "Aplikasi ini saat ini tidak tersedia di negara atau wilayah Anda", aplikasinya tidak hilang: App Store dibagi per wilayah sesuai wilayah Apple ID Anda, dan App Store wilayah Tiongkok tidak memuat sebagian besar aplikasi jaringan. Di iOS, pasang dari App Store dengan Apple ID wilayah selain Tiongkok; langkah-langkahnya ada di halaman ini. Kami sarankan mendaftar Apple ID baru daripada mengubah akun yang sudah ada. Di bawah ini ada langkah-langkahnya, trik memilih "Tidak Ada" sebagai metode pembayaran, dan alasan Anda tidak boleh memakai akun pinjaman dari orang lain.

## Kenapa ini terjadi

App Store dibagi per wilayah sesuai wilayah Apple ID Anda, dan tiap wilayah memuat aplikasi yang berbeda. App Store Tiongkok tidak memuat Hiddify maupun Tailscale, sedangkan Telegram dan Discord kadang ada kadang tidak; Cisco Secure Client dan OpenVPN Connect tersedia di sebagian besar wilayah. Ini soal daftar aplikasi, bukan masalah aplikasinya, dan akun dari wilayah lain bisa memasangnya.

Di iPhone, Hiddify maupun Privat (Tailscale) dari situs ini sama-sama dipasang dari App Store; cukup ikuti langkah di bawah untuk beralih ke Apple ID wilayah lain. Penginstal untuk Android, Windows, dan macOS disediakan langsung oleh situs ini dan tidak terpengaruh.

## Cara 1 (disarankan): daftarkan Apple ID baru di wilayah selain Tiongkok

1. Keluar dari akun App Store saat ini: Pengaturan → profil Anda di bagian atas → Media & Pembelian → Keluar. Ini hanya mengeluarkan Anda dari App Store, bukan iCloud, jadi foto, cadangan, dan kontak Anda tidak terpengaruh.
2. Di App Store, cari aplikasi gratis, ketuk "Dapatkan", lalu ikuti petunjuk untuk "Buat Apple ID Baru". Pilih salah satu dari Amerika Serikat, Hong Kong, Jepang, atau Singapura sebagai wilayah, dan pilih "Tidak Ada" sebagai metode pembayaran. Pilihan "Tidak Ada" ini hanya muncul kalau Anda mendaftar sambil mengunduh aplikasi gratis; kalau mendaftar langsung lewat web, pilihan itu sering tidak ada.
3. Masuk ke App Store dengan akun baru, lalu cari dan unduh Hiddify, Tailscale, dan Telegram.
4. Setelah terpasang, Anda bisa kembali ke akun semula; aplikasi yang sudah terpasang tetap jalan dan diperbarui seperti biasa. Ganti akun lagi kapan pun Anda perlu memasang aplikasi baru.

## Cara 2: ubah wilayah akun yang sudah ada

Masuk di account.apple.com lalu ubah negara atau wilayahnya. Anda harus membatalkan semua langganan dan menghabiskan saldo dulu, dalam beberapa kasus juga harus menambahkan metode pembayaran lokal, dan mengubahnya kembali sama repotnya. Tidak disarankan, kecuali Anda memang berniat pindah wilayah untuk jangka panjang.

## Yang tidak boleh dilakukan

- Jangan memakai Apple ID pinjaman dari orang lain, termasuk "akun bersama" di grup atau di internet. Pemilik akun bisa mengunci perangkat Anda dari jauh, dan iPhone yang terkunci hanya bisa dibuka oleh dia; begitu autentikasi dua faktor dinyalakan, fitur itu tidak bisa dimatikan, dan risiko serta sengketa apa pun jadi tanggungan Anda. Dukungan situs ini juga tidak akan memberikan akun bersama apa pun.
- Jangan memasang profil konfigurasi yang tidak jelas asalnya atau penginstal yang "ditandatangani dengan sertifikat enterprise". Ini cara umum untuk mengakali App Store, sekaligus pintu masuk untuk menanam sertifikat dan membajak lalu lintas.

## Setelah terpasang

Hiddify: kembali ke halaman Hiddify situs ini dan pindai kodenya, atau ketuk tombol "langganan sing-box" untuk menyalin, lalu pindah ke Hiddify dan tambahkan. Tailscale: logout dulu dari akun resmi, lalu ikuti langkah di halaman Privat untuk memasukkan alamat server kontrol situs ini. Telegram, Discord: buka halaman Kontak situs ini dan pindai kodenya untuk bergabung ke grup.

## Tanya jawab

**Apakah perlu kartu kredit untuk mendaftar di wilayah lain?** Tidak. Dengan Cara 1 (mendaftar sambil mengunduh aplikasi gratis), Anda bisa memilih "Tidak Ada" sebagai metode pembayaran.

**Apakah akun baru memengaruhi iCloud dan foto saya?** Tidak. Anda hanya berganti akun di App Store; iCloud tetap di akun semula.

**Apakah sama di iPad?** Ya, iPadOS mengikuti aturan App Store yang sama.

**Apakah HP Android juga mengalami masalah ini?** Tidak. Penginstal untuk Android, Windows, macOS, dan Linux dibagikan langsung oleh situs ini dan tidak bergantung pada toko aplikasi.

## Bacaan lanjutan

- [Halaman Kontak: kartu unduhan klien dan tiga grup](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-06)
- [Hiddify: impor dengan memindai kode](https://www.leotun.com/id/singbox?utm_source=github&utm_content=client-06)
- [Privat (Tailscale): langkah login](https://www.leotun.com/id/mesh?utm_source=github&utm_content=client-06)
- [Cara menghubungi kami dan supaya tidak hilang kontak](https://www.leotun.com/id/guides/stay-in-touch?utm_source=github&utm_content=client-06)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/ios-app-store?utm_source=github&utm_content=client-06

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-06) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-06) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
