# Daegu Apartment Price Prediction using Machine Learning

## Project Overview
Project ini merupakan Capstone Project Machine Learning yang bertujuan untuk membangun model regresi dalam memprediksi harga apartemen berdasarkan karakteristik bangunan, fasilitas, dan lokasi. Model dikembangkan untuk membantu proses penentuan harga agar lebih objektif, konsisten, dan berbasis data.

Model terbaik yang dihasilkan pada project ini adalah Extreme Gradient Boost Regression (XGBoost) karena mampu memberikan performa paling stabil dan akurat dibandingkan model regresi lainnya yang diuji.

---

## Business Problem
Penentuan harga apartemen secara manual sering kali bergantung pada subjektivitas dan pengalaman individu. Kesalahan dalam menentukan harga dapat menyebabkan properti sulit terjual atau potensi keuntungan yang tidak maksimal. Oleh karena itu, dibutuhkan pendekatan berbasis machine learning untuk membantu memprediksi harga apartemen secara lebih akurat dan konsisten.

---

## Goals
Tujuan utama dari project ini adalah:
- Membangun model machine learning untuk memprediksi harga apartemen
- Membandingkan beberapa algoritma regresi
- Meningkatkan performa model melalui hyperparameter tuning
- Menghasilkan model yang siap digunakan kembali tanpa perlu training ulang

---

## Dataset
- Dataset: Daegu Apartment Price Dataset  
- Jumlah data awal: lebih dari 4.000 baris  
- Jumlah data setelah preprocessing: sekitar 2.700 baris  
- Target variable: SalePrice  

### Fitur utama
- HallwayType
- TimeToSubway
- YearBuilt
- Size(sqf)
- Jumlah fasilitas di dalam apartemen
- Jumlah fasilitas di sekitar apartemen
- Kapasitas parkir basement

---

## Data Preprocessing
Tahapan preprocessing yang dilakukan meliputi:
- Penghapusan data duplikat
- Penanganan outlier ekstrem berdasarkan domain knowledge
- Penghapusan nilai target yang tidak valid (harga bernilai nol)
- Encoding data kategorikal menggunakan One Hot Encoder dan Binary Encoder
- Reset index setelah proses pembersihan data

---

## Modeling Approach
Beberapa model regresi diuji dan dibandingkan, antara lain:
- Linear Regression
- K-Nearest Neighbors Regression
- Decision Tree Regression
- Random Forest Regression
- Gradient Boosting Regression
- Extreme Gradient Boost Regression (XGBoost)

Evaluasi model dilakukan menggunakan metrik:
- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)
- Root Mean Squared Log Error (RMSLE)
- R-Squared (R²)

---

## Best Model Selection
Berdasarkan hasil benchmarking pada data train dan test, Extreme Gradient Boost Regression dipilih sebagai model terbaik karena:
- Memiliki nilai error paling rendah
- Memiliki nilai R² paling tinggi
- Menunjukkan perbedaan performa yang kecil antara data train dan test (tidak overfitting)

---

## Hyperparameter Tuning
Hyperparameter tuning dilakukan menggunakan GridSearchCV dengan parameter utama:
- learning_rate
- max_depth
- n_estimators

Parameter terbaik yang diperoleh:
- learning_rate = 0.05  
- max_depth = 9  
- n_estimators = 250  

---

## Model Evaluation
Setelah tuning, performa model pada data test adalah:
- MAE ≈ 14.329 SAR  
- MAPE ≈ 23%  

Model bekerja paling optimal pada rentang harga menengah, sementara pada harga ekstrem performa menurun akibat keterbatasan jumlah data.

---

## Feature Importance
Hasil feature importance menunjukkan bahwa YearBuilt merupakan fitur paling berpengaruh dalam menentukan harga apartemen. Hal ini menunjukkan bahwa apartemen dengan tahun pembangunan yang lebih baru cenderung memiliki harga jual yang lebih tinggi.

---

## Save and Load Model
Model akhir disimpan menggunakan library pickle sehingga dapat digunakan kembali tanpa perlu melakukan training ulang. Proses load model menunjukkan performa yang konsisten dengan hasil evaluasi sebelumnya.

---

## Conclusion
Model Extreme Gradient Boost Regression berhasil dibangun dan memberikan performa prediksi yang cukup baik untuk membantu estimasi harga apartemen. Model ini mampu menangkap pola utama pada data dan dapat digunakan sebagai alat bantu pengambilan keputusan berbasis data.

---

## Recommendation
Beberapa rekomendasi untuk pengembangan lanjutan:
- Menambahkan fitur yang lebih merepresentasikan kondisi bangunan secara detail
- Menambah jumlah data, terutama pada segmen harga ekstrem
- Mengembangkan model klasifikasi tambahan untuk menentukan harga kompetitif
- Melakukan monitoring dan retraining model secara berkala jika digunakan di lingkungan produksi

---

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn