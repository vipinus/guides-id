# 03 · Apa bedanya Privat (Tailscale) dengan VPN, dan kapan memakainya

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/tailscale-mesh?utm_source=github&utm_content=network-03

Bagian Privat memakai Tailscale: alat jaringan berbasis WireGuard. LeoTun menjalankan server kontrolnya sendiri, dan Anda login dengan akun Anda di situs ini. Ini berbeda dengan VPN "jenis koneksi" seperti AnyConnect dan OpenVPN.

## Tiga perbedaan

| | VPN jenis koneksi (AnyConnect / OpenVPN / Hiddify) | Privat (Tailscale) |
|---|---|---|
| Koneksi | Anda mengetuk sambungkan setiap kali, dan menyambung ulang setelah putus | Login sekali dan online terus; pulih otomatis saat ganti jaringan |
| Exit | Begitu tersambung, semua lalu lintas lewat exit | Exit bersifat opsional: kalau tidak dipilih, lalu lintas internet umum keluar lewat jaringan lokal dan hanya lalu lintas antarperangkat di dalam jaringan privat yang dienkripsi; baru kalau Anda memilih exit sebuah wilayah, fungsinya setara dengan VPN |
| Akses antarperangkat | Tidak ada | HP, komputer, dan NAS dalam satu akun bisa saling menjangkau langsung, tanpa port forwarding atau IP publik |

## Kapan sebaiknya memakainya

- Perangkatnya banyak, dan Anda ingin mengatur sekali lalu online terus.
- Ada NAS, komputer, atau kamera di rumah yang ingin diakses dari luar: login ke Privat di kedua sisi lalu sambungkan langsung lewat nama perangkat, seolah-olah di LAN yang sama.
- Perangkat yang harus tersambung dalam waktu lama: tidak ada batas waktu sesi.

## Kapan cara lain lebih cocok

- Anda hanya ingin memakainya sekali, sementara: mengimpor Hiddify lewat kode QR atau memasang AnyConnect lebih cepat.
- Perangkatnya sudah menjalankan VPN kantor atau software jaringan lain: keduanya berebut DNS dan rute, dan gejalanya pemberitahuan hak cipta saat menonton video Tiongkok dan intranet kantor yang tidak bisa dibuka. Pakai cara yang hanya memengaruhi browser, seperti Proxy Web.
- Jaringan kampus / kantor yang membatasi UDP: WireGuard berjalan di atas UDP dan hanya bisa mengandalkan relay, yang lambat; pindah ke AnyConnect.

## Masa aktif dan jumlah perangkat

Masa berlaku login sebuah perangkat mengikuti tanggal berakhir akun; perangkat offline dalam beberapa menit setelah masa aktif habis, dan Anda cukup login lagi setelah memperpanjang. Jumlah perangkat yang online bersamaan tergantung paket (Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat), dan jatahnya dibagi dengan cara koneksi lain; kalau jumlah yang online bersamaan melebihi batas paket, Anda bisa menaikkan paket akun sementara (sisa masa aktif dikonversi senilai menurut harga) lalu kembali lagi setelah selesai.

Langkah instalasi dan login ada di [Panduan klien 05](../client/05-tailscale-private-network.md).

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=network-03) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=network-03) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
