# TUBES-ML
# Analisis Faktor Pembeda Mahasiswa Aktif dan Nonaktif Menggunakan Gradient Boosting

## Deskripsi Proyek
Proyek ini merupakan implementasi machine learning untuk menganalisis faktor-faktor yang membedakan mahasiswa **aktif (Enrolled)** dan **nonaktif (Dropout)** menggunakan algoritma **Gradient Boosting Classifier**.

Penelitian ini memanfaatkan dataset **Predict Students Dropout and Academic Success** dari UCI Machine Learning Repository dan berfokus pada permasalahan **ketidakseimbangan kelas (imbalanced data)** dengan membandingkan beberapa strategi penanganan data tidak seimbang.

---

## Tujuan Penelitian
1. Membangun model klasifikasi untuk membedakan mahasiswa aktif dan nonaktif.
2. Membandingkan performa Gradient Boosting pada beberapa teknik penanganan data tidak seimbang.
3. Mengidentifikasi faktor-faktor yang paling berpengaruh terhadap status mahasiswa menggunakan SHAP.

---

## Dataset
Dataset yang digunakan berasal dari:

- Dataset: Predict Students Dropout and Academic Success
- Sumber: UCI Machine Learning Repository
- ID Dataset: 697

Dataset diakses secara langsung menggunakan library `ucimlrepo`.

---

## Metodologi

### 1. Data Preparation
- Mengunduh dataset dari UCI Repository
- Membersihkan data
- Transformasi target menjadi klasifikasi biner:
  - Enrolled → Aktif
  - Dropout → Nonaktif
- Visualisasi distribusi kelas

### 2. Feature Engineering
- Analisis korelasi fitur
- Pengurangan fitur yang memiliki korelasi tinggi
- Standardisasi fitur menggunakan StandardScaler

### 3. Train-Test Split
- Data dibagi menjadi data latih dan data uji

### 4. Model Training
Model utama yang digunakan adalah:

- Gradient Boosting Classifier

Dengan lima skenario:

1. Baseline
2. Class Weight
3. Tomek Links
4. SMOTE
5. SMOTE + ENN

### 5. Evaluasi Model
Metrik evaluasi yang digunakan:

- Accuracy
- Precision
- Recall
- F1-Score

Hasil setiap model dibandingkan untuk menentukan pendekatan terbaik.

### 6. Explainable AI (XAI)
Interpretasi model dilakukan menggunakan:

- SHAP (SHapley Additive Explanations)

Analisis meliputi:
- Feature Importance
- SHAP Summary Plot
- Pengaruh masing-masing fitur terhadap prediksi model

---

## Struktur Notebook

| Sel | Isi |
|------|------|
| 1 | Setup Environment dan Load Dataset |
| 2 | Transformasi Target dan Visualisasi |
| 3 | Korelasi dan Feature Reduction |
| 4 | Train-Test Split dan Feature Scaling |
| 5 | Penanganan Imbalanced Data dan Training Model |
| 6 | Evaluasi dan Perbandingan Model |
| 7 | Analisis SHAP |

---

## Library yang Digunakan

```bash
pip install ucimlrepo pandas numpy scikit-learn imbalanced-learn shap matplotlib seaborn
```

Library utama:
- pandas
- numpy
- scikit-learn
- imbalanced-learn
- shap
- matplotlib
- seaborn
- ucimlrepo

---

## Cara Menjalankan

1. Clone repository.
2. Install seluruh dependency.
3. Buka notebook `TUBES_ML.ipynb`.
4. Jalankan seluruh sel secara berurutan.
5. Lihat hasil evaluasi model dan analisis SHAP.

---

## Hasil yang Diharapkan
Notebook akan menghasilkan:

- Distribusi kelas sebelum dan sesudah preprocessing
- Analisis korelasi fitur
- Perbandingan performa setiap metode imbalance handling
- Classification Report
- Visualisasi SHAP Feature Importance
- Interpretasi faktor dominan yang memengaruhi status mahasiswa

---

## Kesimpulan
Pendekatan Gradient Boosting yang dikombinasikan dengan teknik penanganan data tidak seimbang dapat digunakan untuk meningkatkan kemampuan prediksi status mahasiswa. Analisis SHAP memberikan interpretasi yang lebih transparan mengenai faktor-faktor yang berkontribusi terhadap keputusan model sehingga hasil penelitian lebih mudah dipahami dan digunakan sebagai bahan pengambilan keputusan akademik.

---

## Author
Tugas Besar Machine Learning
Program Studi Sains Data
Telkom University Surabaya
