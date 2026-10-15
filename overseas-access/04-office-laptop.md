# 04 · Memakai komputer kantor: tanpa hak administrator, sudah tersambung VPN kantor

Komputer kantor punya tiga batasan: Anda tidak bisa memasang software yang tidak disetujui, tidak punya hak administrator, dan sering kali sudah tersambung ke VPN kantor. VPN untuk seluruh perangkat di sini entah tidak bisa dipasang atau malah bertabrakan dengan VPN kantor. Alat yang tepat adalah Proxy Web: ekstensi browser yang hanya mengirim permintaan dari browser ini lewat jalur, sementara intranet kantor, aplikasi email, dan VPN kantor semuanya tetap seperti semula, dan tidak perlu hak administrator. Artikel ini membahas cara mengaturnya, apa yang bisa dilakukannya, apa yang sebaiknya tidak dilakukan, dan cara menyesuaikan diri dengan kebijakan TI kantor.

## Kenapa Proxy Web

- Tidak ada klien yang perlu dipasang: hanya ekstensi browser, dan kebanyakan kantor mengizinkan ekstensi tapi tidak software.
- Tidak perlu hak administrator: ekstensi berjalan di ruang pengguna dan tidak mengubah pengaturan jaringan sistem.
- Bisa berdampingan dengan VPN kantor: VPN kantor mengambil alih rute sistem, sedangkan Proxy Web hanya ada di lapisan browser, jadi keduanya tidak saling mengganggu; halaman intranet kantor tetap lewat VPN kantor.
- Dari desainnya tidak ada koneksi yang bisa putus: proxy bekerja per permintaan tanpa koneksi yang terus terbuka, jadi gangguan di jaringan kantor pun tidak terasa.

## Atur dalam dua langkah

1. Pasang ekstensi ZeroOmega (penerus SwitchyOmega) di browser; halaman Proxy di situs ini punya link pemasangan untuk tiap browser.
2. Login ke situs ini dan, di halaman Proxy, klik "Salin link pemulihan ekstensi", lalu tempel di "Import/Export" → "Restore from online" (pulihkan dari online) di ekstensi. Wilayah dan alamat diimpor sekaligus; setelah itu klik ikon ekstensi dan pilih wilayah, lalu masukkan akun dan kata sandi Anda di situs ini di kotak login yang ditampilkan browser.
3. Kami menyarankan profil browser terpisah (atau browser lain) khusus untuk proxy, sementara browser kerja tetap lokal, supaya keduanya tidak tercampur.

## Cocok untuk apa, dan situasi mana yang butuh cara lain

- Cocok: mencari informasi, membuka Google, GitHub, Stack Overflow, situs dokumentasi luar negeri, ChatGPT versi web, dan email web.
- Pakai cara lain: aplikasi video, software desktop, dan alat baris perintah secara bawaan tidak memakai pengaturan proxy browser (untuk baris perintah, Anda bisa memasukkan alamat proxy ke variabel lingkungan http_proxy; lihat artikel Linux).
- Pakai cara lain: menonton situs video Tiongkok (bagi pengguna di luar negeri). Situs video juga memeriksa IPv6 dan DNS, yang tidak ditangani Proxy Web; situasi itu butuh VPN untuk seluruh perangkat.

## Menyesuaikan diri dengan kebijakan TI

Semua yang ada di komputer kantor bisa diaudit oleh perusahaan, termasuk ekstensi. Baca dulu kebijakan pemakaian perusahaan: yang dilarang kebanyakan perusahaan adalah software yang tidak disetujui dan mengakali kebijakan keamanan, sedangkan ekstensi browser yang mengakses situs luar biasanya ada di wilayah abu-abu; kalau ragu, tanyakan ke bagian TI.

Jangan memasang VPN untuk seluruh perangkat (Cisco, Privat, Hiddify) di komputer kantor untuk mengakali kebijakan perusahaan: semuanya mengubah rute sistem, yang memicu peringatan di software manajemen perangkat (endpoint management) dan juga ikut membawa lalu lintas intranet kantor keluar. Proxy Web hanya memengaruhi satu browser dan risikonya paling kecil.

Pisahkan akun kerja dan akun pribadi: jangan login ke akun kantor di browser yang memakai proxy, dan jangan login ke akun pribadi di browser kantor.

## Tanya jawab

**Bagaimana kalau kantor melarang pemasangan ekstensi?** Pakai HP atau komputer pribadi Anda sendiri. Jangan memakai software portabel yang asal-usulnya tidak jelas untuk mengakali kontrol itu.

**Apakah ekstensi akan melihat lalu lintas intranet kantor saya?** Tidak. Dengan aturan split routing, domain intranet kantor tersambung langsung dan tidak melewati proxy; dalam mode global, lalu lintas itu hanya dikirim ke server proxy lalu kembali, dan yang dilihat proxy adalah nama domain, bukan isinya. Supaya aman, beri proxy profil browser tersendiri.

**Apakah proxy tetap jalan saat VPN kantor menyala?** Ya, keduanya tidak bertabrakan. Sebagian kecil VPN kantor memaksa semua lalu lintas lewat exit kantor dan mematikan pengaturan proxy; dalam kasus itu ekstensi akan melaporkan tidak bisa tersambung, dan satu-satunya pilihan adalah mematikan VPN kantor.

**Apakah sama di Mac kantor?** Sama; ekstensi untuk Chrome, Edge, dan Firefox semuanya punya versi Mac. Safari tidak punya ekstensi ini, jadi pakai browser lain.

## Bacaan lanjutan

- [Halaman pengaturan proxy: pemasangan ekstensi dan link pemulihan](https://www.leotun.com/id/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Apa itu Proxy Web dan kapan memakainya](https://www.leotun.com/id/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Cara mengalirkan server Linux dan alat baris perintah lewat jalur](https://www.leotun.com/id/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Cara koneksi mana yang cocok untuk situasi apa](https://www.leotun.com/id/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-04) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-04) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
