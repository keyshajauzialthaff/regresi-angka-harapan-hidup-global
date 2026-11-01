# regresi-angka-harapan-hidup-global

# Faktor-Faktor yang Memengaruhi Angka Harapan Hidup Global (WHO)

Repositori ini berisi laporan dan kode sumber untuk analisis data Angka Harapan Hidup (*Life Expectancy*) menggunakan dataset resmi dari World Health Organization (WHO) melalui Kaggle.
---

## 📊 Tentang Dataset
* **Sumber Dataset:** [Kaggle - WHO Life Expectancy Statistics](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who)
* **Cakupan:** Data dari 193 negara pada rentang tahun 2000 hingga 2015.
* **Tujuan Penelitian:** Meneliti hubungan antara angka harapan hidup dengan berbagai faktor pendukung seperti sistem pendidikan (*schooling*), tingkat pendapatan, dan angka kematian dewasa (*adult mortality*) guna mengidentifikasi area yang memerlukan intervensi untuk meningkatkan kesejahteraan masyarakat.

Dataset ini memiliki **22 variabel**, di antaranya:
1. `Country` (Negara)
2. `Year` (Tahun)
3. `Status` (Kategori Negara: Maju atau Berkembang)
4. `Life Expectancy` (Angka Harapan Hidup dalam satuan tahun)
5. `Adult Mortality` (Angka kematian dewasa usia 15-60 tahun per 1000 penduduk)
6. `infant deaths` (Jumlah kematian bayi per 1000 penduduk)
7. `Alcohol` (Konsumsi alkohol per kapita dalam liter)
8. `percentage expenditure` (Pengeluaran kesehatan sebagai % dari PDB per kapita)
9. `Hepatitis B` (% cakupan imunisasi pada anak 1 tahun)
10. `Measles` (Jumlah kasus campak per 1000 penduduk)
11. `BMI` (Rata-rata BMI populasi)
12. `under-five deaths` (Jumlah kematian balita per 1000 penduduk)
13. `Polio` (% cakupan imunisasi Polio)
14. `Total expenditure` (% pengeluaran pemerintah untuk kesehatan)
15. `Diphtheria` (% cakupan imunisasi Difteri)
16. `HIV/AIDS` (Kematian akibat HIV/AIDS usia 0-4 tahun per 1000 kelahiran)
17. `GDP` (Produk Domestik Bruto dalam USD)
18. `Population` (Jumlah populasi)
19. `thinness 1-19 years` (% prevalensi kurus usia 10-19 tahun)
20. `thinness 5-9 years` (% prevalensi kurus usia 5-9 tahun)
21. `Income composition of resources` (Indeks Pembangunan Manusia/IPM dari komposisi pendapatan, nilai 0-1)
22. `Schooling` (Lama tahun sekolah)

---

## 🛠️ Alur Pengerjaan Proyek

### **BAB 1: Mengumpulkan Data**
* **Penentuan Kebutuhan Data:** Memuat pustaka Python yang diperlukan seperti `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, dan `scipy.stats`.
* **Pengambilan & Pengintegrasian Data:** Mengimpor dataset dari Google Drive ke dalam environment Google Colab untuk diolah lebih lanjut.

### **BAB 2: Menelaah dan Mempersiapkan Data**
* **Pembersihan Nama Kolom:** Menghilangkan spasi tersembunyi pada nama variabel (contoh: `"Life expectancy "` diubah menjadi `"Life Expectancy"`).
* **Seleksi Variabel & Filter Tahun:** Fokus menggunakan data pada **tahun 2015** dengan 4 variabel utama:
  1. `Country`
  2. `Schooling`
  3. `Adult Mortality`
  4. `Life Expectancy`
* **Analisis Statistik Deskriptif & Distribusi:** 
  * Variabel `Schooling` berdistribusi normal.
  * Variabel `Adult Mortality` berdistribusi miring kanan (*right-skewed*).
  * Variabel `Life Expectancy` berdistribusi miring kiri (*left-skewed*).
* **Penanganan Outlier & Missing Value:** 
  * Melakukan pengecekan *missing value* (ditemukan pada variabel `Schooling`).
  * Mendeteksi dan menangani *outlier* pada data menggunakan metode statistik yang sesuai.
