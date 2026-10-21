# 02 · Cara koneksi mana yang cocok untuk situasi apa

Satu akun LeoTun punya enam cara koneksi: Privat (Tailscale), Cisco (AnyConnect), OpenVPN, Proxy Web, Hiddify, dan Router. Setiap cara punya situasi yang paling cocok, dan artikel ini memberi jawaban per situasi: pertama menurut perangkat yang Anda pakai, lalu menurut jaringan tempat Anda berada, dan terakhir menurut apa yang ingin Anda lakukan. Setiap situasi disertai rekomendasi, alasannya, dan alternatifnya. Ingat satu hal: satu akun bisa memakai enam cara; selalu ada satu yang cocok dengan jaringan Anda.

## Menurut perangkat: Anda online dengan apa

- Satu HP, dinas dan perjalanan: Cisco atau Hiddify. Cisco langsung tersambung begitu alamatnya dimasukkan di aplikasi resmi dan paling stabil; Hiddify diimpor dengan memindai kode QR dan lebih cepat saat packet loss tinggi. Alternatif: Privat.
- Komputer pribadi (Windows, Mac): Hiddify atau Privat. Hiddify cepat dan punya sakelar split routing bawaan; Privat tetap online setelah sekali login. Alternatif: Cisco.
- Komputer dari kantor, tanpa hak administrator: Proxy Web. Anda hanya memasang satu ekstensi browser, tidak perlu hak administrator, dan tidak menyentuh pengaturan jaringan kantor.
- iPhone, perangkat lama: Cisco. Tersambung dengan VPN bawaan sistem atau klien resmi, tidak perlu impor konfigurasi, dan kompatibilitasnya paling baik.
- NAS (Synology, QNAP), server Linux: OpenVPN. Impor satu file .ovpn dan perangkat tersambung otomatis saat menyala; kebanyakan perangkat ini sudah punya klien bawaan.
- TV, set-top box, konsol game, HP orang tua: Router. Apa pun yang tersambung ke Wi‑Fi lewat jalur, dan tidak ada yang perlu dipasang di perangkatnya. Ketiga paket akun bisa memakainya.
- Banyak perangkat untuk seluruh keluarga atau kantor: Router, diatur sekali dan berlaku untuk semua; kalau Anda juga ingin menjangkau NAS di rumah dari luar, tambahkan Privat.

## Menurut lingkungan jaringan: Anda di jaringan apa

- Jaringan asrama atau kampus, jaringan kantor yang membatasi UDP: Cisco. Berjalan di atas TLS, sama seperti membuka situs HTTPS, dan paling stabil di jaringan yang dibatasi; Hiddify, Privat, dan OpenVPN semuanya berjalan di atas UDP dan akan lambat atau putus-putus.
- Internet rumah yang sering putus, sinyal Wi‑Fi lemah: Proxy Web. Bekerja per permintaan tanpa koneksi yang terus terbuka, jadi memang tidak ada koneksi yang bisa putus.
- Internet di kompleks perumahan lama, data seluler, packet loss tinggi: Hiddify. Protokolnya dirancang tahan packet loss dan memberi kecepatan terbaik di jaringan seperti itu.
- Komputer sudah tersambung ke VPN kantor: Proxy Web. Dua VPN untuk seluruh perangkat yang berjalan bersamaan akan berebut pengaturan jaringan; Proxy Web hanya menangani browser, jadi keduanya tidak saling mengganggu.
- Internet China Mobile, Great Wall, dan lainnya, atau jalur lintas negara yang selalu tidak stabil: cara apa pun, dengan memilih titik masuk wilayah Tiongkok. Biasanya ini pilihan paling stabil di jaringan seperti ini.

## Menurut tujuan: apa yang ingin Anda lakukan

- Anda di luar Tiongkok dan ingin menonton video Tiongkok: cara apa pun yang mencakup seluruh perangkat (Cisco, Hiddify, Privat, OpenVPN, Router) dengan wilayah Tiongkok dipilih; untuk TV di rumah pakai Router. Jangan pakai Proxy Web untuk video: ia tidak menjangkau saluran jaringan perangkat itu sendiri, sehingga situs video mungkin tetap menganggap Anda di luar negeri.
- Game, panggilan suara dan video: Hiddify, Privat, atau Router, dengan wilayah yang latensinya paling rendah. Proxy Web hanya menangani browser; game dan aplikasi panggilan tidak lewat situ.
- Kerja kantor dan mencari informasi, hanya browser: Proxy Web paling praktis; kalau Anda perlu tersambung ke sistem internal kantor, pastikan dulu apakah VPN kantor bisa berjalan bersama milik kami, dan kalau tidak bisa, pakai Proxy Web.
- Server, skrip, baris perintah: OpenVPN; di desktop Linux Anda juga bisa memakai Privat atau Hiddify.
- Menjangkau NAS atau kamera di rumah dari luar: Privat. Perangkat dalam satu akun bisa saling menjangkau, tanpa perlu membuka port di router.

## Ringkasan enam cara: paling cocok untuk / kurang cocok untuk

- Privat (Tailscale): paling cocok untuk banyak perangkat, login sekali lalu dilupakan, menjangkau perangkat rumah dari luar. Kurang cocok untuk jaringan yang membatasi UDP (hanya bisa mengandalkan relay, yang lambat), dan untuk berjalan bersama VPN lain.
- Cisco AnyConnect: paling cocok untuk jaringan yang dibatasi, komputer kantor, iPhone, perangkat lama; kompatibilitasnya paling baik. Kurang cocok untuk orang di Tiongkok yang tidak ingin semua lalu lintas lewat jalur (perlu menjalankan skrip split routing terpisah).
- OpenVPN: paling cocok untuk NAS, server Linux, router OpenWrt; impor satu file dan tersambung otomatis saat menyala. Kurang cocok untuk pemakaian harian di HP dan komputer, di mana ia kalah praktis dibanding Cisco dan Hiddify; juga jaringan yang membatasi UDP.
- Proxy Web: paling cocok untuk yang tidak punya hak administrator, yang sudah tersambung ke VPN kantor, dan internet rumah yang sering putus. Kurang cocok untuk aplikasi video, game, panggilan; ia hanya menangani browser.
- Hiddify: paling cocok untuk yang mengejar kecepatan, jaringan dengan packet loss tinggi; impor dengan memindai kode QR, aplikasi yang sama di lima platform, split routing bawaan. Kurang cocok untuk jaringan yang membatasi UDP.
- Router: paling cocok untuk seluruh keluarga, kantor, perangkat yang tidak bisa dipasangi klien; firmware-nya punya split routing bawaan dan diperbarui otomatis. Kurang cocok untuk orang yang hanya punya satu perangkat dan sering di luar rumah (Anda tetap perlu memasang klien saat keluar).

## Memilih wilayah menurut internet rumah Anda

Cara yang sama bisa berbeda kecepatannya berkali-kali lipat antarwilayah; penyebabnya ada di jalur keluar operator Anda ke wilayah itu, bukan di servernya. China Unicom di wilayah utara: coba Jepang dan Korea dulu. China Telecom di wilayah selatan: coba Asia Tenggara (Singapura, Malaysia, Thailand, Filipina, Indonesia) atau Australia dulu. Internet lain (China Mobile, Great Wall, dan sejenisnya): coba titik masuk wilayah Tiongkok dulu.

Lampu merah, kuning, dan hijau di daftar wilayah menunjukkan beban tiap wilayah secara langsung; di antara beberapa titik masuk Jepang, pilih yang lampunya hijau. Pukul 20.00 sampai 23.00 adalah jam sibuk nasional; pada jam itu pilih wilayah berlampu hijau atau ganti cara koneksi. Kalau masih lambat, penyebab biasanya internet rumah setempat (internet bersama di kompleks perumahan, atau operator dan wilayah yang tidak cocok).

## Split routing: langsung untuk situs di Tiongkok, lewat jalur untuk luar negeri

Hanya pengguna yang berada di Tiongkok daratan yang butuh split routing; pengguna di luar negeri memakai mode global, dan menyalakan split routing justru membuat sebagian situs memutar jauh. Di Hiddify Anda beralih ke "Auto split routing" (split routing otomatis) di klien, di Proxy Web Anda beralih ke "Split routing" di ekstensi, router melakukan split routing untuk setiap perangkat di jaringan dan firmware-nya menyalakannya secara bawaan; dengan Cisco dan OpenVPN semua lalu lintas lewat jalur begitu tersambung, dan skrip split routing tersedia di bagian "Cisco"; Privat mengalirkan seluruh perangkat lewat jalur.

Kalau sebuah situs tidak terbuka dengan split routing, pindah sementara ke "Global" untuk memeriksa: kalau terbuka dengan mode global, situs itu tidak ada di daftar; kalau dengan mode global pun tidak terbuka, masalahnya ada di situs itu sendiri.

## Cara berpindah kalau tidak jalan

1. Ganti wilayah dulu. Kalau wilayah lain bisa tersambung, server tadi hanya sedang tidak terjangkau sementara.
2. Lalu ganti jaringan. Kalau internet rumah tidak jalan, pindah ke data seluler, dan sebaliknya; gangguan di operator yang berbeda tidak terjadi bersamaan.
3. Lalu ganti cara. Kalau yang berjalan di atas UDP (Hiddify, Privat, OpenVPN) tidak jalan, pindah ke Cisco yang berjalan di atas TLS; kalau cara untuk seluruh perangkat terus putus, pindah ke Proxy Web. Pemblokiran protokol yang berbeda tidak saling terkait.
4. Kalau masih tidak jalan, lihat panduan pemecahan masalah, atau tanyakan di grup dukungan dengan menyertakan cara koneksi, wilayah, teks error persisnya, dan waktunya.

## Tanya jawab

**Dari enam cara, mana yang paling cepat?** Di jaringan dengan packet loss tinggi, Hiddify paling cepat; di jaringan yang bersih bedanya kecil, dan yang membatasi adalah wilayah dan jamnya, bukan caranya.

**Mana untuk game dan panggilan suara?** Hiddify, Privat, atau Router, dengan wilayah yang latensinya paling rendah. Proxy Web hanya menangani browser; game dan aplikasi panggilan tidak lewat situ.

**Bisakah keenam cara dipakai bersamaan?** Di perangkat berbeda, bisa; semua cara dalam satu akun berbagi jatah perangkat online bersamaan (Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat). Jangan jalankan dua cara untuk seluruh perangkat sekaligus di perangkat yang sama (misalnya Privat dan Cisco), karena keduanya akan berebut pengaturan jaringan.

**Apakah harus memilih antara router atau klien?** Tidak. Pakai router di rumah dan nyalakan klien di HP saat keluar; masing-masing dihitung satu perangkat.

**Mana untuk Linux?** Privat, OpenVPN, dan Hiddify semuanya punya klien Linux; Cisco di Linux memakai OpenConnect yang open source; OpenVPN di Linux meminta akun dan kata sandi saat sambungan pertama. Untuk server dan NAS, OpenVPN paling praktis.

## Bacaan lanjutan

- [Apa bedanya kami dengan VPN lain](https://www.leotun.com/id/guides/why-us?utm_source=github&utm_content=network-02)
- [Apa itu jaringan Privat (Tailscale)](https://www.leotun.com/id/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [Cara memakai OpenVPN dan kapan memilihnya](https://www.leotun.com/id/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Apa itu Proxy Web dan kapan memakainya](https://www.leotun.com/id/guides/web-proxy?utm_source=github&utm_content=network-02)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/choose-connection?utm_source=github&utm_content=network-02

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=network-02) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=network-02) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
