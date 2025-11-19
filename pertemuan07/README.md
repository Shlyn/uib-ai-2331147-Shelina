# Bankrupt Prediction Analysis

Proyek ini bertujuan untuk menganalisis dataset keuangan perusahaan dan memodelkan prediksi kebangkrutan menggunakan beberapa algoritma machine learning: Decision Tree, Random Forest, dan Artificial Neural Network (ANN).

Di dalam proyek ini, terdapat beberapa langkah: **Data Understanding**, **Data Preparation**, **Modelling**, dan **Evaluation**. Setiap langkah menghasilkan **dataset baru** maupun **visualisasi** yang disimpan sebagai file.

---

## 1. Dataset

### Dataset asli

* [`data-bank.csv`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/data-bank.csv)
  Dataset mentah berisi informasi keuangan perusahaan dengan kolom target `Bankrupt?` dan 95 fitur numerik.

### Dataset hasil preprocessing

* [`data-bank_cleaned.csv`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/data-bank_cleaned.csv)
  Dataset setelah pembersihan, standardisasi, dan transformasi (misal log-transform untuk fitur skewed).
* [`data-bank_balanced.csv`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/data-bank_balanced.csv)
  Dataset setelah penanganan ketidakseimbangan kelas menggunakan SMOTE.

---

## 2. Visualisasi (Images)

### 2.1 Data Understanding

* [`boxplot_bivariate.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/boxplot_bivariate.png)
  Box plot hubungan **top 4 fitur** dengan target `Bankrupt?`. Memperlihatkan distribusi fitur untuk kelas 0 dan 1.

* [`scatterplot_bivariate.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/scatterplot_bivariate.png)
  Scatter plot untuk **top 4 fitur numerik** vs target. Memvisualisasikan korelasi dan sebaran data.

* [`heatmap_correlation.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/heatmap_correlation.png)
  Heatmap korelasi **top 10 fitur + target**, mempermudah identifikasi fitur yang paling berhubungan dengan target.

### 2.2 Data Preparation

* [`target_distribution.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/target_distribution.png)
  Visualisasi distribusi target sebelum balancing. Terlihat dataset sangat imbalance (rasio minoritas:mayoritas ≈ 0.033).

* [`target_distribution_balanced.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/target_distribution_balanced.png)
  Visualisasi distribusi target setelah balancing menggunakan SMOTE, sehingga jumlah kelas 0 dan 1 seimbang.

### 2.3 Modelling

* [`roc_curves_comparison.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/roc_curves_comparison.png)
  ROC Curve untuk ketiga model (Decision Tree, Random Forest, ANN) untuk membandingkan performa.

### 2.4 Evaluation

* [`confusion_matrix_decision_tree.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/confusion_matrix_decision_tree.png)
  Confusion matrix Decision Tree.

* [`confusion_matrix_random_forest.png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/confusion_matrix_random_forest.png)
  Confusion matrix Random Forest.

* [`confusion_matrix_ann_(mlp).png`](https://github.com/Shlyn/uib-ai-2331147-Shelina/blob/main/pertemuan07/confusion_matrix_ann_%28mlp%29.png)
  Confusion matrix ANN (MLP).

---

## 3. Ringkasan Workflow

1. **Data Understanding**

   * Analisis korelasi dan hubungan bivariate.
   * Visualisasi boxplot, scatter plot, dan heatmap.

2. **Data Preparation**

   * Cek balance target, missing values, duplicates, dan outliers.
   * Standardisasi fitur numerik.
   * Transformasi fitur skewed dengan log.
   * Penanganan imbalance menggunakan SMOTE.

3. **Modelling**

   * Decision Tree, Random Forest, ANN (MLP).
   * Split data: 80% train, 20% test.
   * Evaluasi dengan accuracy, precision, recall, F1-score, ROC-AUC.

4. **Evaluation**
   * Confusion matrix per model.
   * Perbandingan model berdasarkan ROC-AUC.

---

## 4. Kesimpulan

* Model terbaik berdasarkan ROC-AUC: **Random Forest**.
* Dataset sangat imbalance awalnya, tetapi setelah SMOTE, model memiliki performa sangat baik pada kedua kelas.
* Semua dataset hasil preprocessing dan visualisasi tersimpan sebagai file `.csv` dan `.png` sesuai kebutuhan dokumentasi.
