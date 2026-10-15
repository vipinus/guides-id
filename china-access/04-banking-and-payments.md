# 04 · Internet banking, mobile banking, dan pembayaran

## Apa yang dilihat manajemen risiko bank

Bank tidak hanya melihat IP. Bank menggabungkan beberapa sinyal lalu memberi skor:

1. **Lokasi terdaftar IP**: IP luar negeri langsung menaikkan tingkat risiko.
2. **Kartu SIM**: aplikasi mobile banking membaca informasi SIM, dan kartu dari operator luar negeri jadi nilai minus.
3. **Sidik jari perangkat**: perangkat baru, atau yang sudah di-jailbreak atau di-root.
4. **Perilaku**: transfer besar pada login pertama dari lokasi baru.

Jadi yang sering terjadi: setelah pindah ke IP Tiongkok Anda bisa login, tapi transfernya tetap diblokir. IP hanya menyelesaikan poin pertama.

## Yang bisa Anda lakukan

- Setelah pindah ke IP Tiongkok, **lakukan transaksi kecil dulu** supaya manajemen risiko terbiasa dengan lingkungan ini, baru transaksi besar.
- Pertahankan kartu SIM Tiongkok dan nyalakan roaming; kode verifikasi dan pemeriksaan SIM sama-sama bergantung padanya.
- Kalau bisa, pasang edisi Tiongkok aplikasi mobile banking; untuk masalah wilayah toko aplikasi, lihat [Kalau iOS tidak mengizinkan Anda memasang aplikasi](../client/06-ios-app-store.md) di repositori pendamping.
- Kalau diblokir, jangan terus mencoba ulang. Kegagalan berulang memicu pembekuan sementara, dan menelepon layanan pelanggan bank untuk membukanya adalah cara tercepat.

## Alipay dan WeChat Pay

Keduanya lebih longgar soal IP dibanding bank, dan biasanya bisa dipakai dari IP luar negeri, tetapi akun yang ditautkan ke kartu luar negeri punya batasan jumlah dan tempat pemakaian. Saat Anda perlu membayar dengan kartu Tiongkok atau mentransfer uang ke merchant Tiongkok, pindah ke IP Tiongkok membuat semuanya jauh lebih lancar.

## Yang sebaiknya tidak dilakukan

Jangan melakukan transaksi perbankan di Wi-Fi publik, baik lewat jalur maupun tidak. Jalur hanya mengganti IP exit Anda dan tidak mengenkripsi apa pun di luar ruas sampai ke bank; keamanan datang dari enkripsi aplikasi bank itu sendiri.

---
Disusun oleh tim [LeoTun](https://www.leotun.com/id?utm_source=github&utm_content=china-access-04) · Ada pertanyaan? Lihat [halaman kontak](https://www.leotun.com/id/contact?utm_source=github&utm_content=china-access-04) (grup, email, dan dukungan semuanya ada di sana) · Daftar dan dapatkan uji coba gratis 24 jam; undang teman yang membayar dan Anda berdua masing-masing mendapat 20 hari paket Pribadi, promo yang terus berlaku
