# 13 · WeChat, Alipay, dan Mini Program Tiongkok

## Yang Anda lihat

Anda di luar negeri, dan WeChat serta Alipay sendiri berjalan normal, tapi begitu Anda membuka **Mini Program, artikel Official Account, atau Channels** di dalamnya, yang muncul hanya ikon loading atau layar kosong:

- Anda membuka postingan Official Account dan gambarnya tidak pernah selesai dimuat
- Sebuah Mini Program macet di halaman pembuka, atau menampilkan "network error" (galat jaringan)
- Di Channels Anda bisa menggulir sampai gambar sampulnya, tapi tidak ada yang diputar saat diketuk
- Halaman Citizen Centre (pusat layanan warga), asuransi kesehatan, dan dana perumahan (housing provident fund) di Alipay tidak mau terbuka

## Penyebabnya

**Chat dan transfer** di WeChat dan Alipay berjalan lewat kanal mereka sendiri, yang bisa dipakai di seluruh dunia, sehingga Anda mengira "aplikasinya baik-baik saja".

Tetapi Mini Program, artikel Official Account, dan Channels pada dasarnya adalah **halaman web**, yang disajikan oleh server pihak ketiga, dan kebanyakan server itu hanya melayani pengguna di Tiongkok. Dengan IP luar negeri, server itu tidak memberi konten sama sekali atau sangat lambat sampai timeout.

Jadi gejalanya terbelah dengan aneh: Anda bisa chat dan menerima angpao digital (red packet), tapi tidak bisa membuka isi di dalamnya.

## Yang harus dilakukan

Pindah ke IP Tiongkok lalu buka lagi, dan semuanya jalan normal. Ada dua detail yang sering membuat orang tersandung:

**Pertama, restart aplikasinya, jangan hanya membuka ulang halamannya.** WeChat menyimpan cache "terakhir tersambung ke mana", dan me-refresh Mini Program tepat setelah ganti IP sering kali masih gagal. Menutup WeChat sepenuhnya dari latar belakang lalu masuk lagi jauh lebih sering berhasil.

**Kedua, jangan hanya mengalirkan browser lewat jalur.** Mini Program berjalan di dalam WeChat, dan cara berbentuk ekstensi browser tidak bisa menjangkaunya. Anda perlu **seluruh HP**, atau setidaknya aplikasi WeChat, lewat jalur.

## Cara mengalirkan hanya WeChat lewat jalur di HP

Klien Android dan iOS sama-sama mendukung mode "per aplikasi", tempat Anda bisa mencentang hanya WeChat dan Alipay, sementara aplikasi lain tetap di jaringan lokal. Keuntungannya:

- Aplikasi yang bergantung pada **lokasi asli** Anda, seperti pesan antar makanan, transportasi online, dan peta, tidak terpengaruh
- Menghemat baterai dan kuota
- Aplikasi bank tidak memicu manajemen risiko karena "lokasinya tiba-tiba berubah"

## Salah paham yang umum

Sebagian orang mengira Official Account yang tidak terbuka itu sudah "diblokir" atau "akunnya bermasalah", lalu berkali-kali uninstall dan instal ulang. Hampir tidak pernah itu penyebabnya: artikel yang sama langsung muncul begitu IP diganti. Cara mengujinya sederhana: minta teman di Tiongkok membuka link yang sama dan mengirimkan tangkapan layarnya. Kalau dia bisa melihatnya dan Anda tidak, masalahnya di IP.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-13) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-13) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
