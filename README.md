# Bayesian Inference and Logistic Regression Based Modeling for Earthquake Probability Estimation in East Java

# Tujuan Penelitian
Penelitian ini bertujuan untuk mengembangkan kerangka statistik dua tahap yang mengintegrasikan antara pemodelan peluang kejadian dengan analisis parameter serta prediksi gempa bumi di Provinsi Jawa Timur, guna mendukung mitigasi bencana berbasis kuantitatif.

# Metode
Penelitian ini menggunakan pendekatan dua tahap:

**Tahap 1 - Inferensi Bayesian**  
Digunakan untuk mengestimasi peluang harian terjadinya gempa bumi berdasarkan data historis 2014-2024, dengan data kejadian gempa sebanyak 538 dari 3652 hari.

**Tahap 2 - Regresi Logistik**  
Digunakan untuk analisis parameter dan prediksi gempa bumi berkekuatan sedang hingga besar berdasarkan parameter gempa (magnitude, kedalaman, koordinat, dan lokasi). Pemilihan model terbaik dilakukan dengan kriteria AIC.

Implementasi analisis dilakukan menggunakan **R 4.2.2** dengan packages: *stats, ggplot2, car, dplyr*. Visualisasi akhir berupa *bubble plot* dibuat menggunakan **Python (Google Colab)** dengan libraries: *pandas, matplotlib, seaborn, numpy*.

# Data yang Digunakan
Dataset terdiri dari 544 kejadian gempa yang tercatat selama 4018 hari (2014-2024) di Provinsi Jawa Timur. Data diperoleh dari akun resmi BMKG (@infoBMKG) pada platform X.

Parameter yang digunakan:
| Parameter | Deskripsi |
|-----------|-----------|
| Magnitude | Kekuatan gempa (skala Richter) |
| Depth | Kedalaman fokal (km) |
| Latitude | Koordinat episenter |
| Longitude | Koordinat episenter |
| Location | Variabel kategorik lokasi dari BMKG |

# Hasil dan Validasi
# Tahap 1 - Bayesian Inference
Berdasarkan inferensi Bayesian, diperoleh rata-rata peluang harian gempa bumi sebesar **13,5%** dengan 95% *Credible Interval* **12-14%**.

# Tahap 2 - Regresi Logistik
Model regresi logistik terbaik mencapai **AIC = 6**, dengan variabel *magnitude* dan *depth* terbukti signifikan secara statistik (p = 2 × 10⁻¹⁶, α = 0.05). Berdasarkan model, kejadian gempa berisiko tinggi terkonsentrasi di wilayah selatan Jawa Timur.

# Visualisasi Bubble Plot
Visualisasi akhir berupa *bubble plot* yang merangkum hasil prediksi peluang gempa dari model regresi logistik tersedia dalam file `05_forecasting_plot.ipynb`.

# Implementasi Kode
Kode dalam penelitian ini tersebar dalam 4 file R dan 1 file Python (Google Colaboratory):

**R:**
- `01_bayesian` - Inferensi Bayesian untuk peluang gempa harian
- `02_bayesian_subregion` - Inferensi Bayesian untuk peluang gempa per wilayah bagian
- `03_logistic_regression` - Uji signifikansi regresi logistik
- `04_forecasting` - Prediksi dengan ridge regression

**Python (Visualisasi):**
- `05_forecasting_plot.ipynb` - Visualisasi bubble plot hasil prediksi

# Dataset
Dataset berupa data kejadian gempa bumi di Provinsi Jawa Timur tahun 2014-2024 yang bersumber dari BMKG. Data disimpan dalam 1 file:

- `06_dataset.xlsx`
