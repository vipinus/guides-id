# 02 · Apakah Cisco AnyConnect bisa dipakai di Tiongkok

> Versi situs web (lebih lengkap): https://www.leotun.com/id/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Bisa. AnyConnect adalah protokol VPN perusahaan buatan Cisco. Perusahaan di seluruh dunia mengandalkannya untuk kerja jarak jauh, dan cabang perusahaan asing di Tiongkok memakainya setiap hari, jadi biaya untuk melarangnya sama sekali terlalu tinggi. **Yang sebenarnya diblokir adalah alamat server tertentu, bukan protokolnya.** Jadi "bisa atau tidak" tergantung apakah penyedianya punya cukup banyak alamat dan menggantinya dengan cukup cepat.

## Kenapa lebih tahan blokir daripada aplikasi VPN buatan sendiri

| | AnyConnect | Aplikasi VPN buatan sendiri |
|---|---|---|
| Ciri lalu lintas | TLS standar, sama seperti membuka situs HTTPS | Protokol sendiri, dengan ciri yang tetap |
| Begitu dikenali | Hanya alamat itu yang tidak bisa tersambung | Seluruh aplikasi berhenti bekerja |
| Klien | Diterbitkan Cisco; alternatif open source OpenConnect ada di semua platform | Hilang begitu dihapus dari toko aplikasi |

LeoTun menjalankan mesin sendiri di 24 wilayah. Kalau sebuah alamat ditandai, alamat itu diganti yang baru, nama domainnya diarahkan ulang otomatis, dan alamat yang tersimpan di klien Anda tidak perlu diubah.

## Cara memasang

1. Unduh installer untuk sistem Anda dari halaman Cisco di situs. Windows 10 ke atas, macOS, iOS, Android, dan Linux semuanya tersedia; Windows 7/8 hanya bisa memakai versi 4.9, versi terakhir yang mendukungnya.
2. Buka klien dan masukkan alamat server di kolom alamat; di situs, klik bendera wilayah untuk menyalinnya.
3. Masukkan akun dan kata sandi lalu sambungkan. Tidak perlu file sertifikat, dan tidak perlu mengimpor konfigurasi.
4. Begitu muncul "Connected" (tersambung), cek IP exit Anda.

## Kalau tidak mau tersambung, periksa dengan urutan ini

1. **Ganti ke wilayah lain.** Kalau wilayah lain bisa tersambung, hanya server itu yang sementara tidak bisa dijangkau.
2. **Ganti jaringan.** Kalau internet rumah gagal, pindah ke data seluler, dan sebaliknya; gangguan di operator yang berbeda tidak terjadi bersamaan.
3. **Baca pesan error-nya.** `Login failed` berarti akun atau kata sandi salah, atau masa aktif habis; `Untrusted server certificate` kemungkinan besar karena jam sistem salah atau jaringan yang sedang dipakai mencegat TLS, jadi ganti jaringan; hanya `Connection attempt has failed` yang berarti alamatnya tidak bisa dijangkau.
4. **Perbarui klien.** Ini terutama penting setelah upgrade besar sistem operasi.
5. **Ganti cara koneksi.** Akun yang sama bisa memakai OpenVPN atau Hiddify untuk tersambung ke server yang sama, dan pemblokiran ketiga protokol tidak saling bergantung; lihat [02 · Cara koneksi mana yang cocok untuk situasi apa](../network/02-choose-your-connection-method.md).

## Memperbarui Cisco AnyConnect

Cisco sudah mengganti namanya menjadi Cisco Secure Client; cara pakainya sama. Tidak perlu uninstall dulu: pasang versi baru di atas versi lama, dan alamat yang tersimpan tetap ada. Di HP, perbarui lewat App Store / Google Play; kalau pencarian di toko tidak menemukannya, pakai OpenConnect yang open source, yang memakai protokol dan akun yang sama (untuk mengganti wilayah App Store di iOS, lihat [Klien 06](../client/06-ios-app-store.md)).

## Tanya jawab

**Apakah lambat berarti sedang dibatasi kecepatannya?** Ganti wilayah dulu: lihat lampu merah, kuning, dan hijau di daftar wilayah di situs, lalu pilih yang hijau. Kalau masih lambat, penyebab biasanya internet lokal: internet bersama di kompleks perumahan, atau operator dan wilayah yang tidak cocok (China Unicom di utara: Jepang atau Korea; China Telecom di selatan: Asia Tenggara atau Australia; penyedia lain: titik masuk Tiongkok).

**Kenapa alamat yang sama kadang bagus, kadang jelek?** Alamatnya berupa nama domain, dan mesin di baliknya diganti otomatis sesuai pemblokiran dan beban. Tunggu satu atau dua menit lalu coba lagi; biasanya Anda kebetulan mencoba di tengah pergantian.

**Apakah koneksi putus sendiri setelah tersambung lama?** Bukan karena waktu. Saat akun kedaluwarsa, server memutus koneksi Anda; perpanjang lalu sambungkan ulang.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-02) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-02) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
