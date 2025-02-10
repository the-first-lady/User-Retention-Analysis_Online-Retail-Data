# Analisis Retensi Pengguna - Data Retail Online

## Ikhtisar
Proyek ini berfokus pada analisis retensi pengguna untuk bisnis ritel online menggunakan data penjualan historis. Tujuannya adalah untuk memahami perilaku pengguna, mengidentifikasi pola retensi, dan mengembangkan strategi untuk meningkatkan retensi pengguna.

## Dataset
Dataset yang digunakan dalam analisis ini adalah **Data Retail Online**, yang berisi data transaksi dari perusahaan ritel online yang berbasis di Inggris dari tahun 2010 hingga 2011. Dataset ini mencakup kolom-kolom berikut:
- `order_id`: Identifikasi unik untuk setiap pesanan.
- `product_code`: Kode yang mewakili setiap produk.
- `product_name`: Nama produk.
- `quantity`: Jumlah produk yang dipesan.
- `order_date`: Tanggal dan waktu ketika pesanan dibuat.
- `price`: Harga per unit produk.
- `customer_id`: Identifikasi unik untuk setiap pelanggan.

## Langkah Proyek

1. **Pembersihan dan Persiapan Data**:
   - Menangani tipe data
   - Menangani nilai yang hilang dalam kolom `product_name` dan `customer_id`.
   - Menangani value pada kolom product_code dan product_name yang mengandung kata "test
   - Menangani duplikasi data
   - Menangani Inaccurate value
   - Menghapus outlier dalam `quantity` dan `amount` menggunakan metode Z-score.

2. **Rekayasa Fitur**:
   - Standarisasi `product_name` dengan mengganti beberapa nama produk dengan nama produk yang paling sering muncul untuk setiap `product_code`.
   - Menambahkan kolom baru 'order_status' dan 'amount'
   - Mengonversi `customer_id` ke tipe string untuk konsistensi.
   - Mengagregasi data transaksi untuk menghitung metrik retensi pengguna.

3. **Analisis Kohort**:
   - Melakukan analisis kohort untuk memvisualisasikan retensi pengguna dari waktu ke waktu.
   - Membuat heatmap untuk menampilkan kohort retensi pengguna untuk setiap bulan.

4. **Visualisasi**:
   - Menggunakan `matplotlib` dan `seaborn` untuk membuat visualisasi seperti heatmap dan diagram batang.
   - Menginterpretasikan visualisasi untuk mendapatkan wawasan dan rekomendasi yang dapat ditindaklanjuti.

## Wawasan Utama
1. **Retensi bulan pertama:** Tingkat retensi tertinggi terjadi di bulan pertama untuk semua cohort, yaitu 100%.
2. **Penurunan retensi:** Secara umum, terjadi tren penurunan tingkat retensi seiring berjalannya waktu untuk semua cohort.
3. **Cohort Januari 2010:** Cohort Januari 2010 memiliki tingkat retensi tertinggi di bulan-bulan terakhir dibandingkan cohort lain, dengan tingkat retensi sebesar 47% di bulan ke-12.
4. **Cohort Februari 2010:** Cohort Februari 2010 menunjukkan penurunan signifikan setelah bulan pertama, dengan retensi hanya sebesar 22% di bulan ke-12.
5. **Cohort Juni 2010:** Cohort Juni 2010 menunjukkan sedikit peningkatan retensi di bulan ke-6 (32%) dibandingkan bulan-bulan sebelumnya.
6. **Cohort Juli hingga Desember 2010:** Cohort dari bulan Juli 2010 hingga Desember 2010 umumnya memiliki tingkat retensi yang lebih rendah dibandingkan cohort sebelumnya.

## Rekomendasi
- **Meningkatkan Proses Onboarding**: Meningkatkan pengalaman onboarding untuk mempertahankan lebih banyak pengguna selama periode awal yang kritis.
- **Intervensi Terarah**: Mengidentifikasi dan mengatasi masalah spesifik yang menyebabkan pengguna berhenti menggunakan untuk meningkatkan retensi keseluruhan.
- **Keterlibatan yang Dipersonalisasi**: Menerapkan strategi keterlibatan yang dipersonalisasi berdasarkan perilaku pengguna untuk mempertahankan minat pengguna dari waktu ke waktu.



Semoga ini membantu! Jika ada pertanyaan lebih lanjut atau bantuan tambahan, jangan ragu untuk menghubungi saya! 😊
