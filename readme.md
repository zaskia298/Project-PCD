# Project PCD 2024 (Kelompok 19)

## Klasifikasi Penyakit Pada Daun Kentang Menggunakan Ekstrasi Fitur

### Data Understanding

Pada project ini digunakan dataset berupa gambar dari daun kentang, dengan total 300 gambar. Dataset ini memiliki 3 label, yaitu Potato___Early_blight, Potato___Late_blight dan Potato___healthy. Dataset diperoleh dari situs kaggle.com. 

### Preprocessing
Adapun preprocessing yang digunakan dalam project ini adalah:
1. Normalisasi
2. Grayscale
3. Smoothing
4. Egde detection
5. Draw Pattern

Teknik-teknik preprocessing di atas dipilih karena memberikan hasil akurasi terbaik terhadap model yang dipilih yaitu KNN, SVM dan RF.

### Feature Selection

Untuk menentukan fitur yang tepat untuk digunakan, diterapkan teknik seleksi fitur berbasis korelasi. Langkah pertama adalah menghitung matriks korelasi absolut dari fitur-fitur dalam dataset untuk mengidentifikasi korelasi antar fitur. Setelah itu, dengan menggunakan bagian segitiga atas dari matriks korelasi ini, dilakukan identifikasi dan penghapusan fitur-fitur yang memiliki korelasi tinggi (lebih dari 0,95) dengan fitur lainnya. Langkah ini penting untuk menghindari redundansi dan overfitting karena fitur-fitur yang sangat berkorelasi biasanya membawa informasi yang mirip dan tidak memberikan nilai tambah bagi model.     

### Modelling

Untuk proses hyperparameter tuning pada model, dilakukan dengan membagi data yang sudah dipilih fiturnya menjadi data latih dan data uji dengan rasio 80:20. Data tersebut dinormalisasi menggunakan min-max scaling agar setiap fitur memiliki skala yang sama, sehingga model machine learning dapat lebih efektif dalam belajar dari data. lalu menggunakan tiga model berbeda: K-Nearest Neighbors (KNN), Support Vector Machine (SVM), dan Random Forest. Setiap model dilatih menggunakan data latih yang dinormalisasi, dan kemudian prediksinya diuji menggunakan data uji yang juga dinormalisasi.

## Evaluation
### Tanpa Preprocessing
Pada percobaan dengan data tanpa preprocessing, dapat diketahui bahwa hasil akurasi yang didapat terbilang cukup rendah. Akurasi dari percobaan tanpa preprocessing dapat dilihat sebagai berikut:
1. K-Nearest Neighbors (KNN) Accuracy: 47 %
2. Support Vector Machine (SVM) Accuracy: 55 %
3. Random Forest Accuracy: 51 %

### Dengan Preprocessing

Pada percobaan dengan data yang telah melalui preprocessing, dapat diketahui bahwa hasil akurasi yang didapat cukup meningkat dibandinngkan dengan melakukan percobaan dengan data tanpa preprocessing. Akurasi dari percobaan dengan data yang telah melalui preprocessing adalah sebagai berikut:
1. K-Nearest Neighbors (KNN) Accuracy: 79 %
2. Support Vector Machine (SVM) Accuracy: 87 %
3. Random Forest Accuracy: 77 %

Beberapa teknik preprocessing yang digunakan dalam project ini meliputi normalisasi, konversi ke grayscale, smoothing, edge detection, dan draw pattern sangat mempengaruhi hasil akurasi. Normalisasi mengubah skala fitur sehingga semua berada dalam rentang yang sama, yang penting untuk algoritma seperti KNN dan SVM yang sensitif terhadap skala fitur. Konversi gambar ke grayscale menyederhanakan data dengan menghilangkan warna yang mungkin tidak diinginkan, sementara smoothing mengurangi noise dalam gambar, sehingga pola yang penting lebih terlihat. Edge detection menyoroti tepi objek dalam gambar, membantu model mengenali bentuk dan struktur daun yang mungkin terkait dengan jenis penyakit. Draw pattern menonjolkan pola tertentu dalam gambar yang berkaitan dengan karakteristik penyakit. Semua teknik ini membantu mengurangi noise, menyeimbangkan skala fitur, menyederhanakan data, dan meningkatkan rasio signal-to-noise, sehingga model machine learning dapat belajar dari data yang lebih bersih (tidak noisy). Sehingga, akurasi model meningkat saat menggunakan data yang telah dipreprocessing dibandingkan dengan data mentah, seperti yang terlihat dari peningkatan akurasi model KNN, SVM, dan Random Forest dalam project ini.






