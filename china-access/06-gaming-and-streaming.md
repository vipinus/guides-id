# 06 · Game server Tiongkok dan siaran langsung

## Game: bisa login, tapi latensinya tinggi

Sebagian besar game server Tiongkok tidak memblokir IP luar negeri; masalahnya ada di latensi. Kalau Anda berada di Eropa atau Amerika Utara, jarak fisik ke server di Tiongkok sudah memberi latensi dasar yang tetap, ditambah jitter dan packet loss di jalur lintas negara, yang terasa sebagai lag dan putus sambungan.

Yang dilakukan "akselerator" adalah mengirim lalu lintas Anda lewat jalur yang lebih baik ke Tiongkok, sehingga rutenya tidak berputar-putar dan paket yang hilang berkurang. Koneksi yang naik turun dan sering kehilangan paket menjadi stabil, dan untuk sebagian besar game itulah bedanya antara bisa dimainkan atau tidak.

## Cara memilih titik masuk

Wilayah yang Anda pilih adalah negara tempat lalu lintas keluar: untuk game server Tiongkok, pilih **wilayah Tiongkok**, sehingga yang terlihat adalah IP Tiongkok. Jangan pilih wilayah seperti Jerman atau Prancis yang tidak mendukung UDP; lewat wilayah itu game hampir pasti tidak bisa tersambung. Coba beberapa, lalu nilai dari latensi yang ditampilkan di dalam game.

## Memilih protokol

Game sensitif terhadap packet loss, jadi utamakan protokol berbasis UDP dan hindari wilayah yang tidak mendukung UDP. Protokol berbasis TCP mengirim ulang paket yang hilang, sehingga latensinya melonjak tajam.

## Siaran langsung

Douyin, Kuaishou, Douyu, dan Huya membatasi IP luar negeri dengan cara yang berbeda-beda; sebagian besar tetap bisa ditonton, tapi resolusinya dibatasi. Dengan IP Tiongkok, semua pilihan resolusi terbuka. Siaran langsung adalah lalu lintas bitrate tinggi yang terus-menerus, jadi pilih titik masuk dengan bandwidth yang lega.

## Verifikasi nama asli

Game server Tiongkok mewajibkan verifikasi identitas dengan nama asli. Ini syarat di tingkat akun yang tidak ada hubungannya dengan IP, dan mengganti IP tidak menyelesaikannya.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-06) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-06) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
