# 05 · Cara mengenali aplikasi VPN yang berisiko

Seluruh lalu lintas Anda melewati tangan aplikasi VPN, dan aplikasi itu bisa melihat apa saja yang ia mau. Ada dua jenis yang perlu diwaspadai secara khusus: pertama, yang di kalangan pengguna disebut "VPN merah", yang punya latar belakang regulator, meminta identitas asli Anda atas nama kepatuhan hukum, lalu menyerahkan catatannya; kedua, akselerator gratis yang asal-usulnya tidak jelas, yang mencari uang dari data Anda, perangkat Anda, atau sesuatu yang ditanamnya. Kesamaan keduanya: "dipakai sih lancar-lancar saja"; masalahnya ada di tempat yang tidak terlihat. Di bawah ini ada sepuluh tanda yang bisa Anda periksa sendiri, apa yang harus dilakukan kalau sudah telanjur memasangnya, dan pemeriksaan mandiri tiga menit.

## Kenapa aplikasi VPN lebih berisiko daripada aplikasi biasa

VPN bekerja di tingkat sistem: ia menerima lalu lintas setiap program di perangkat, termasuk yang tidak Anda ketahui sedang berjalan di latar belakang. Aplikasi biasa membocorkan data yang dikumpulkannya sendiri; VPN membocorkan semua yang Anda lakukan di perangkat itu. Jadi standar memilih VPN harus jauh lebih ketat daripada memilih aplikasi biasa.

"Saya sudah pakai dan tidak terjadi apa-apa" bukan bukti aman. Pencatatan, pelaporan, dan penyisipan semuanya terjadi di sisi server atau di latar belakang dan tidak terasa dari sisi pengguna; kalau ada yang terjadi, sering kali baru berbulan-bulan kemudian, dan tidak bisa ditelusuri software mana penyebabnya.

## Sepuluh tanda

- Sumbernya tidak jelas: file instalasinya beredar lewat grup chat, cloud drive, atau kode QR, tanpa situs resmi atau halaman di toko aplikasi. Klien yang sah datang dari toko aplikasi, situs resmi pengembangnya, atau halaman rilis yang tanda tangannya bisa diperiksa.
- Meminta Anda memasang sertifikat root: saat instalasi ia meminta Anda "memercayai sertifikat" atau "memasang profil" dan mewajibkan memercayai sebuah CA. Begitu sertifikat root terpasang, ia bisa membuka seluruh lalu lintas HTTPS Anda, termasuk internet banking dan email. VPN normal tidak butuh langkah ini.
- Izinnya terlalu banyak: VPN yang meminta akses kontak, SMS, log panggilan, lokasi persis, dan galeri foto. VPN hanya butuh izin untuk membuat terowongan; sisanya tidak ada gunanya.
- Mewajibkan pendaftaran nama asli: mendaftar butuh KTP, pemindaian wajah, atau menautkan nomor HP Tiongkok daratan. Begitulah cara VPN yang katanya "patuh hukum" mengikat identitas Anda ke catatan lalu lintas; layanan yang sah hanya butuh alamat email.
- Protokol khusus + klien tertutup: Anda hanya bisa memakai aplikasinya sendiri, dan tidak ada protokol standar (AnyConnect, OpenVPN, WireGuard, Hiddify) yang didukung, sehingga Anda tidak bisa memakai klien open source pihak ketiga untuk memeriksa apa yang sebenarnya dikirim.
- Gratis, tanpa sumber pemasukan yang terlihat: tidak ada paket berbayar, tidak ada iklan, tidak ada pelanggan bisnis, tapi tetap jalan bertahun-tahun. Bandwidth exit di Tiongkok daratan ditagih sesuai pemakaian, dan layanan yang tidak menarik bayaran pasti menutup biayanya dari tempat lain.
- Tanpa perusahaan, tanpa dukungan, tanpa rekam jejak: badan pengelolanya tidak bisa ditemukan, tidak ada yang bisa dihubungi, domainnya didaftarkan kurang dari setahun lalu, dan sering ganti nama dan ganti kemasan.
- Lalu lintas latar belakang yang tidak wajar: perangkat terus mengunggah data meski sedang tidak dipakai, dan baterai serta kuota cepat habis. Mungkin perangkat Anda dipakai sebagai exit untuk orang lain, atau data Anda sedang disinkronkan.
- Promosinya menekankan "resmi", "terdaftar", "legal dan patuh hukum" dan menyiratkan bahwa yang lain ilegal: ini jualan paling khas "VPN merah", dan kepatuhannya berupa mencatat dan melapor.
- Rating di toko aplikasi berat sebelah, ulasannya mirip-mirip, dan jumlah unduhan tidak sebanding dengan jumlah ulasan: semuanya palsu.

## Cara memeriksa

1. Lihat protokolnya: apakah situs resminya menyebutkan protokol yang dipakai dan apakah bisa memakai klien pihak ketiga. Dengan layanan yang bisa disambungkan memakai klien open source atau standar seperti OpenVPN, AnyConnect, Hiddify, dan Tailscale, Anda bisa merekam paket sendiri dan melihat apa yang dikirim.
2. Lihat izinnya: setelah memasang, buka pengaturan sistem untuk melihat izin apa saja yang dimintanya, matikan semua selain VPN, lalu lihat apakah masih jalan. Kalau tidak jalan, hapus.
3. Lihat sertifikatnya: iOS Pengaturan → Umum → VPN & Manajemen Perangkat; Android Setelan → Keamanan → Enkripsi & kredensial → Kredensial tepercaya → Pengguna; "Trusted Root Certification Authorities" (Otoritas Sertifikasi Root Tepercaya) di pengelola sertifikat Windows. Kalau ada sertifikat yang dipasangnya, hapus dan uninstall aplikasinya.
4. Periksa kebocoran: setelah tersambung, buka tes kebocoran DNS dan halaman tes IPv6 untuk melihat apakah resolusi nama dan alamatnya sama-sama lewat servernya; lalu buka situs HTTPS dan lihat apakah penerbit sertifikatnya CA yang asli.
5. Periksa badan pengelolanya: apakah situs resminya punya profil perusahaan atau tim, sudah berapa tahun beroperasi, dan di mana dukungannya; apakah aturan refund tertulis; apakah kebijakan privasinya menjelaskan dengan jelas apa saja yang dicatat.

## Kalau sudah telanjur memasangnya

1. Uninstall software-nya, lalu periksa lokasi-lokasi yang disebut di atas dan hapus sertifikat serta profil yang dipasangnya.
2. Ganti kata sandi: internet banking, email, akun yang sering dipakai, terutama yang Anda login saat memakainya.
3. Untuk akun yang memakai verifikasi dua langkah, periksa riwayat login dan hapus perangkat yang tidak dikenal.
4. Kalau dipasang di router, kembalikan ke setelan pabrik lalu flash ulang firmware resmi atau yang tepercaya.

## Cara kami membiarkan Anda memeriksa

Setiap klien LeoTun berasal dari vendor resmi dan organisasi open source ternama: Cisco, OpenVPN, Hiddify, dan Tailscale, disalin apa adanya tanpa modifikasi, dan Anda bisa mengganti salinan yang diunduh dari situs ini dengan klien resmi atau open source kapan saja. Protokolnya semua protokol standar dan bisa diperiksa dengan merekam paket.

Mendaftar hanya butuh alamat email, tanpa nomor telepon dan tanpa KTP. Kami hanya menyimpan informasi yang diperlukan untuk penagihan; kami tidak mencatat apa yang Anda kunjungi, tidak menyisipkan iklan, dan tidak menjual data.

Kami tidak memasang sertifikat dan tidak meminta akses kontak atau lokasi. Kalau suatu hari klien kami meminta Anda memasang sertifikat root, itu pasti bukan kami.

## Tanya jawab

**Apakah semua yang gratis tidak bisa dipakai?** Klien dari komunitas open source (OpenVPN, Hiddify, Tailscale) sendiri gratis dan tepercaya; risikonya ada pada "layanan gratis", bukan "software gratis". Untuk layanan gratis, lihat dari mana ia hidup.

**Apakah sesuatu aman karena ada di toko aplikasi?** Ada di toko aplikasi hanya berarti lolos pemeriksaan otomatis toko; bukan berarti sisi servernya tidak mencatat. Lihat izin, pendaftaran nama asli, protokol, dan badan pengelola di antara sepuluh tanda di atas; toko aplikasi tidak memeriksakan hal-hal ini untuk Anda.

**Apa yang disebut "VPN merah"?** Sebutan di kalangan pengguna untuk VPN yang punya latar belakang regulator, mewajibkan pendaftaran nama asli atas nama kepatuhan hukum, dan menyimpan catatan. Biasanya mempromosikan diri sebagai "resmi" dan "legal" dan berfungsi normal saat dipakai; masalahnya, identitas Anda dan seluruh catatan lalu lintas Anda terikat jadi satu.

**Bagaimana tahu apakah sebuah VPN mencatat isi lalu lintas saya?** Dari sisi pengguna tidak bisa diketahui; Anda hanya bisa melihat berapa banyak cara memeriksa yang diberikannya: apakah protokolnya standar, apakah kliennya open source, apakah kebijakan privasinya spesifik, apakah badan pengelolanya bisa dicari. Kalau keempatnya tidak ada, anggap saja ia mencatat.

**Apakah firmware router juga punya risiko seperti ini?** Ya; "firmware tembus blokir" yang asal-usulnya tidak jelas bisa membajak seluruh jaringan rumah. Flash hanya OpenWrt resmi atau firmware yang sumbernya bisa diperiksa; firmware situs ini dikompilasi dari OpenWrt, hanya ditambah komponen untuk menyambung ke jalur dan aturan split routing.

## Bacaan lanjutan

- [Apa bedanya kami dengan VPN lain](https://www.leotun.com/id/guides/why-us?utm_source=github&utm_content=network-05)
- [VPN ke Tiongkok: gratis atau berbayar](https://www.leotun.com/id/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Kalau Tencent Video menampilkan pembatasan hak cipta di luar negeri](https://www.leotun.com/id/guides/overseas-video?utm_source=github&utm_content=network-05)
- [Tentang kami: cara layanan ini dibangun dan apa yang kami catat](https://www.leotun.com/id/about?utm_source=github&utm_content=network-05)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=network-05) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=network-05) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
