# 05 · Cara mengalirkan server Linux dan alat baris perintah lewat jalur

Di Linux ada dua cara ke jalur; pilih sesuai kebutuhan. Kalau seluruh mesin mau lewat jalur (menarik image Docker, menjalankan layanan yang butuh jaringan luar negeri, berjalan tanpa diawasi), pakai OpenVPN: satu file konfigurasi diletakkan di /etc/openvpn/client/ dan dijalankan saat boot. Kalau hanya beberapa perintah yang mau lewat jalur (git, pip, npm, curl), pakai Proxy Web: masukkan alamat proxy ke variabel lingkungan http_proxy, dan lalu lintas lainnya tidak tersentuh. Di Linux desktop, Anda juga bisa mengimpornya di NetworkManager. Artikel ini membahas ketiganya, termasuk cara menulis file kata sandi dan perintah untuk memeriksa hasilnya.

## Cara pertama: seluruh mesin lewat jalur (OpenVPN)

1. Pasang kliennya: Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Login ke situs ini dan, di halaman OpenVPN, klik bendera wilayah untuk mengunduh .ovpn. Konfigurasi yang diterima Linux tidak menyertakan akun dan kata sandi (NetworkManager tidak menerima file yang berisi kredensial), jadi buat file kata sandi terpisah: dua baris, baris pertama email Anda di situs ini, baris kedua kata sandinya, lalu chmod 600.
3. Salin .ovpn ke /etc/openvpn/client/<wilayah>.conf, lalu tambahkan path file kata sandi setelah auth-user-pass di file itu.
4. sudo systemctl enable --now openvpn-client@<wilayah>. Cek statusnya dengan systemctl status openvpn-client@<wilayah>, lalu pastikan curl -s https://ipinfo.io/country menampilkan wilayah yang Anda pilih.
5. Untuk ganti wilayah, unduh konfigurasi lain dan aktifkan unit lain; jalankan hanya satu dalam satu waktu.

## Cara kedua: hanya alat baris perintah yang lewat jalur (Proxy Web)

Alamat proxy yang tertera di halaman Proxy Web situs ini, bersama akun dan kata sandi Anda, bisa langsung dimasukkan ke variabel lingkungan: export https_proxy=https://username:password@alamat-proxy export http_proxy=$https_proxy. Karakter khusus di kata sandi harus di-encode sebagai URL. Setelah itu curl, wget, git, pip, dan npm di terminal ini semuanya lewat jalur, sedangkan program lain tidak terpengaruh.

Daemon Docker tidak membaca variabel lingkungan shell; tulis ke Environment= di /etc/systemd/system/docker.service.d/proxy.conf lalu restart docker. Untuk apt, tulis Acquire::https::Proxy di /etc/apt/apt.conf.d/proxy.conf.

Di cara ini, memang tidak ada koneksi yang bisa putus; tidak butuh root dan tidak mengubah rute. Cocok untuk server kantor dan kalau Anda hanya ingin mempercepat unduhan; hanya berlaku untuk program yang mengikuti variabel proxy, dan lalu lintas lainnya tidak tersentuh.

## Cara ketiga: NetworkManager di Linux desktop

1. Pasang network-manager-openvpn-gnome (sekali klik di halaman OpenVPN situs ini bisa membuka pusat perangkat lunak).
2. Pengaturan → Jaringan → VPN → "+" → Impor dari file, pilih .ovpn, masukkan email dan kata sandi Anda di situs ini, lalu simpan.
3. Nyalakan dan matikan VPN dari bilah atas atau tray. Untuk tersambung otomatis saat boot, centang "Sambungkan otomatis ke VPN" di pengaturan koneksi kabel/nirkabel.

## Memeriksa dan memecahkan masalah

- Cek exit: negara di curl -s https://ipinfo.io adalah wilayah yang Anda pilih.
- Cek DNS: di resolvectl status, DNS antarmuka VPN harus yang dikirim oleh jalur; kalau bocor, tambahkan dhcp-option DNS ke konfigurasi atau pakai skrip update-systemd-resolved.
- AUTH_FAILED: file kata sandinya salah atau akun sudah kedaluwarsa; kalau Anda mengganti kata sandi, perbarui file kata sandinya.
- TLS handshake timeout: UDP ke server tidak tembus; ganti wilayah atau jaringan. Di server cloud, security group harus mengizinkan UDP keluar.
- Servernya di Tiongkok dan sumber paket Tiongkok seharusnya tersambung langsung: begitu OpenVPN tersambung, semua lalu lintas keluar lewat jalur. Ganti sumber apt / pip / npm ke mirror Tiongkok, atau pakai cara kedua saja supaya hanya perintah tertentu yang lewat jalur.

## Yang perlu diketahui

- Satu mesin Linux dihitung satu perangkat dan berbagi jatah online bersamaan dengan perangkat Anda yang lain (Pribadi 2 perangkat, Keluarga 4 perangkat, Perusahaan 8 perangkat); Proxy Web di cara kedua dihitung per koneksi dan juga termasuk.
- File konfigurasi dan file kata sandi sama nilainya dengan akun Anda; jangan commit ke repositori git atau memasukkannya ke image.
- Setelah Anda mengganti kata sandi, konfigurasi lama langsung tidak berlaku; ini memang mekanisme pencabutannya. Cukup perbarui file kata sandi.
- Saat menjalankan jalur di server cloud, patuhi ketentuan penyedia cloud; jalur hanya mencatat durasi koneksi dan total lalu lintas.

## Tanya jawab

**Kenapa konfigurasi Linux tidak menyertakan akun dan kata sandi?** Saat mengimpor konfigurasi, NetworkManager tidak menerima file yang berisi kredensial dan melaporkan impor gagal, jadi salinan untuk Linux meminta Anda mengisinya sendiri; dengan cara systemd, tulis ke file kata sandi.

**Bisakah hanya Docker yang lewat jalur?** Bisa: atur variabel proxy khusus untuk daemon Docker (cara kedua); atau jalankan container yang berisi OpenVPN (gluetun) supaya container tertentu lewat jalur.

**Bagaimana dengan Privat (Tailscale) di Linux?** Skrip resmi memasangnya dalam satu baris, dan tailscale up --login-server=<server kontrol situs ini> untuk login. Cocok kalau Anda perlu mengakses mesin ini dari luar, atau ingin mengaturnya sekali lalu selalu online; kalau sekadar mempercepat unduhan, OpenVPN atau proxy lebih sederhana.

**Apakah sama untuk OpenWrt di router?** Di OpenWrt, pasang luci-app-openvpn dan unggah .ovpn, lalu seluruh LAN lewat jalur; router dengan firmware situs ini tidak perlu itu, cukup login ke akun Anda.

## Bacaan lanjutan

- [Halaman OpenVPN: unduhan klien dan file konfigurasi](https://www.leotun.com/id/openvpn?utm_source=github&utm_content=overseas-access-05)
- [Cara memakai OpenVPN dan kapan memilihnya](https://www.leotun.com/id/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Cara mengalirkan NAS Synology atau QNAP lewat jalur](https://www.leotun.com/id/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Apa itu Proxy Web dan kapan memakainya](https://www.leotun.com/id/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Versi situs web artikel ini (tersedia juga dalam bahasa Mandarin tradisional dan Inggris): https://www.leotun.com/id/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-05) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-05) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 4 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 15 kredit (sekitar 15 hari paket Pribadi), berlaku jangka panjang
