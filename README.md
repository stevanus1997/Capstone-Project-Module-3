# **Customer Lifetime Value Prediction**

Repository ini berisi project untuk memprediksi **Customer Lifetime Value (CLV)** menggunakan dataset pelanggan dan metode **Machine Learning**. Project ini mencakup analisis data, pemodelan, dan evaluasi performa model untuk membantu perusahaan memahami pelanggan bernilai tinggi.

---

## **Table of Contents**

- [Pendahuluan](#pendahuluan)
- [Data yang Digunakan](#data-yang-digunakan)
- [Pipeline Pemodelan](#pipeline-pemodelan)
- [Hasil Evaluasi](#hasil-evaluasi)
- [Visualisasi](#visualisasi)
- [Kesimpulan](#kesimpulan)
- [Rekomendasi](#rekomendasi)

---

## **Pendahuluan**

**Customer Lifetime Value (CLV)** adalah metrik yang digunakan untuk memprediksi nilai yang dihasilkan pelanggan selama mereka berhubungan dengan perusahaan. Dengan memprediksi CLV, perusahaan dapat:

1. Mengidentifikasi pelanggan bernilai tinggi.
2. Mengoptimalkan strategi pemasaran.
3. Meningkatkan retensi pelanggan.

---

## **Data yang Digunakan**

Dataset yang digunakan terdiri dari **5669 baris** dan **12 kolom**, mencakup informasi seperti:

- **Numerical Features**:
  - `Customer Lifetime Value`, `Total Claim Amount`, `Monthly Premium Auto`, `Income`, dll.
- **Categorical Features**:
  - `Vehicle Class`, `Coverage`, `EmploymentStatus`, `Education`, dll.

### **Data Preprocessing**

1. **Handling Skewness**:
   - Transformasi log diterapkan pada beberapa kolom numerik untuk mengurangi skewness.
2. **Encoding Fitur Kategorikal**:
   - One-Hot Encoding dilakukan pada kolom seperti `Vehicle Class`, `Coverage`, dll.
3. **Scaling**:
   - Semua fitur numerik di-standardisasi menggunakan **StandardScaler**.

---

## **Pipeline Pemodelan**

1. **Model yang Digunakan**:

   - **Linear Regression**
   - **KNN**
   - **Decision Tree**
   - **Random Forest**
   - **XGBoost**
   - **Gradient Boosting**

2. **Evaluasi Model**:

   - **RMSE**: Root Mean Squared Error
   - **MAE**: Mean Absolute Error
   - **MAPE**: Mean Absolute Percentage Error
   - **R-Squared**: Kemampuan model menjelaskan variabilitas data.

3. **Hyperparameter Tuning**:
   - Dilakukan **RandomizedSearchCV** untuk mencari parameter terbaik pada model terbaik.

---

## **Hasil Evaluasi**

| **Model**             | **RMSE** | **MAE** | **MAPE** | **R-Squared** |
| --------------------- | -------- | ------- | -------- | ------------- |
| **Random Forest**     | 3731.12  | 1591.22 | 14.42%   | 0.68568       |
| **XGBoost**           | 4061.43  | 1956.07 | 21.14%   | 0.62756       |
| **Gradient Boosting** | 5809.00  | 2578.62 | 8.29%    | 0.62851       |

### **Model Terbaik**: **Random Forest**

- **RMSE** lebih rendah, menunjukkan model lebih baik dalam mengurangi error besar.
- **R-Squared** lebih tinggi, menunjukkan kemampuan model menjelaskan variabilitas target dengan lebih baik.

---

## **Visualisasi**

### **Scatter Plot: Actual vs Predicted CLV**

Model mampu memprediksi nilai CLV dengan baik pada pelanggan dengan nilai CLV rendah hingga sedang. Namun, terdapat bias berupa **overestimation** dan **underestimation** pada nilai CLV tinggi.

![Scatter Plot](scatter_plot.png)

---

### **Feature Importance**

Variabel yang paling berpengaruh terhadap prediksi CLV adalah:

1. **Number of Policies**
2. **Monthly Premium Auto**
3. **Total Claim Amount**
4. **Income**

![Feature Importance](feature_importance.png)

---

## **Kesimpulan**

Berdasarkan analisis dan evaluasi model:

- Model **Random Forest** adalah model terbaik untuk memprediksi CLV, dengan nilai **MAPE sebesar 14.42%**.
- **Fitur penting** yang berkontribusi terhadap CLV adalah jumlah polis, premi bulanan, jumlah klaim, dan pendapatan pelanggan.
- **Variabel demografi** dan **karakteristik kendaraan** memiliki pengaruh yang sangat kecil terhadap prediksi CLV.

---

## **Rekomendasi**

1. **Penggunaan Model**:

   - Gunakan model ini untuk memprediksi pelanggan dengan CLV rendah hingga sedang.
   - Untuk pelanggan dengan CLV tinggi, disarankan pendekatan tambahan seperti segmentasi data atau model khusus.

2. **Improvisasi Model**:

   - Menambahkan fitur baru yang lebih relevan, seperti loyalitas pelanggan atau durasi polis aktif.
   - Melakukan **A/B testing** untuk mengukur dampak model terhadap strategi pemasaran dan retensi pelanggan.

3. **Langkah Lanjutan**:
   - Gunakan insight dari A/B testing untuk meningkatkan performa model di iterasi berikutnya.

---

### **Referensi**

- Jablecka, M. (2020). _Modelling CLV in the Insurance Industry Using Deep Learning Methods._

---

## **How to Use**

1. Clone repository:
   ```bash
   git clone <repository-link>
   ```
