# 05 · Privat (Tailscale): memasang, login ke server kontrol situs ini, memilih exit

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/tailscale-mesh?utm_source=github&utm_content=client-05

Bagian jaringan Privat memakai Tailscale (alat jaringan yang dibangun di atas WireGuard). LeoTun menjalankan server kontrolnya sendiri, dan Anda login dengan **akun Anda di situs ini**, yang tidak ada hubungannya dengan akun Tailscale resmi. Login sekali dan perangkat tetap online; wilayah exit bisa diganti dari menu kapan saja. Apa bedanya dengan VPN dan untuk siapa cocoknya, lihat [Panduan jaringan 03](../network/03-private-network-vs-vpn.md).

## Memasang

| Platform | Tempat mengunduh |
|---|---|
| Windows / macOS / Linux / Android | Bagian unduhan di [halaman Privat situs web](https://www.leotun.com/id/mesh?utm_source=github&utm_content=client-05) (disediakan langsung oleh situs ini, tidak perlu ke situs resmi) |
| iPhone / iPad | App Store; butuh Apple ID wilayah selain Tiongkok (lihat [Klien 06](06-ios-app-store.md)) |

## Login

1. **Logout dulu dari akun resmi** (kalau pernah login): di HP, ketuk avatar → Log Out; di komputer, jalankan `tailscale logout`. Selama belum logout sepenuhnya, opsi yang dibutuhkan di langkah berikutnya tidak muncul.
2. **Arahkan login ke situs ini**:
   - HP: di layar yang belum login, ketuk "⋯" di kanan atas → Use custom server (pakai server khusus; di sebagian versi namanya Use an alternate server), masukkan alamat yang tertera di halaman Privat situs web, lalu ketuk Log in.
   - Windows / Linux: salin perintah `tailscale up --login-server=…` dari halaman situs web dan jalankan di PowerShell / terminal.
   - macOS: **jangan klik Log in**. Di jendela Tailscale, klik panah di baris akun → Account Settings… → Accounts → panah kecil di samping "Add Account…" → Add Account Using Alternate Server (tambah akun dengan server alternatif), tempel alamatnya, lalu klik Add Account….
3. Browser otomatis membuka halaman login situs ini; konfirmasi dengan akun Anda di situs ini. Saat kembali ke klien, perangkat sudah online.

## Memilih exit

- HP: menu → Exit Node, pilih wilayah; langsung berlaku.
- Komputer: ikon di tray / menu bar → submenu Exit Node; atau `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` menampilkan pilihan yang tersedia).
- Kalau tidak ingin memakai exit, pilih None (tidak ada) (di baris perintah, kosongkan nilai setelah tanda sama dengan). Hanya satu exit yang bisa dipakai pada satu waktu.

## Masa aktif dan jumlah perangkat

- Masa berlaku login sebuah perangkat mengikuti tanggal berakhir akun, dan perangkat offline dalam beberapa menit setelah masa aktif habis; setelah diperpanjang, cukup login sekali lagi. Tidak perlu memasang ulang.
- Jumlah perangkat yang online bersamaan tergantung paket Anda (Pribadi 2, Keluarga 4, Perusahaan 8), dan jatahnya berbagi dengan cara koneksi lain; kalau melebihi batas paket, Anda bisa menaikkan paket akun sementara (sisa masa aktif dikonversi senilai menurut harga) lalu kembali lagi setelah selesai.

## Dua kasus yang lebih cocok memakai cara lain

- Ada VPN lain yang berjalan di perangkat yang sama (AnyConnect kantor, software mesh networking lain): keduanya berebut DNS dan rute. Inilah penyebab munculnya pemberitahuan hak cipta saat menonton video Tiongkok dan intranet kantor yang tidak bisa dibuka.
- Di jaringan kampus / kantor yang membatasi UDP: WireGuard berjalan di atas UDP, jadi terpaksa lewat relay, yang sangat lambat; pindah ke AnyConnect.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=client-05) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=client-05) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
