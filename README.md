# Analisis K-Means Clustering pada Tiga Dataset Berbeda

Repositori ini berisi implementasi algoritma *unsupervised machine learning*, K-Means Clustering, untuk melakukan pemetaan dan segmentasi data pada tiga domain studi kasus yang berbeda. Skrip Python (`K-Means-Tiga-Dataset.py`) secara otomatis melakukan prapemrosesan, evaluasi jumlah klaster optimal, hingga visualisasi hasil pengelompokan.

## Studi Kasus & Dataset

Skrip ini memproses tiga dataset berikut:

### 1. Segmentasi Pelanggan Mall (`Mall_Customers.csv`)
* **Tujuan:** Memahami profil pelanggan untuk mengidentifikasi kelompok target potensial guna membantu strategi pemasaran yang lebih terarah.
* **Fitur yang Dianalisis:** `Annual Income` (Pendapatan Tahunan) dan `Spending Score` (Skor Pengeluaran).

### 2. Segmentasi Transaksi Perbankan (`bank_transactions_data_2.csv`)
* **Tujuan:** Memetakan perilaku transaksional nasabah untuk keperluan simulasi deteksi penipuan (*fraud detection*) dan identifikasi anomali transaksi.
* **Fitur yang Dianalisis:** `TransactionAmount` (Nominal Transaksi) dan `AccountBalance` (Saldo Rekening).

### 3. Segmentasi Kualitas Kopi Arabika (`df_arabica_clean.csv`)
* **Tujuan:** Mengidentifikasi profil mutu biji kopi berdasarkan metrik evaluasi sensorik profesional dari *Coffee Quality Institute* (CQI) untuk membedakan kopi komersial dan *specialty*.
* **Fitur yang Dianalisis:** `Aroma` dan `Flavor` (Rasa).

## Metode Evaluasi Klaster
Untuk menentukan jumlah kelompok (K) yang paling optimal dan representatif pada masing-masing dataset, skrip ini menggunakan dua metode evaluasi standar:
1.  **Metode Elbow (WCSS):** Menghitung *Within-Cluster Sum of Squares* untuk meminimalkan variansi internal klaster. Titik optimal berada di area kurva yang membentuk "siku", di mana penambahan klaster tidak lagi mereduksi variansi secara signifikan.
2.  **Metode Silhouette:** Mengukur seberapa baik tingkat pemisahan antar klaster dengan mengevaluasi tingkat kohesi (kedekatan data dengan kelompoknya sendiri) dan separasi (jarak dengan kelompok lain).

## Visualisasi Data
Skrip ini akan secara otomatis menghasilkan beberapa grafik (plot) untuk setiap dataset:
* Grafik garis Metode Elbow (K = 1 hingga 10).
* Grafik garis Metode Silhouette (K = 2 hingga 10).
* *Scatter plot* pemetaan titik data beserta lokasi *Centroid* klaster untuk nilai K dari 1 hingga 5.

## Cara Menjalankan Skrip

**1. Persiapan Dependencies**
Pastikan environment Python Anda telah terinstal *library* yang dibutuhkan:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
