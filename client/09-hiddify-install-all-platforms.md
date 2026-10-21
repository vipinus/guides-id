# 09 · Memasang Hiddify di semua platform: Windows, macOS, Linux, Android, iOS

Klien yang dipakai di bagian Hiddify situs ini adalah Hiddify yang open source, dengan inti sing-box di dalamnya, jadi setelah terpasang tidak ada lagi yang perlu diatur. Kelima platform memakai aplikasi yang sama, tetapi hambatan saat pertama dibuka berbeda-beda: di Windows bisa diblokir atau dihapus antivirus, di Mac bisa muncul pesan aplikasi "rusak" dan Anda juga harus mengizinkan ekstensi jaringan, di Linux Anda harus menjalankan perintah otorisasi dulu supaya mode VPN jalan, dan di iPhone aplikasinya tidak ada di App Store wilayah Tiongkok. Artikel ini membahas, untuk tiap platform, tempat mengunduh, cara memasang, dan apa yang perlu dilakukan saat pertama dibuka, lalu ditutup dengan langkah tersingkat untuk mengimpor langganan dan tersambung.

## Tempat mengunduh

| Platform | Penginstal | Tempat mendapatkannya |
|---|---|---|
| Windows | Penginstal (.exe), hanya x64 | Bagian unduhan di halaman Hiddify |
| macOS | .dmg, satu paket untuk Apple silicon dan Intel | Bagian unduhan di halaman Hiddify |
| Linux | .deb (keluarga Debian / Ubuntu), hanya x64 | Bagian unduhan di halaman Hiddify |
| Android | .apk, dua versi: ARM64 dan x86-64 | Bagian unduhan di halaman Hiddify, atau Google Play |
| iPhone / iPad | Hiddify Proxy & VPN di App Store | App Store; butuh Apple ID wilayah selain Tiongkok |

Bagian unduhan di halaman Hiddify otomatis menyarankan paket untuk sistem yang sedang Anda pakai, dan paket untuk sistem lain tercantum di bawahnya. Di samping setiap baris juga ada ikon "Situs resmi" yang mengarah ke halaman rilis resmi Hiddify, jadi Anda bisa membandingkan versinya. Ketiga sistem desktop (Windows, macOS, Linux) juga punya video tutorial.

Penginstal desktop adalah salinan apa adanya dari paket rilis resmi Hiddify, tidak diubah atau dikemas ulang. Sebelum mengizinkannya, Anda bisa memeriksanya sendiri: unggah penginstalnya ke VirusTotal dan lihat hasilnya; caranya ada di [Pemecahan masalah 06](../troubleshooting/06-antivirus-false-positive.md).

## Windows

1. Unduh penginstal dari bagian unduhan di halaman Hiddify lalu klik dua kali untuk memasang. (Dalam uji kami saat ini, Keamanan Windows tidak menandainya; kalau antivirus yang Anda pasang menandainya, lihat Tanya jawab di akhir [Pemecahan masalah 06](../troubleshooting/06-antivirus-false-positive.md).)

## macOS

1. Unduh .dmg dari bagian unduhan di halaman Hiddify, buka, lalu seret Hiddify ke "Aplikasi".
2. Di "Finder" → "Aplikasi", tahan Control dan klik ikon Hiddify, pilih "Buka", lalu klik "Buka" sekali lagi di dialog.
3. Kalau masih tidak bisa dibuka: "Pengaturan Sistem" → "Privasi & Keamanan", klik "Tetap Buka" di bagian "Keamanan" dan masukkan kata sandi untuk konfirmasi.
4. Kalau muncul pesan aplikasi "rusak dan tidak bisa dibuka": file-nya tidak rusak; Gatekeeper sistem yang memblokirnya. Buka "Terminal", jalankan perintah di bawah, tekan Return dan masukkan kata sandi login, lalu buka Hiddify lagi:

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Perintah ini hanya menghapus tanda karantina yang menandai file sebagai hasil unduhan, dan hanya berlaku untuk aplikasi ini. **Jangan** memakai `sudo spctl --master-disable` untuk mematikan Gatekeeper di seluruh komputer.

Saat pertama kali Anda klik sambungkan setelah memasang, sistem juga akan meminta izin untuk "ekstensi jaringan". Kalau langkah ini dilewati, ikonnya terus berputar dan tidak pernah tersambung:

- **macOS 15 Sequoia dan yang lebih baru**: "Pengaturan Sistem" → "Umum" → "Item Login & Ekstensi", gulir ke "Ekstensi" di bagian bawah, ubah tampilan ke "Menurut Kategori", klik ⓘ di samping "Ekstensi Jaringan", nyalakan sakelar untuk Hiddify, lalu masukkan kata sandi atau pakai sidik jari saat diminta.
- **macOS 13 Ventura / 14 Sonoma**: buka Hiddify dulu dan klik sambungkan sekali, sampai muncul "Ekstensi Sistem Diblokir"; lalu buka "Pengaturan Sistem" → "Privasi & Keamanan", gulir ke bawah sampai "Perangkat lunak sistem dari pengembang … diblokir untuk dimuat", klik "Izinkan" dan masukkan kata sandi.

Di Mac milik kantor, kalau tombol-tombol ini berwarna abu-abu, artinya dikunci oleh kebijakan manajemen perangkat; tanyakan ke bagian IT, atau pakai klien Cisco, OpenVPN, atau Privat sebagai gantinya.

## Linux

1. Unduh .deb dari bagian unduhan di halaman Hiddify lalu klik dua kali untuk memasangnya lewat pusat perangkat lunak, atau buka terminal di folder unduhan dan jalankan (Debian, Ubuntu, dan turunannya):

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Kalau langsung disambungkan setelah dipasang, muncul "operation not permitted" dan mode VPN tidak mau jalan, karena deb resmi tidak membawa izin ini setelah terpasang. Buka terminal dan jalankan perintah di bawah untuk memberi izin pada Hiddify, lalu buka ulang Hiddify:

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Jalankan lagi setiap kali Hiddify diperbarui**: izinnya melekat pada file program, dan pembaruan mengganti file itu, sehingga izinnya hilang.

Paket deb-nya untuk x64; di perangkat Linux ARM pakai OpenVPN, dengan akun yang sama.

## Android

1. Unduh .apk dari bagian unduhan di halaman Hiddify. Halaman itu otomatis menyarankan arsitektur untuk HP Anda; sebagian besar HP memakai ARM64. Kalau Anda bisa memakai Google Play, Anda juga bisa memasangnya langsung dari sana.
2. Kalau saat memasang muncul peringatan soal "sumber tidak dikenal" atau dari aplikasi keamanan, izinkan saja.
3. Saat pertama kali mengetuk sambungkan, sistem meminta izin VPN; ketuk izinkan.

## iPhone / iPad

1. Cari "Hiddify" di App Store lalu pasang; gratis.
2. Kalau tidak ketemu, atau muncul "Aplikasi ini saat ini tidak tersedia di negara atau wilayah Anda": di iOS, pasang dari App Store dengan Apple ID wilayah selain Tiongkok (Hiddify ada di App Store Amerika Serikat, Hong Kong, Taiwan, Jepang, dan Singapura). Kami sarankan mendaftar Apple ID baru: di App Store, ketuk "Dapatkan" pada aplikasi gratis apa saja → "Buat Apple ID Baru", pilih wilayah seperti Hong Kong atau Amerika Serikat, dan pilih "Tidak Ada" sebagai metode pembayaran. Anda hanya berganti akun di App Store, iCloud tidak terpengaruh. Langkah lengkapnya ada di [06 · Kalau iOS tidak mengizinkan Anda memasang aplikasi](06-ios-app-store.md).
3. Saat pertama kali mengetuk sambungkan, sistem meminta izin VPN; ketuk izinkan.

**Jangan** memakai Apple ID pinjaman dari orang lain; pemiliknya bisa mengunci perangkat Anda dari jauh.

## Setelah terpasang: impor langganan dan sambungkan

1. Login ke situs lalu buka halaman Hiddify.
2. Klik bendera wilayah yang Anda inginkan dan kode QR akan muncul; atau klik "Impor semua wilayah · pilih otomatis" di bagian atas halaman untuk mengimpor semua wilayah di luar Tiongkok sekaligus dan biarkan klien memilih sendiri. **Wilayah Tiongkok diimpor terpisah**: untuk menonton video atau memakai mobile banking Tiongkok dari luar negeri, klik bendera Tiongkok untuk mengimpornya.
3. Di bawah kode QR ada tiga tombol, dikelompokkan menurut jenis langganan. Hiddify memakai tombol pertama (bertuliskan Hiddify / sing-box / GUI.for.SingBox / Karing, dengan subjudul "langganan sing-box"), dan tombolnya sama di HP maupun komputer. HP: ketuk tombolnya, lalu pindah ke Hiddify dan tambahkan sesuai petunjuk, atau pindai kodenya dengan Hiddify di perangkat lain. Komputer: klik untuk menyalin alamat https://, lalu di Hiddify klik "+" → "Add from clipboard" (tambah dari clipboard).
4. Klik sambungkan.

Perbedaan ketiga tombol, cara mengimpor ke Clash dan klien lain, serta apakah langganan bisa kedaluwarsa dijelaskan di [02 · Cara mengimpor link langganan (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md). Kalau sudah diimpor tapi tidak bisa tersambung, lihat [Pemecahan masalah 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Tanya jawab

**Apakah penginstalnya kalian ubah?** Tidak. Penginstal desktop adalah salinan apa adanya dari paket rilis resmi Hiddify. Setiap baris di halaman Hiddify punya link ke halaman rilis resmi, jadi Anda bisa membandingkan versinya sendiri, dan Anda juga bisa mengunggah file-nya ke VirusTotal untuk memastikan.


**Saya sudah menjalankan perintah xattr di Mac tapi tetap tidak tersambung?** Kemungkinan besar "ekstensi jaringan" belum diizinkan; ikuti bagian macOS di atas dan nyalakan sakelar Hiddify di Pengaturan Sistem.

**Setelah Hiddify di Linux diperbarui, mode VPN tidak jalan lagi?** Itu wajar; jalankan perintah otorisasi sekali lagi setelah pembaruan.

**Bisakah dipakai di komputer Windows atau Linux ARM?** Bisa, dengan cara koneksi lain seperti OpenVPN, dengan akun yang sama; paket desktop Hiddify saat ini hanya x64.

**Tidak mau repot dengan langkah-langkah izin?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect), dan Privat (Tailscale) semuanya langsung terbuka dengan klik dua kali; tidak ditandai antivirus, Mac tidak menyebutnya "rusak", dan akunnya sama.

## Bacaan lanjutan

- [Halaman Hiddify: unduhan klien dan kode QR untuk tiap wilayah](https://www.leotun.com/id/singbox?utm_source=github&utm_content=client-09)
- [Cara mengimpor link langganan (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/id/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [Klien ditandai antivirus / Mac bilang rusak: periksa dulu, baru izinkan](https://www.leotun.com/id/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [Apa itu izin "ekstensi jaringan" di macOS dan cara mengizinkannya](https://www.leotun.com/id/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [Kalau iOS tidak mengizinkan Anda memasang aplikasi](https://www.leotun.com/id/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-09) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-09) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
