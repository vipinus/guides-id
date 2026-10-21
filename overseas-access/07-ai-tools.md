# 07 · Mengakses alat AI (ChatGPT, Claude, Gemini, dan lainnya)

## Yang Anda lihat

Saat membuka situs-situs ini dari dalam Tiongkok, gejalanya bermacam-macam, sehingga mudah salah menilai:

| Gejala | Penyebab yang paling mungkin |
|---|---|
| Halaman sama sekali tidak terbuka | Tidak bisa dijangkau di tingkat jaringan |
| Halaman terbuka, tapi login macet | Layanan pihak ketiga yang dipakai untuk login tidak bisa dijangkau |
| Bisa mengobrol, tapi langsung terputus begitu mengirim pesan panjang | Koneksinya tidak stabil |
| Pesan "tidak tersedia di negara Anda" | Penyedia menolak berdasarkan IP |
| Pesan bahwa akun diblokir atau perlu verifikasi | Lihat "Hal terpenting" di bawah |

## Hal terpenting: stabil lebih penting daripada cepat

Layanan-layanan ini sangat peka terhadap **IP yang sering berganti**. Kalau koneksi Anda sebentar keluar lewat Jepang lalu sebentar lewat Amerika Serikat, yang dilihat penyedia adalah "akun yang sama melintasi beberapa negara dalam beberapa menit", yang mudah memicu manajemen risiko: paling ringan Anda diminta verifikasi ulang, paling berat akunnya diblokir.

Jadi saat memakai alat AI:

- **Pilih satu wilayah dan tetap di situ**; jangan sering berganti
- Usahakan pendaftaran dan pemakaian sehari-hari ada di **wilayah yang sama**
- Kalau Anda mendaftar lewat Amerika Serikat, terus pakai Amerika Serikat sejak itu

Ini jauh lebih penting daripada "wilayah mana yang lebih cepat". Kecepatan yang sedikit lebih rendah hanya berarti menunggu sedikit lebih lama; masalah pada akun berarti mulai dari awal.

## Wilayah mana yang dipilih

Jepang dan Singapura dekat dan latensinya rendah, sehingga paling nyaman untuk mengobrol sehari-hari. Tapi ada dua hal yang perlu diperhatikan:

- Ketersediaan sebagian layanan berbeda per wilayah, jadi sebelum mendaftar, pastikan layanannya terbuka normal dari wilayah itu
- Kalau fitur yang Anda inginkan melibatkan pembayaran, negara asal metode pembayaran Anda sebaiknya tidak bertentangan dengan wilayah yang Anda pilih

Kalau ragu, pakai uji coba gratis untuk membuka setiap layanan yang akan Anda pakai dan lihat hasilnya, lalu putuskan wilayah mana yang dipakai jangka panjang.

## Routing per aplikasi di klien sangat berguna

Alat AI biasanya dipakai di browser atau di aplikasi tersendiri. Masukkan aplikasi itu ke daftar yang lewat jalur, dan biarkan aplikasi lain tetap di jaringan lokal. Keuntungannya:

- Aplikasi pesan antar makanan, transportasi online, dan pembayaran Tiongkok tidak terpengaruh
- Wilayah Anda tidak "ikut berganti" karena aplikasi lain
- Menghemat kuota

## Baris perintah dan API

Kalau Anda memanggil API lewat alat baris perintah atau kode, perhatikan bahwa program-program itu **belum tentu membaca proxy sistem**. Untuk kasus itu lihat [05 · Linux dan baris perintah](05-linux-server.md).

## Pengingat

Jangan menempelkan rahasia perusahaan, data pelanggan, atau kode yang belum dirilis ke layanan-layanan ini. Ini tidak ada hubungannya dengan jalur mana yang Anda pakai; begitu konten terkirim, konten itu ada di server pihak lain.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-07) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-07) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
