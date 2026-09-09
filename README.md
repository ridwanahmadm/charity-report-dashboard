# Siiru — Laporan Kebaikan Publik

Landing page publik untuk menjelajahi laporan distribusi donasi Siiru di Arab Saudi. Pengunjung tidak perlu login. Detail donasi personal diarahkan ke Siiru App.

## Menjalankan

Jalankan `npm start`, lalu buka http://localhost:4173. Tidak ada paket tambahan yang diperlukan. Gunakan `PORT` untuk mengganti port.

Folder `public/` dapat ditempatkan pada hosting statis. Navigasi memakai hash sehingga URL detail dapat dibuka langsung tanpa konfigurasi server tambahan. Website belum dipublikasikan ke internet.

## Fitur

- Hero foto Makkah dengan logo SVG resmi Siiru.
- Ringkasan dampak dan tujuh program: botol air, makanan, wakaf kursi roda, wakaf Al-Qur’an, qurban, aqiqah, dan dam.
- Carousel program dengan kontrol sebelumnya/berikutnya dan pilihan tab.
- Galeri foto referensi dengan modal, navigasi tombol, panah keyboard, dan Escape.
- Laporan kegiatan publik dengan filter kota, program, periode, pencarian, accordion detail, tombol “lihat lebih banyak”, dan unduh CSV agregat.
- Detail laporan publik yang hanya menampilkan ringkasan kegiatan; tidak ada data donatur.
- Tautan App Store dan Google Play resmi Siiru untuk detail donasi personal.
- FAQ, menu mobile native, focus state, skip link, scroll reveal, hover motion, dan prefers-reduced-motion.

## Status data dan integrasi

Seluruh ID, tanggal, kuantitas, lokasi kegiatan, dan status pada `public/app.js` adalah **data demo**, bukan bukti transaksi atau laporan operasional resmi Siiru. Kota Makkah, Madinah, dan Jeddah adalah lokasi sebenarnya; peta hanya skematis.

Website ini tidak menerima pembayaran dan belum terhubung ke backend atau data akun. Untuk penggunaan operasional, ganti koleksi `programs` dan `reports` dengan data terverifikasi dari API. Foto program selain air sengaja tidak direkayasa sebagai bukti penyaluran.

## Referensi

- Profil Siiru: https://services.siiru.io/faq/
- App Store: https://apps.apple.com/my/app/siiru/id6739772762
- Google Play: https://play.google.com/store/apps/details?id=io.siiru.app
- Foto air `water.webp` dan `community.webp`: https://siiru.io/sadaqah-water-for-hajj-pilgrims-1447h-report/ (masing-masing gambar 6.webp dan 7.webp). Digunakan sebagai referensi visual, bukan bukti kegiatan demo.
- Foto suasana Makkah: https://images.unsplash.com/photo-1565552645632-d725f8bfc19a
- Mobbin: https://mobbin.com/discover/apps/web — telah ditelusuri; desain dan rating tidak dapat diverifikasi dari akses publik. Tidak mengklaim menggunakan desain terpopuler atau berperingkat tertinggi.
- Inspirasi pola dashboard dan interaksi: https://collectui.com/ dan https://canvasui.dev/. Implementasi CSS/JavaScript mandiri; tidak memakai efek eksperimental canvas.
- Tipografi: DM Sans dan Instrument Serif melalui Google Fonts, dengan fallback Arial dan Georgia jika jaringan tidak tersedia.

## Verifikasi

`npm run check` memeriksa sintaks JavaScript. `tests/verify.cjs` menjalankan pemeriksaan alur dengan Playwright dan Chrome lokal. Path Playwright pada pengujian merujuk runtime yang tersedia di workspace ini; sesuaikan jika dipindah ke komputer lain.

Hasil pemeriksaan: `artifacts/landing-verification.json`. Pratinjau visual: `artifacts/landing-desktop.png`, `artifacts/landing-mobile.png`, dan `artifacts/landing-public-detail.png`. Contoh hasil unduhan: `artifacts/landing-public-report.csv`.

Pemeriksaan mencakup tanpa login, aset logo, carousel tujuh program, filter dan URL, pencarian kosong, CSV tanpa data pribadi, detail publik, galeri, tautan aplikasi, status terjadwal, FAQ, responsivitas tujuh lebar layar, menu mobile, reduced motion, scroll reveal, dan runtime errors.
# charity-report-dashboard
