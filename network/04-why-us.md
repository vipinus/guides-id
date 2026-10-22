# 04 · Apa bedanya kami dengan VPN lain

VPN di pasaran kira-kira terbagi tiga jenis: merek internasional besar yang menyasar pengguna di seluruh dunia, penyedia jalur proxy yang dikenal di kalangan berbahasa Mandarin dengan sebutan "jichang" (langganan proxy yang dijual ulang), dan bermacam-macam software gratis. LeoTun menjalankan server sendiri sejak 2006 dan hanya mengerjakan satu hal: menjaga koneksi tetap stabil di kedua arah, bagi pengguna di Tiongkok daratan maupun bagi orang yang tinggal di luar Tiongkok dan perlu mengakses layanan Tiongkok. Artikel ini membandingkan kami dengan ketiga jenis produk itu poin demi poin, menunjukkan cocoknya untuk siapa dan bagaimana kami bekerja, supaya Anda bisa melihat dengan jelas sebelum membayar.

## Posisi kami dalam satu kalimat

Kami adalah layanan yang **dioptimalkan khusus untuk kondisi jaringan di Tiongkok daratan**, bukan penjual ulang jalur internasional. Kualitas jalur internasional China Telecom, China Unicom, dan China Mobile sangat berbeda; kami menyetelnya untuk tiap operator secara terpisah dan memberi rekomendasi wilayah yang berbeda pula. Kami punya node pendaratan di dalam Tiongkok, sehingga pengguna dengan internet rumah yang biasa-biasa saja pun punya titik masuk yang stabil. Kami terus menyesuaikan port dan protokol mengikuti perubahan kondisi jaringan di Tiongkok, bukan memasangnya sekali lalu dibiarkan.

Sebaliknya, kalau Anda berada di luar Tiongkok dan perlu mengakses layanan di Tiongkok, cukup pilih wilayah Tiongkok dengan akun yang sama: situs Tiongkok diakses dari IP Tiongkok, sedangkan situs di luar Tiongkok tetap keluar di luar Tiongkok. Mengakses Tiongkok dari luar negeri dan mengakses layanan luar negeri dari Tiongkok adalah dua arah dari hal yang sama.

## Dibandingkan merek internasional besar

- Kelebihan mereka: puluhan negara di seluruh dunia, ribuan server, aplikasi yang matang, klaim tanpa log yang diaudit pihak independen. Kalau Anda di Eropa atau Amerika dan hanya butuh enkripsi di Wi‑Fi publik atau ingin menonton layanan streaming negara lain, mereka pilihan yang baik.
- Kekurangan mereka: produknya tidak dirancang untuk jaringan Tiongkok. Ciri protokol buatan sendiri itu tetap, dan begitu dikenali di dalam Tiongkok, seluruh aplikasinya berhenti bekerja; mereka tidak punya node pendaratan di dalam Tiongkok, jadi untuk menonton video Tiongkok dari luar negeri, fiturnya tidak ada atau memakai IP Hong Kong atau Taiwan, yang tetap diblokir Tencent Video dan iQIYI.
- Yang kami lakukan: hanya memakai protokol standar (AnyConnect, OpenVPN, Hiddify, Tailscale, proxy web HTTPS), dengan klien dari vendornya atau dari komunitas open source. Yang bisa diblokir hanya alamat tertentu, dan cukup ganti alamat; kliennya tidak akan ikut tumbang.
- Kompromi kami: 24 wilayah, masing-masing didukung beberapa mesin, dan yang paling sepi dipilih otomatis saat Anda tersambung; kliennya rilis resmi dari vendor dan komunitas open source, diatur dengan memindai kode QR atau impor sekali klik; tidak ada laporan audit pihak ketiga; apa yang kami catat dan tidak kami catat tertulis di halaman Tentang kami, dan kami mengandalkan penjelasan yang terang, bukan cap pengesahan.

## Dibandingkan penyedia jalur proxy

- Kelebihan penyedia jalur proxy: murah, node-nya banyak, langsung bisa dipakai begitu link langganan ditempel, dan orang yang suka mengutak-atik klien menikmati kebebasannya.
- Kekurangan penyedia jalur proxy: kebanyakan perorangan atau tim kecil yang menyewa mesin di luar negeri lalu menjual ulang kuota, tanpa titik pendaratan sendiri di Tiongkok, dan kualitas exit-nya naik turun mengikuti jalur yang disewa; kabur membawa uang, ganti nama, dan tutup itu hal biasa, dan membayar setahun bukan jaminan bisa memakai setahun penuh; urusan klien hampir seluruhnya diserahkan ke pengguna, dan tidak ada yang bertanggung jawab kalau ada masalah.
- Yang kami lakukan: mesinnya milik kami sendiri, dan exit Tiongkok adalah mesin kami sendiri yang terdaftar atas nama asli di penyedia cloud Tiongkok daratan; satu akun punya enam cara koneksi, dan solusi router untuk semua perangkat serta grup dukungan 24 jam tidak dimiliki penyedia jalur proxy; kami beroperasi sejak 2006 sampai sekarang, dan akun, masa aktif, serta harga tidak berubah sebelum maupun sesudah ganti nama.
- Harga kami: paket Pribadi $5 per bulan, paket Keluarga $10, paket Perusahaan $20, sudah mencakup mesin milik sendiri, enam cara koneksi, dan grup dukungan 24 jam; Anda hanya memilih wilayah, dan di balik tiap wilayah sistem memilih mesin yang paling sepi, jadi tidak perlu tes kecepatan dan memilih node sendiri.

## Dibandingkan software gratis

- Kelebihan yang gratis: tidak bayar, dan cukup untuk sesekali mencari sesuatu.
- Kekurangan yang gratis: bandwidth exit di Tiongkok daratan dibayar menurut pemakaian, jadi layanan gratis hanya bisa bertahan dengan menjejalkan pengguna, membatasi kecepatan, atau menjual data; yang berbentuk ekstensi browser hanya mem-proxy permintaan web, sedangkan video, aplikasi, dan DNS sistem tidak lewat situ; installer yang asal-usulnya tidak jelas sudah merupakan risiko tersendiri, lihat "Cara mengenali aplikasi VPN yang berisiko".
- Yang kami lakukan: uji coba gratis 4 jam tanpa kartu kredit, untuk mengecek barangnya; bayar per hari (kredit) untuk pengguna sesekali; kalau teman yang Anda undang membayar, Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), sumber waktu gratis jangka panjang.
- Cara kami mengaturnya: waktu gratis datang dari uji coba 4 jam dan hadiah undangan; untuk pemakaian jangka panjang Anda membayar per bulan, per tahun, atau per hari.

## Enam cara koneksi, satu akun

Privat (Tailscale): login sekali dan online terus, ganti wilayah dari menu. Cisco AnyConnect: kompatibilitas terbaik, sudah ada di sistem atau dengan klien resmi. OpenVPN: untuk router, NAS, dan Linux. Proxy Web: hanya browser yang lewat situ, dan dari desainnya tidak ada koneksi yang bisa putus. Hiddify: tahan terhadap packet loss, dengan kecepatan terbaik. Router: akses untuk semua perangkat, termasuk TV, set-top box, dan perangkat anggota keluarga lansia.

Setiap jaringan punya cara yang paling cocok, jadi Anda mendapat keenamnya: dengan akun yang sama Anda bisa berganti kapan saja, dari Hiddify ke AnyConnect kalau jaringan kampus membatasi UDP, atau ke Proxy Web kalau internet rumah sedang tidak stabil. Cara memilihnya ada di "Cara koneksi mana yang cocok untuk situasi apa".

## Aturan akun

- Akun punya tiga paket, Pribadi, Keluarga, dan Perusahaan, dengan masing-masing 2, 4, dan 8 perangkat online bersamaan; wilayah, kuota, dan cara koneksi sama di ketiganya. Jumlah perangkat tempat Anda memasang tidak dibatasi, yang dibatasi hanya jumlah koneksi bersamaan. Kalau jumlah yang online bersamaan melebihi batas paket, Anda bisa menaikkan paket akun sementara (sisa masa aktif dikonversi senilai menurut harga) lalu kembali lagi setelah selesai.
- Anda bisa berganti di antara ketiga paket kapan saja, dengan sisa masa aktif dikonversi senilai (Keluarga dan Perusahaan masing-masing 2 kali dan 4 kali harga Pribadi); ketiga paket mendukung router, dan paket Pribadi sudah cukup untuk satu orang.
- Refund dihitung proporsional menurut waktu yang sudah dipakai, bisa diminta kapan saja, dan diproses manual; tidak ada janji kapan dananya tiba.
- Kecepatan: kami menjamin YouTube lancar, bahkan di jam sibuk malam, asalkan internet rumah Anda bagus: China Unicom di utara atau China Telecom di selatan. Internet bersama di kompleks perumahan (di Tiongkok disebut "xiaoqu kuandai") adalah pengecualian. Kalau satu wilayah lambat, ganti wilayah atau cara koneksi.
- Konfigurasi Hiddify dan OpenVPN membawa akun Anda, dan mengganti kata sandi membatalkan konfigurasi lama: kalau HP hilang atau link bocor, sekali ganti kata sandi semuanya tidak berlaku lagi, lalu Anda cukup mengimpor ulang.

## Cara kami bekerja

- Kami hanya menyimpan informasi yang dibutuhkan untuk penagihan. Kami tidak mencatat apa yang Anda kunjungi, tidak menyisipkan iklan, dan tidak menjual data.
- Setiap klien berasal dari vendor resmi dan organisasi open source ternama: Cisco, OpenVPN, Hiddify, dan Tailscale, di-mirror apa adanya tanpa diubah; konfigurasinya dengan memindai kode QR atau impor sekali klik.
- Wilayah Tiongkok berjalan di mesin di Tiongkok daratan, dan IP exit-nya semuanya ada di Tiongkok daratan.

## Tanya jawab

**Apakah Anda lebih aman daripada merek internasional besar?** Kekuatan enkripsinya setara; keduanya memakai protokol standar. Bedanya ada di model kepercayaan: merek besar mengandalkan laporan audit; kami hanya menyimpan informasi yang dibutuhkan untuk penagihan, dan setiap klien berasal dari vendor resmi dan organisasi open source ternama.

**Kenapa tidak menyediakan ratusan node seperti penyedia jalur proxy?** Node yang lebih banyak tidak berarti lebih stabil. Di balik setiap wilayah kami ada beberapa mesin, dan saat tersambung sistem memilih yang paling sepi, jadi Anda tidak perlu menjalankan tes kecepatan dan memilih node sendiri; kalau sebuah alamat diblokir, alamat itu diganti otomatis, dan alamat di klien Anda tidak perlu diubah.

**Bisakah harganya lebih murah lagi?** Paket Pribadi $5 per bulan, dan makin lama Anda membeli, makin besar diskonnya (hemat 5% → hemat 10% → hemat 20%); per hari dengan kredit sekitar $0,36 sehari; kalau teman yang Anda undang membayar, Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), tanpa batas jumlah orang. Mendaftar juga langsung mendapat uji coba gratis 4 jam.

**Bagaimana cara membuktikan klaim Anda?** Ambil uji coba 4 jam, sambungkan ke wilayah Tiongkok di jam sibuk malam dan tonton satu episode di Tencent Video, sambungkan ke wilayah luar negeri dan buka YouTube, lalu cek lokasi terdaftar IP-nya dan halaman tes IPv6. Daftar periksanya ada di "Cara memilih VPN ke Tiongkok".


## Bacaan lanjutan

- [Cara koneksi mana yang cocok untuk situasi apa](https://www.leotun.com/id/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Cara mengenali aplikasi VPN yang berisiko](https://www.leotun.com/id/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [VPN ke Tiongkok: gratis atau berbayar](https://www.leotun.com/id/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [Tentang kami: bagaimana layanan ini dibangun dan apa yang kami catat](https://www.leotun.com/id/about?utm_source=github&utm_content=network-04)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/why-us?utm_source=github&utm_content=network-04

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=network-04) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=network-04) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), promo yang terus berlaku
