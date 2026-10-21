# 01 · Memulai dengan router yang sudah terpasang firmware

## Tiga langkah setelah dikeluarkan dari kotak

1. **Colokkan listrik dan kabel jaringan**: sambungkan port WAN router ke modem atau router utama yang sudah ada, lalu tunggu sampai lampu indikatornya stabil, sekitar satu menit.
2. **Sambungkan ke Wi-Fi**: nama dan kata sandi Wi-Fi bawaan tercetak di kartu petunjuk (bawaan pabrik keduanya adalah nama domain situs). Setelah tersambung, buka browser dan masuk ke alamat admin `http://192.168.11.1`.
3. **Login ke akun Anda**: di halaman admin, masukkan email akun dan kata sandi lalu simpan (akun Pribadi, Keluarga, dan Perusahaan semuanya bisa memakai router). Sejak itu, setiap perangkat yang tersambung ke Wi-Fi ini otomatis lewat VPN.

## Ganti kata sandi bawaan

Kata sandi admin dan kata sandi Wi-Fi bawaan pabrik itu diketahui umum, jadi ganti segera setelah login: halaman admin → System → Administration (kata sandi admin); Wireless → Interfaces → Wireless Security (keamanan nirkabel).

## Mode split routing

Bawaannya adalah split routing: domain Tiongkok yang ada di daftar lewat VPN, dan sisanya tersambung langsung. Mode ini paling cocok kalau Anda di luar negeri dan menonton video Tiongkok, atau kalau anggota keluarga lansia memakai TV. Kalau Anda di Tiongkok dan memilih wilayah luar negeri, arahnya berbalik otomatis: secara bawaan hanya situs dan layanan yang diblokir yang lewat VPN, sedangkan situs Tiongkok serta situs asing yang memang bisa dibuka dari Tiongkok tersambung langsung; lihat [03 · Apa itu split routing di router](03-router-split-routing.md). Kalau sementara Anda perlu semuanya lewat VPN, pindah ke "Global" lalu kembalikan setelah selesai.

## Tanya jawab

- **Lampu indikator normal tapi perangkat yang tersambung tidak dapat internet**: cek status akun di halaman admin; akun yang kedaluwarsa atau kata sandi yang salah sama-sama akan terlihat di sana.
- **Anda ingin beralih ke router lain**: lepas tautan router lama di situs web dulu; lihat [Penautan MAC dan mengganti router](05-mac-binding-and-replacing.md).

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=router-01) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=router-01) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
