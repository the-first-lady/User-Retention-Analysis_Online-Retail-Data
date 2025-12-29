# Analisis Retensi Pengguna – Data Ritel Online  

## 1. Ikhtisar  
Tujuan proyek ini adalah menganalisis retensi pengguna dalam data transaksi ritel online. Setelah proses pembersihan data, terdapat **352.079 catatan transaksi**. Analisis dilakukan dengan membangun *cohort analysis* untuk memahami tren retensi pelanggan dari waktu ke waktu.  

## 2. Tujuan & Pertanyaan Riset  
**Tujuan:**  
- Mengukur tingkat retensi pelanggan bulanan.  
- Mengidentifikasi *cohort* dengan retensi terbaik dan terburuk.  

**Pertanyaan Riset:**  
- Bagaimana pola retensi dari bulan pertama hingga bulan ke-12?  
- *Cohort* mana yang menunjukkan tingkat retensi tertinggi?  
- Faktor apa yang berkontribusi terhadap penurunan retensi?  

## 3. Deskripsi Data  
- **Jumlah catatan:** 352.079 transaksi setelah pembersihan.  
- **Fitur utama:** order_id, product_code, product_name, quantity, order_date, price, customer_id, year_month, order_status, amount.  
- **Periode waktu:** Data transaksi multi-tahun (contoh *cohort* Januari–Desember 2010).  
- **Kualitas data:**  
  - Nilai hilang dihapus (customer_id & product_name).  
  - Outlier pada quantity & amount difilter menggunakan z-score.  
  - Duplikasi dihapus (6.411 baris).  

## 4. Langkah Utama  
- **Pembersihan Data:** Menghapus nilai hilang, duplikasi, dan outlier.  
- **Rekayasa Fitur:** Membuat kolom year_month, order_status, dan amount.  
- **Standarisasi:** Menyamakan nama produk berdasarkan product_code.  
- **Cohort Analysis:** Membentuk *cohort* berdasarkan bulan transaksi pertama, menghitung tingkat retensi per bulan.  

## 5. Metodologi & Algoritma  
**Proses Cohort Analysis:**  
- Mengagregasi transaksi per pelanggan per bulan.  
- Menentukan *cohort* (bulan transaksi pertama).  
- Menghitung period_num (jarak bulan dari *cohort*).  
- Membuat pivot table → jumlah pelanggan unik per *cohort* & bulan.  
- **Retention rate = pelanggan aktif / ukuran cohort.**  
- Visualisasi: *heatmap* retensi per *cohort*.  

## 6. Metrik Evaluasi  
- **Retention Rate:** Persentase pelanggan yang tetap aktif pada bulan ke-n setelah *cohort* dimulai.  
- **Cohort Size:** Jumlah pelanggan baru pada bulan pertama.  

**Temuan:**  
- Bulan 1 retensi = 100% (baseline).  
- Penurunan tajam setelah bulan ke-2.  
- *Cohort* Januari 2010 → 47% retensi di bulan ke-12.  
- *Cohort* Februari 2010 → hanya 22% retensi di bulan ke-12.  
- *Cohort* Juni 2010 → sedikit peningkatan di bulan ke-6 (32%).  

## 7. Visualisasi & Dashboard  
- **Heatmap Retensi:** Menunjukkan tren penurunan retensi antar *cohort*.  
- **Tabel Cohort Size:** Menampilkan jumlah pelanggan baru per bulan.  

**Insight Visual:**  
- *Cohort* awal (Jan–Jun 2010) menunjukkan retensi lebih kuat.  
- *Cohort* akhir (Jul–Des 2010) umumnya lebih lemah.  

## 8. Keterbatasan & Tantangan  
- **Outlier Data:** Quantity negatif (pesanan dibatalkan) → perlu transformasi.  
- **Cakupan Cohort:** Analisis terbatas pada tahun 2010.  
- **Customer ID Hilang:** 100.920 baris dihapus → potensi kehilangan informasi.  

## 9. Pekerjaan Lanjutan / Rekomendasi  
- Perluasan *cohort analysis* ke tahun-tahun berikutnya.  
- Tambahkan segmentasi berdasarkan kategori produk.  
- Integrasikan *clustering* untuk memprofilkan pelanggan dalam *cohort*.  
- Bangun model prediksi churn berbasis supervised learning.  

## 10. Dampak Bisnis  
- *Cohort* dengan retensi tinggi → kandidat program loyalitas.  
- *Cohort* dengan retensi rendah → target utama kampanye re-engagement.  
- **Insight utama:** Retensi turun tajam setelah bulan ke-2 → perlu strategi onboarding & engagement awal.  

## 11. Insight Strategis  
- **Strategi Retensi:** Fokus pada *cohort* dengan penurunan tajam (misalnya Februari 2010).  
- **Program Loyalitas:** Perkuat *cohort* dengan retensi stabil (misalnya Januari 2010).  
- **Upselling & Bundling:** Dorong *cohort* dengan pesanan kecil untuk meningkatkan keterlibatan.  
- **Optimasi Konversi:** Kurangi *cart abandonment* dan optimalkan checkout untuk meningkatkan retensi.  

## 12. Tools & Lingkungan  
- **Python Libraries:** pandas, numpy, matplotlib, seaborn, scipy.  
- **Lingkungan:** Google Colab untuk analisis interaktif.  
- **Visualisasi:** *Heatmap* retensi *cohort* menggunakan seaborn.  
