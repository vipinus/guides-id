# 06 · Kalau Mac Anda bilang aplikasi "rusak"

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

Kesimpulannya dulu: file-nya tidak rusak, dan tidak ada yang mengutak-atiknya. Kalau saat mengklik dua kali Hiddify di Mac muncul pesan "rusak dan tidak dapat dibuka" atau "pengembang tidak dapat diverifikasi", itu Gatekeeper milik sistem yang memblokirnya; ikuti langkah di bawah untuk mengizinkannya.

Dalam pengujian kami saat ini, memasang Hiddify di Windows tidak lagi memicu peringatan virus. Kalau antivirus yang Anda pasang tetap menandainya, ikuti urutan yang sama di sini: periksa dulu, baru izinkan.

## Kenapa diblokir

**File yang diunduh dari halaman web diberi tanda karantina.** Saat Gatekeeper di macOS melihat tanda ini, ia memblokir aplikasinya. Pesannya kadang "rusak" dan kadang "pengembang tidak dapat diverifikasi"; penyebabnya sama.

Yang kami lakukan: klien desktop adalah **salinan tanpa modifikasi** dari paket rilis proyek open source aslinya. Kami tidak mengubahnya, tidak mengemasnya ulang, dan tidak menyisipkan apa pun; kami hanya menaruhnya di situs unduhan kami sendiri agar lebih mudah diunduh.

## Periksa sendiri dulu; jangan asal mengizinkan

Mengizinkan aplikasi berarti sistem berhenti memeriksanya, jadi urutannya: periksa dulu, baru izinkan.

**Unggah ke VirusTotal untuk pemeriksaan kedua.** Seret file instalasinya ke [virustotal.com](https://virustotal.com/gui/home/upload). Beberapa mesin heuristik menandainya sementara vendor-vendor utama semuanya meloloskan, itu pola khas positif palsu. Kalau sebagian besar mesin utama menandainya, **jangan pasang**; langsung hubungi kami.

Lanjutkan hanya setelah lolos pemeriksaan. Kalau ragu, hubungi dukungan dulu dan kami akan memeriksa situs unduhannya.

## Tiga cara mengizinkan, dari yang paling sempit ke paling luas

Setelah klik dua kali, Anda mungkin melihat "“Nama klien” rusak dan tidak dapat dibuka. Anda harus memindahkannya ke Tempat Sampah", atau "tidak dapat dibuka karena pengembang tidak dapat diverifikasi". Tiga langkah di bawah berurutan dari yang paling sempit ke paling luas; **kalau langkah pertama berhasil, jangan pakai yang ketiga**.

1. Cari aplikasinya di "Aplikasi" (Applications) di Finder, Control-klik ikonnya (atau klik kanan), pilih "Buka" (Open), lalu klik "Buka" sekali lagi di dialog yang muncul. Ini izin sekali saja, khusus untuk aplikasi ini.
2. Kalau menu klik kanan tidak punya "Buka" yang bisa dipakai, buka "Pengaturan Sistem" (System Settings) → "Privasi & Keamanan" (Privacy & Security) dan gulir ke bawah ke bagian Keamanan. Anda akan melihat "“Nama klien” diblokir karena bukan dari pengembang yang teridentifikasi". Klik "Tetap Buka" (Open Anyway) di sebelah kanan dan masukkan kata sandi untuk mengonfirmasi.
3. Kalau pesannya "rusak", dua langkah pertama biasanya tidak berhasil. Buka "Terminal" dan jalankan `sudo xattr -dr com.apple.quarantine` diikuti path aplikasinya (biasanya sebuah `.app` di bawah `/Applications/`), tekan Return, masukkan kata sandi login, lalu buka aplikasinya lagi. Perintah ini menghapus tanda karantina yang menandai asal unduhan.

Saat pertama dijalankan, sistem juga akan meminta kata sandi untuk mengizinkan pemasangan ekstensi jaringan. Aplikasinya baru bisa mengambil alih lalu lintas setelah Anda setuju.

Beberapa pengingat:

- Pakai perintah `xattr` **hanya untuk file yang asalnya sudah Anda periksa**; cara memeriksanya ada di bagian sebelumnya.
- **Jangan** memakai `sudo spctl --master-disable` untuk mematikan Gatekeeper secara global. Itu mematikan perlindungan seluruh komputer, sedangkan Buka lewat klik kanan hanya berlaku untuk satu aplikasi.
- Sejak macOS 15, Apple memperketat jalur Buka lewat klik kanan, dan dalam banyak kasus Anda harus lewat langkah "Pengaturan Sistem". Ini perubahan perilaku sistem, bukan masalah paket kami.
- Mac yang diberikan kantor sering dikelola dengan profil MDM, dan ketiga langkah di atas mungkin dinonaktifkan. Jangan dipaksa; pakai tiga pilihan di bawah.

## Tidak ingin mengizinkannya? Pakai salah satu dari tiga ini

Kliennya **langsung jalan di macOS dengan klik dua kali** dan tidak memunculkan pesan-pesan di atas. Akunnya sama, tanpa bayar tambahan:

- **Privat (klien Tailscale resmi)**: langsung bisa dipakai setelah dipasang, cocok dibiarkan menyala dalam jangka panjang
- **OpenVPN Connect**: file instalasi resmi dari OpenVPN; cukup impor konfigurasinya
- **Cisco Secure Client**: klien kelas perusahaan, sudah terpasang di banyak komputer kantor

## Tanya jawab

**Apakah program Anda sebenarnya mengandung virus?**
Tidak. Ini salinan tanpa modifikasi dari paket rilis resmi proyek open source aslinya. Tapi Anda tidak perlu sekadar percaya kata kami; cara memeriksanya sendiri sudah dijelaskan di atas: unggah ke VirusTotal dan lihat sebaran hasil pemeriksaan mesin-mesinnya.

**Apakah di Windows masih akan ditandai?**
Saat ini, dalam pengujian kami, pusat keamanan bawaan Windows tidak lagi menandai instalasi Hiddify. Kalau antivirus yang Anda pasang tetap menandainya, unggah dulu ke VirusTotal untuk pemeriksaan kedua, dan setelah lolos, jadikan direktori instalasi Hiddify tepercaya di antivirus itu. Jangan mematikan perlindungan real-time demi memasangnya.

**Setelah dipasang di Mac tidak mau terbuka. Apakah unduhannya rusak?**
Tidak. Aplikasinya tidak terbuka karena diblokir Gatekeeper. Atasi dengan tiga cara mengizinkan di atas.

**Perlukah memasang antivirus di Mac sekalian?**
Tidak. Yang memblokir Anda di macOS adalah Gatekeeper bawaan sistem, bukan antivirus. Memasang antivirus pihak ketiga tidak akan menghilangkan pesan ini, dan malah bisa menambah blokir baru.

**Apakah masalah ini terjadi di HP?**
Di iOS, karena dipasang dari App Store, masalah ini tidak ada. Android sesekali memperingatkan soal sumber tidak dikenal; cukup izinkan.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=troubleshooting-06) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=troubleshooting-06) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
