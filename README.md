# Bank Customer Classification

## 📌 Project Overview
Proyek ini adalah tahap lanjutan (*Supervised Learning*) dari proyek **[Customer_CLustering_Kmeans](https://github.com/dimasfadhila/Customer_Clustering_KMeans)** yang sebelumnya menggunakan *Unsupervised Learning* (K-Means). 

Setelah nasabah berhasil disegmentasi ke dalam *Cluster 0* (Usia Dewasa) dan *Cluster 1* (Usia Muda), proyek ini membangun model klasifikasi Machine Learning untuk memprediksi segmen nasabah baru secara otomatis dan *real-time* berdasarkan data transaksi mereka, tanpa perlu menjalankan ulang algoritma *clustering* dari awal.

## 🎯 Objectives
* Mengubah data kategorikal nasabah menjadi representasi numerik menggunakan *One-Hot Encoding* (`pd.get_dummies`).
* Membagi dataset menjadi data latih (*training set*) dan data uji (*test set*) dengan proporsi yang seimbang (*stratified*).
* Membangun model klasifikasi *baseline* menggunakan algoritma **Decision Tree**.
* Membangun model yang lebih kompleks menggunakan **Random Forest** dan melakukan optimasi melalui *Hyperparameter Tuning* (**GridSearchCV**).

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Decision Tree, Random Forest, GridSearchCV, train_test_split, metrics)
* **Model Export:** Joblib

## ⚙️ Methodology
1. **Data Loading:** Memuat dataset `data_clustering.csv` yang sudah memiliki kolom `Target` hasil dari *clustering*.
2. **Feature Encoding:** Menggunakan *One-Hot Encoding* untuk mengubah fitur kategorikal bertipe *object* agar dapat diproses oleh model.
3. **Data Splitting:** Membagi data menjadi 80% *Training Set* (1.556 data) dan 20% *Testing Set* (389 data).
4. **Base Modeling:** Melatih model `DecisionTreeClassifier` sebagai *baseline*.
5. **Advanced Modeling & Tuning:** Melatih model `RandomForestClassifier` dan menggunakan `GridSearchCV` (dengan 5-*fold cross-validation*) untuk mencari kombinasi *hyperparameter* terbaik (`n_estimators`, `max_depth`, `min_samples_split`).
6. **Model Serialization:** Menyimpan model terlatih ke dalam format `.h5` menggunakan `joblib` untuk keperluan *deployment*.

## 📈 Results
Evaluasi model pada data uji (*test set*) menunjukkan performa yang luar biasa:

* **Decision Tree (Baseline):** 
  * Accuracy: 1.00 | Precision: 1.00 | Recall: 1.00 | F1-Score: 1.00
* **Random Forest (Tuned):** 
  * Accuracy: 1.00 | Precision: 1.00 | Recall: 1.00 | F1-Score: 1.00

*Catatan: Akurasi 100% ini tercapai karena model Supervised secara efektif berhasil memetakan kembali batasan matematis yang sebelumnya dibuat oleh algoritma K-Means Clustering pada dataset yang sama.*

## 🚀 How to Run the Project
1. Clone repositori ini:
   ```bash
   git clone [https://github.com/dimasfadhila/bank-customer-classification.git](https://github.com/dimasfadhila/bank-customer-classification.git)
