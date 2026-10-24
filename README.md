# Dashboard Analisis Transaksi, Nasabah, dan Biaya Perbankan

Proyek ini menganalisis transaksi perbankan untuk memahami penggunaan media transaksi, pola penggunaan produk oleh nasabah, serta biaya layanan dan keterlambatan. Pengolahan dan visualisasi dilakukan menggunakan Microsoft Excel, Power Query, dan Power Pivot.

> Dataset bersifat simulasi dan digunakan untuk latihan analisis, bukan untuk menggambarkan kinerja bank nyata.

## Pertanyaan Bisnis

1. Media transaksi mana yang perlu diprioritaskan untuk evaluasi pengembangan?
2. Produk apa yang paling banyak digunakan, dan nasabah mana yang dapat menjadi kandidat awal penawaran produk tambahan?
3. Kategori produk mana yang mencatat biaya layanan terbesar dan perlu diprioritaskan untuk evaluasi biaya keterlambatan?

## Dataset

Dataset berasal dari [FP20 Analytics Challenge 27 — Banking Dataset](https://zoomcharts.com/en/microsoft-power-bi-custom-visuals/challenges/fp20-analytics-june-2025).

- 20.000 transaksi
- 8.025 nasabah
- Periode 1 Januari 2023–20 Mei 2025
- Mata uang EUR dan USD
- Mei 2025 merupakan periode parsial

## Proses Analisis

1. Mengimpor dan membersihkan data menggunakan Power Query.
2. Menyesuaikan tipe data dan memeriksa error, nilai kosong, serta duplikasi.
3. Membuat ringkasan nasabah dan menghubungkannya ke data transaksi melalui Data Model.
4. Menghitung metrik menggunakan measure DAX.
5. Membuat PivotTable, PivotChart, KPI, slicer, dan timeline.
6. Menyusun insight serta rekomendasi bisnis dari hasil analisis.

## Dashboard

### 1. Analisis Transaksi dan Media Transaksi

Membandingkan jumlah transaksi berdasarkan media, tren bulanan, kota, serta nilai transaksi berdasarkan jenis dan tahun.

### 2. Analisis Nasabah dan Penggunaan Produk

Menganalisis penggunaan kategori produk dan mencari kandidat awal untuk evaluasi penawaran produk tambahan. Terdapat 112 nasabah dengan satu kategori produk, minimal dua transaksi, dan transaksi terakhir dalam 0–90 hari sebelum 20 Mei 2025.

### 3. Analisis Biaya Layanan dan Biaya Keterlambatan

Membandingkan biaya kartu kredit, biaya asuransi, serta nominal dan persentase transaksi yang dikenai biaya keterlambatan. EUR dan USD dianalisis secara terpisah.

## Temuan Utama

- EUR mencakup 16.974 transaksi, sementara USD mencakup 3.026 transaksi.
- Pada EUR, Mobile memiliki jumlah transaksi tertinggi di antara media transaksi.
- Pada USD, jumlah transaksi di empat media relatif merata.
- Loan mencatat biaya layanan terbesar, terutama melalui biaya asuransi.
- Checking Account memiliki proporsi transaksi dengan biaya keterlambatan tertinggi pada kedua mata uang.
- Kandidat penawaran produk tambahan adalah kelompok awal untuk dievaluasi; kebutuhan dan kepemilikan produk perlu diverifikasi sebelum penawaran.

## Tools

- Microsoft Excel
- Power Query
- Power Pivot
- DAX
- PivotTable dan PivotChart

## File Proyek

- `Banking_Analysis_Dashboard.xlsx` — workbook analisis dan dashboard.
- `Dashboard.pdf` — versi PDF statis dari dashboard.
- `dashboards/` — gambar dashboard untuk preview.
- `docs/` — dokumentasi persiapan data, data dictionary, measure DAX, insight, dan sumber data.

## Catatan

Analisis ini menggunakan data simulasi. Data transaksi tidak menjelaskan penyebab keterlambatan, penerimaan penawaran, keuntungan bank, atau seluruh produk yang dimiliki nasabah. Insight dan rekomendasi merupakan dasar evaluasi, bukan bukti dampak bisnis yang sudah terjadi.