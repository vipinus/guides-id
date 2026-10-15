# 01 · Layanan apa yang butuh IP luar negeri, dan bagaimana jalur bekerja

Patokannya kebalikan dari mengakses Tiongkok dari luar negeri: begitu layanan melihat IP asal Anda ada di Tiongkok daratan, atau servernya sama sekali tidak bisa dijangkau, layanan itu tidak mau terbuka, diturunkan kualitasnya, atau sangat lambat. Tabel di bawah disusun menurut kegunaan.

| Kategori | Contoh | Yang terjadi tanpa jalur | Yang dibutuhkan selain IP |
|---|---|---|---|
| Kerja | Google Workspace, Slack, Zoom, Teams, Notion | Tidak terbuka, atau terus terputus | Akun kantor |
| Pengembangan | GitHub, npm, Docker Hub, sumber PyPI selain mirror, Stack Overflow | Sangat lambat sampai timeout | Tidak ada |
| AI | ChatGPT, Claude, Gemini | Tidak terbuka | Negara pendaftaran akun, nomor telepon |
| Riset | Google Scholar, database jurnal, email kampus | Tidak terbuka, atau sangat lambat | Akun kampus |
| Game | Steam wilayah luar negeri, PSN, Switch eShop, server luar negeri | Toko tidak terbuka, latensi tinggi | Akun untuk server wilayah itu |
| Video dan musik | YouTube, Netflix, Disney+, Spotify | Tidak terbuka | Akun berbayar, dan wilayah akun harus cocok dengan IP |
| Media sosial | X, Instagram, Telegram, Discord, WhatsApp | Tidak terbuka | Nomor telepon |

## Perbedaan penting

**"Butuh IP luar negeri" dan "butuh akun luar negeri" adalah dua hal berbeda.** Untuk GitHub dan YouTube, cukup ganti IP; Netflix butuh akun berbayar dengan wilayah yang cocok; mendaftar ChatGPT butuh nomor telepon luar negeri yang bisa menerima kode verifikasi. Jalur menyelesaikan soal "bisa dibuka atau tidak"; urusan akun tetap di tangan Anda.

## Cara kerja jalur

Lalu lintas Anda dienkripsi dulu dan dikirim ke server di luar negeri, lalu server itu yang mengakses tujuannya. Yang dilihat tujuan adalah IP server tersebut. Ada tiga caranya: klien, Proxy Web, dan router. Cara memilihnya ada di [Cara koneksi mana yang cocok untuk situasi apa](../network/02-choose-your-connection-method.md).

## Tiga salah kaprah yang umum

- **Ganti DNS tidak membantu.** Gagal tersambung adalah masalah jalur, bukan masalah resolusi nama.
- **Kecepatan tergantung jalur antara kedua titik.** Dari Tiongkok ke luar, hambatannya ada di sambungan lintas negara dan gerbang keluar operator Anda, jadi memilih wilayah lebih penting daripada spesifikasi server; lihat [03](03-which-region-is-fastest.md).
- **Saat memakai aplikasi Tiongkok, tidak semuanya harus lewat jalur.** Nyalakan split routing: secara bawaan hanya situs yang diblokir yang lewat jalur, sedangkan situs Tiongkok dan situs luar negeri yang memang bisa dibuka dari Tiongkok tersambung langsung, jadi tidak ada yang memutar; lihat [Split routing di router](../router/03-router-split-routing.md).

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=overseas-access-01) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=overseas-access-01) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, berlaku jangka panjang
