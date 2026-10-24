# AGENTS.md — Kontrak Proyek RasanyaChips

## 1. Sumber kebenaran
Dokumen berikut adalah acuan utama proyek:
1. `docs/sot/PRD.md`
2. `docs/sot/UI-GUIDELINE.md`
3. `docs/sot/IMPLEMENTATION_PLAN.md`

Baca ketiganya sebelum mengubah kode. Jika ada konflik, hentikan perubahan yang terdampak dan minta klarifikasi; jangan menebak keputusan produk.

## 2. Batas ruang lingkup
Implementasikan hanya tujuh modul yang tercantum pada PRD:
1. Dashboard Admin
2. Manajemen Produk
3. Kategori Produk
4. Manajemen Stok
5. Transaksi Penjualan
6. Laporan Penjualan
7. Login dan Pengguna

Jangan menambahkan marketplace, portal pelanggan, payment gateway, kurir, supplier, akuntansi lengkap, atau fitur lain tanpa persetujuan eksplisit.

## 3. Kontrak teknologi
- Gunakan React + Vite untuk front-end.
- Ikuti stack yang ditetapkan dalam `IMPLEMENTATION_PLAN.md`.
- Jangan mengganti framework/build tool tanpa persetujuan.
- Backend/database masih merupakan keputusan terbuka. Jangan mengasumsikan pilihan produksi.
- Mock data harus diberi label sebagai data contoh dan tidak boleh dipresentasikan sebagai data toko nyata.
- Local storage, jika digunakan, hanya untuk prototipe lokal dan bukan pengganti backend produksi multi-pengguna.

## 4. Kontrak UI/UX
- Ikuti warna, tipografi, layout, komponen, dan prinsip responsivitas dalam UI-GUIDELINE.
- Pertahankan identitas orange, putih, dan aksen kuning.
- Gunakan status yang jelas dengan label/ikon selain warna.
- Sertakan loading, empty, error, dan success state yang relevan.
- Pastikan label input, fokus keyboard, dan kontras dapat digunakan.
- Jangan membuat layar atau fitur di luar ruang lingkup yang disetujui.

## 5. Kontrak arsitektur
- Pisahkan presentasi, aturan bisnis, dan akses data.
- Hindari logika transaksi/stok yang kompleks di dalam komponen UI.
- Gunakan komponen bersama untuk pola yang berulang.
- Hindari duplikasi definisi metrik penjualan.
- Pertahankan integritas data historis.
- Validasi sisi klien tidak menggantikan validasi sisi server.

## 6. Aturan bisnis yang tidak boleh dilanggar
- Harga dan jumlah stok tidak boleh negatif.
- Produk nonaktif atau stok yang tidak cukup tidak dapat dijual.
- Stok hanya dikurangi setelah transaksi berhasil disimpan.
- Cegah pengurangan stok ganda akibat aksi transaksi yang diulang.
- Catat riwayat perubahan stok.
- Total transaksi harus sesuai harga item dikalikan kuantitas.
- Jangan menghapus relasi atau data historis tanpa strategi yang aman.
- Akses administratif harus mengikuti autentikasi dan otorisasi yang benar.

## 7. Prosedur kerja
1. Periksa struktur proyek dan status file sebelum mengubahnya.
2. Baca SOT yang relevan.
3. Kerjakan perubahan kecil dan terfokus.
4. Jangan menimpa file pengguna atau menghapus data tanpa kebutuhan dan izin yang jelas.
5. Jika diperlukan keputusan yang belum ada dalam SOT, jelaskan pilihan dan minta persetujuan sebelum membuat perubahan yang mengikat.
6. Perbarui dokumentasi jika perilaku atau instruksi proyek berubah.
7. Jangan menambahkan dependensi tanpa alasan yang jelas.

## 8. Pemeriksaan dan pelaporan
- Jalankan pemeriksaan yang tersedia dan relevan: lint, test, serta build.
- Jika script belum tersedia, laporkan; jangan mengklaim pemeriksaan telah dijalankan.
- Laporkan file yang diubah, keputusan yang dibuat, hasil pemeriksaan, dan keterbatasan.
- Jangan menyatakan fitur selesai hanya karena halaman dapat dirender.
- Jangan mengarang hasil pengujian, data, atau status integrasi.

## 9. Definisi selesai
Tugas dianggap selesai ketika:
- Perubahan sesuai SOT dan ruang lingkup.
- Aturan bisnis terkait diuji.
- Penanganan loading/error/empty state relevan tersedia.
- Pemeriksaan yang dapat dijalankan telah dilakukan dan hasilnya dilaporkan.
- Dokumentasi terkait diperbarui.
- Tidak ada keputusan penting yang disamarkan sebagai fakta.

## 10. Perubahan SOT
SOT hanya boleh diubah berdasarkan persetujuan pemilik proyek. Jika implementasi membutuhkan perubahan ruang lingkup, ajukan perubahan dan tunggu persetujuan sebelum melanjutkan.
