# Laporan Proyek Machine Learning - Jessica Vega Nainggolan

## Domain Proyek
Di era digital yang terus berkembang, industri elektronik konsumen, seperti ponsel, jam tangan, laptop, tablet dan lainnya, mengalami pertumbuhan yang signifikan. Dengan berbagai pilihan produk yang tersedia di pasar, memahami perilaku dan preferensi konsumen menjadi sangat penting untuk meningkatkan strategi pemasaran dan pengembangan produk.

Salah satu aspek kunci dalam pemasaran adalah niat pembelian, yang mencerminkan kemungkinan seorang pelanggan untuk melakukan pembelian atau tidak. Memahami faktor-faktor yang mempengaruhi niat pembelian ini dapat membantu perusahaan dalam menyusun strategi yang lebih efektif untuk menarik konsumen.

Dalam konteks ini, usia pelanggan telah diidentifikasi sebagai variabel yang memiliki korelasi tinggi dengan niat pembelian. Usia mempengaruhi keputusan pembelian secara signifikan, karena setiap kelompok usia memiliki kebutuhan, preferensi, dan perilaku belanja yang berbeda. Misalnya, generasi muda mungkin lebih tertarik pada teknologi terbaru dan produk inovatif, sementara generasi yang lebih tua mungkin lebih fokus pada kualitas dan keandalan.

Dengan menggunakan teknik machine learning, proyek ini akan bertujuan untuk membangun model klasifikasi yang dapat memprediksi niat pembelian barang elektronik berdasarkan usia pelanggan. Model ini tidak hanya akan membantu perusahaan dalam memahami hubungan antara usia dan niat pembelian, tetapi juga akan memberikan wawasan yang berharga untuk meningkatkan strategi pemasaran, mengembangkan produ,k dan strategi pemasaran yang lebih terarah.

**Rubrik/Kriteria Tambahan (Opsional)**:
Proyek ini penting untuk diselesaikan karena berpotensi untuk meningkatkan kinerja bisnis dengan memberikan wawasan yang lebih baik tentang perilaku konsumen. Hal ini juga membantu perusahaan dalam mengambil keputusan yang lebih baik dalam hal pemasaran terutama dalam mempreferensi kelompok usia pembeli, pengembangan produk, dan manajemen inventaris. Selain itu, proyek itu akan memberikan kontribusi pada pengembangan ilmu pengetahuan dengan memperkaya pemahaman tentang perilaku konsumen dan penerapan metode analisis data. 

[Pengaruh Shopping Lifestyle, Usia, dan Gender Terhadap Impulse Buying Produk Fashion (Survey Pada Konsumen Produk Fashion di Malang Town Square (Matos))](https://ejournal.umm.ac.id/index.php/jmb/article/view/5383) 

[Pengaruh Usia Dalam Memoderasi Pengaruh Tingkat Kesiapan Teknologi Pada Niat Konsumen Dalam Menggunakan Layanan SMS Banking di Kota Denpasar](https://onesearch.id/Record/IOS2118.article-9453)

## Business Understanding
Dalam proyek ini, pernyataan masalah dan tujuan dari analisis ini adalah:

### Problem Statements

Menjelaskan pernyataan masalah:
1. Bagaimana pemanfaatan model klasifikasi ini dapat membantu meningkatkan kepuasan pelanggan dengan memberikan rekomendasi produk yang lebih relevan bagi kelompok usia tertentu?
2. Model prediksi mana yang paling efektif dalam mengklasifikasikan niat pembelian konsumen elektronik?
3. Bagaimana hasil prediksi niat pembelian dapat digunakan untuk meningkatkan strategi pemasaran dan pengembangan produk perusahaan elektronik?

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
1. Tujuan proyek ini adalah membangun model klasifikasi yang dapat memprediksi niat pembelian pelanggan berdasarkan variabel usia. Dengan ini, perusahaan dapat memberikan rekomendasi produk yang lebih relevan bagi kelompok usia tertentu. Rekomendasi yang lebih sesuai dengan preferensi pelanggan akan meningkatkan kepuasan pelanggan, yang pada akhirnya berkontribusi pada loyalitas dan retensi pelanggan jangka panjang.
2. Memilih model prediksi yang paling optimal untuk digunakan dalam sistem rekomendasi dan pengambilan keputusan bisnis, dengan membandingkan algoritma yang digunakan dalam pembuatan model prediksi niat pembelian.
3. Hasil klasifikasi ini akan digunakan untuk memperbaiki strategi pemasaran dan pengembangan produk. Dengan memanfaatkan hasil prediksi niat pembelian, perusahaan dapat menargetkan kelompok pelanggan yang lebih mungkin untuk membeli produk tertentu, serta menyesuaikan penawaran produk dengan kebutuhan dan preferensi pasar. Ini akan meningkatkan efektivitas kampanye pemasaran dan membantu perusahaan menciptakan produk yang lebih sesuai dengan harapan konsumen.

**Rubrik/Kriteria Tambahan (Opsional)**:
Untuk menyelesaikan masalah ini, beberapa solusi yang diajukan adalah:

  ### Solution statements
  - Menggunakan model Random Forest yang efektif dalam menangani klasifikasi data yang kompleks.
  - Menggunakan model Logistic Regression sebagai baseline model yang sederhana untuk klasifikasi niat pembelian. Meskipun tidak sekompleks Random Forest, model ini memberikan interpretasi yang lebih mudah terhadap hubungan antara fitur. Model ini akan membandingkan performa modelnya dengan Random Forest.
  - Menambahkan hyperparameter tuning untuk memaksimalkan kinerja model.

## Data Understanding
Dataset yang digunakan dalam proyek ini berasal dari platform [Kaggle](https://www.kaggle.com/datasets/rabieelkharoua/consumer-electronics-sales-dataset/data) dengan total 9000 baris dan 9 kolom. Data ini mencakup id produk,	kategori produk,	merk produk,	harga produk,	umur pembeli,	jenis kelamin pembeli,	banyaknya barang yang dibeli,	kepuasan pembeli, dan	niat pembeli dalam melakukan pembelian.


Variabel-variabel pada 'Predict Consumer Electronics Sales Dataset' Kaggle dataset adalah sebagai berikut:
- **ProductID** : Pengidentifikasi unik untuk setiap produk (tipe data `int`).
- **ProductCategory** : Kategori produk elektronik konsumen (tipe data `object`).
- **ProductBrand** : Merek produk ((tipe data `object`)).
- **ProductPrice** : Harga produk (tipe data `float`).
- **CustomerAge** : Usia pelanggan (tipe data `int`).
- **CustomerGender** : Jenis kelamin pelanggan (0 - Pria, 1 - Wanita) (tipe data `int`).
- **PurchaseFrequency** : Jumlah rata-rata pembelian per tahun (tipe data `int`).
- **CustomerSatisfaction** : Peringkat kepuasan pelanggan (1 - 5) (tipe data `int`).
- **PurchaseIntent (Target Variable)** : Niat untuk membeli (tipe data `int`).

Statistik Deskriptif untuk Kolom `PurchaseFrequency`
- **Rata-rata (mean)**: 10.05
- **Standar deviasi (std)**: 5.46
- **Nilai minimum (min)**: 1.00
- **Kuartil 25%**: 5.00
- **Median (50%)**: 10.00
- **Kuartil 75%**: 15.00
- **Nilai maksimum (max)**: 19.00

*Missing Value* 
Data ini  tidak memiliki nilai hilang atau missing value.

Duplikasi Data
Tidak ada data duplikat dalam dataset ini, seperti ditunjukkan oleh output pada code `df.duplicated().sum()`, yang menghasilkan 0.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan visualisasi data menggunakan histogram untuk menampilkan distribusi penjualan berdasarkan kategori produk.

  ![](https://raw.githubusercontent.com/jessicaavg/Machine-Learning-Terapan/main/image.png)

  **Hasil:** Dari grafik di atas, terlihat bahwa penjualan produk:

  - **Smartphones** : 1841
  - **Smart watches** : 1810
  - **Tablets** : 1769
  - **Laptops** : 1842
  - **Headphones** : 1738
  
  Dari hasil tersebut, terlihat jelas bahwa penjualan terbanyak adalah produk **laptop**.

- Menampilkan visualisasi data menggunakan histogram untuk distribusi penjualan berdasarkan merk produk.

  ![](https://raw.githubusercontent.com/jessicaavg/Machine-Learning-Terapan/main/image-1.png)

  **Hasil:** Dari grafik di atas, terlihat bahwa penjualan produk berdasarkan merk:

  - **Samsung** : 1854
  - **Sony** : 1790
  - **HP** : 1820
  - **Apple** : 1760
  - **Other Brand** : 1776
  
  Dari hasil tersebut, terlihat jelas bahwa penjualan terbanyak adalah produk merk **Samsung**.

- Menampilkan visualisasi data menggunakan histogram untuk menunjukkan distribusi usia pelanggan.
  
  ![](https://raw.githubusercontent.com/jessicaavg/Machine-Learning-Terapan/main/image-2.png)

  **Hasil:** Dari grafik di atas, terlihat bahwa rata rata usia pelanggan yang paling umum dalam kelompok pelanggan adalah **umur 43-50 tahun**.

- Melakukan visualisasi data menggunakan pie chart untuk melihat perbandingan, lebih banyak pria atau wanita yang melakukan pembelian.

  ![](https://raw.githubusercontent.com/jessicaavg/Machine-Learning-Terapan/main/image-3.png)

  **Hasil:** Visualisasi diatas digunakan untuk melihat perbandingan, lebih banyak pria atau wanita yang melakukan pembelian. Dengan selisih yang tipis, **pelanggan wanita mendominasi 50.9%** dalam pembelian produk elektronik.

- Menampilkan matriks korelasi untuk menganalisis dan memahami hubungan antara variabel dalam dataset.

  ![](https://raw.githubusercontent.com/jessicaavg/Machine-Learning-Terapan/main/image-4.png)

  **Hasil:** Proses ini bertujuan untuk menghitung dan memvisualisasikan matriks korelasi menggunakan heatmap, memberikan cara yang intuitif untuk menganalisis dan memahami hubungan antara variabel dalam dataset. Dari visualisasi tersebut, terlihat bahwa korelasi tertinggi terdapat antara kolom **CustomerGender dan PurchaseIntent**.

## Data Preparation
Pada tahap ini, dilakukan beberapa persiapan data agar siap untuk digunakan dalam pemodelan. Langkah-langkah yang dilakukan adalah sebagai berikut:

### 1. Menghapus Kolom `ProductID` 
Kolom `ProductID` dihapus karena tidak digunakan dalam proses pembuatan model.

```python
data=data.drop(['ProductID'],axis=1)
```

### 2. Mengubah Variabel Kategori Menjadi Nilai Numerik Pada Kolom `ProductCategory`, `ProductBrand`, dan `ProductPrice` 
Hal ini dilakukan karena algoritma yang akan digunakan memerlukan data dalam format numerik. Melalui proses ini, data dalam kolom ProductCategory, ProductBrand, dan ProductPrice diubah menjadi nilai numerik dan dapat digunakan dalam permodelan.

```python
le_category = LabelEncoder()
data['ProductCategory'] = le_category.fit_transform(data['ProductCategory'])

le_brand = LabelEncoder()
data['ProductBrand'] = le_brand.fit_transform(data['ProductBrand'])

le_price_range = LabelEncoder()
data['ProductPrice'] = le_price_range.fit_transform(data['ProductPrice'])
```

### 3. Split Data Menjadi Data Pelatihan dan Data Pengujian
Proses ini dilakukan agar model dilatih dan dievaluasi secara efektif dan konsisten, sehingga model dapat menggeneralisasi pada data baru yang belum pernah dilihat sebelumnya.

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
  - Data dibagi dengan komposisi 80:20. Data pelatihan 80% dan data test 20% dari keseluruhan data.
  - Random state bernilai 42.

## Model Development
Pada tahap pembuatan model, saya mencoba dua jenis model yang dapat analisis prediksi niat pembelian penjualan barang elektronik, yaitu metode Random Forest dan Logistic Regression. Saya akan menjelaskan proses pengembangan model, parameter yang digunakan, serta bagaimana masing-masing model bekerja.

### Random Forest
Random Forest adalah salah satu algoritma machine learning yang paling populer dan efektif untuk masalah klasifikasi. Algoritma ini mampu menangani dataset besar dengan banyak fitur dan memberikan akurasi yang tinggi. Metode ini bekerja dengan menggabungkan banyak decision trees untuk menghasilkan model klasifikasi yang lebih kuat dan akurat. 

```python
# Inisialisasi model Random Forest
rf_model = RandomForestClassifier(random_state=42)

# Hyperparameter tuning dengan GridSearchCV 
param_grid = {
    'n_estimators': [50, 100, 200],
    'max_depth': [None, 10, 20],
    'min_samples_split': [2, 5]
}
grid_search = GridSearchCV(rf_model, param_grid, cv=5,
  coring='f1_macro', early_stopping=True)
grid_search.fit(X_train, y_train)

# Mendapatkan model terbaik dari hasil GridSearchCV
best_rf_model = grid_search.best_estimator_

# Train model dengan model terbaik
best_rf_model.fit(X_train, y_train)
```

Code diatas menginisialisasi dan melatih model **Random Forest** serta melakukan hyperparameter tuning untuk meningkatkan kinerja model. Parameter yang digunakan pada model ini:

- **random_state**: Parameter untuk mengatur random seed yang bertujuan agar memudahkan reproduksi hasil. Nilai 42 umum digunakan sebagai seed acak default.
- **n_estimators**: Nilai ini menentukan jumlah pohon keputusan dalam hutan acak. Nilai yang lebih tinggi umumnya meningkatkan akurasi, tetapi juga meningkatkan waktu komputasi. Dalam kasus ini, saya akan mencoba 3 nilai yaitu 50, 100, dan 200 pohon.
- **max_depth**: Menentukan kedalaman maksimal dari setiap pohon dalam hutan. Semakin dalam pohon, semakin banyak aturan yang bisa dibuat, tetapi bisa menyebabkan overfitting jika terlalu dalam. Parameter ini ditetapkan dengan 3 nilai yaitu None (tidak ada batasan kedalaman), 10, dan 20.
- **min_samples_split**: Jumlah sampel minimum yang diperlukan untuk membagi sebuah node. Nilai yang lebih tinggi dapat mencegah overfitting. Nilai 2: Default, artinya setiap node akan dibagi jika ada setidaknya 2 sampel. Nilai 5: Setiap node harus memiliki setidaknya 5 sampel untuk dibagi, yang membuat model sedikit lebih general.
- **cv**: Parameter yang mengatur jumlah lipatan dalam validasi silang. 5-fold cross-validation digunakan, yang berarti dataset akan dibagi menjadi 5 bagian, dan model dilatih serta divalidasi sebanyak 5 kali pada subset yang berbeda. 
- **scoring=f1_macro**: Ini adalah metrik evaluasi yang digunakan untuk membandingkan model. F1-score adalah rata-rata harmonik dari precision dan recall, dan 'f1_macro' menghitung rata-rata F1-score untuk semua kelas.
- **early_stopping = True:** Bertujuan untuk menghentikan pelatihan model lebih awal jika performa validasi tidak meningkat setelah beberapa iterasi, sehingga menghemat waktu komputasi.

**Parameter terbaik yang diperoleh dari proses hyperparameter tuning:** 
```python
Best parameters found:  {'max_depth': None, 'min_samples_split': 5, 'n_estimators': 200}
```

Setelah membuat model, dilanjutkan dengan proses melakukan prediksi dan melihat akurasi dari model yang telah dibuat.
```python
# prediksi performa model
y_pred_rf = best_rf_model.predict(X_test)

# akurasi model
accuracy_rf = accuracy_score(y_test, y_pred_rf)
print(f'Accuracy: {accuracy_rf:.2f}')
```
Hasil akurasi dari model Random Forest ini adalah 0.95 atau setara dengan 95%.

### Logistic Regression
Logistic Regression adalah model klasifikasi yang sederhana, efisien, dan mudah diinterpretasikan, menjadikannya pilihan ideal untuk tugas klasifikasi biner. Model ini cepat dalam pelatihan dan prediksi, serta memiliki generalisasi yang baik, sehingga mampu memberikan hasil yang akurat tanpa overfitting. Model bekerja dengan menggunakan fungsi sigmoid yang mengubah hubungan linier antara fitur-fitur tersebut dan variabel target menjadi probabilitas antara 0 dan 1. Selama proses pelatihan, Logistic Regression mempelajari koefisien untuk setiap fitur, yang menunjukkan seberapa besar pengaruh fitur tersebut terhadap keputusan pembelian. Setelah dilatih dengan dataset, model kemudian dievaluasi untuk melihat akurasi prediksinya menggunakan metrik seperti accuracy, precision, recall, dan f1-score.

```python
log_reg = LogisticRegression(max_iter=1000)

# Menentukan parameter grid untuk hyperparameter tuning
param_grid = {
    'C': [0.01, 0.1, 1, 10, 100],  
    'penalty': ['l1', 'l2'],  
    'solver': ['liblinear', 'saga']  
}

# Menggunakan GridSearchCV untuk menemukan hyperparameter terbaik
grid_search = GridSearchCV(log_reg, param_grid, cv=5, scoring='accuracy', n_jobs=-1, verbose=1)
grid_search.fit(X_train, y_train)

# Mendapatkan model terbaik
best_log_reg_model = grid_search.best_estimator_

# Train model dengan model terbaik
best_log_reg_model.fit(X_train, y_train)
```

Parameter yang digunakan pada model ini:
- **max_iter:** Parameter ini mengatur jumlah maksimum iterasi yang dilakukan oleh algoritma optimasi untuk menemukan koefisien model. Nilai 1000 menunjukkan bahwa algoritma akan melakukan maksimal 1000 iterasi sebelum dihentikan.
- **c:** Parameter ini mengontrol kekuatan regularisasi dalam model. Nilai C yang kecil mengindikasikan regularisasi yang kuat, yang dapat membantu mencegah overfitting. Pada grid search ini, nilai C yang diuji adalah [0.01, 0.1, 1, 10, 100], yang memungkinkan kita untuk menemukan nilai C optimal dari rentang tersebut.
- **penalty:** Parameter yang menentukan jenis regularisasi yang digunakan. Dua jenis yang diuji adalah:
  - **'l1'**: L1 regularization (Lasso), yang menghasilkan beberapa koefisien fitur menjadi nol, sehingga berguna untuk feature selection.
  - **'l2'**: L2 regularization (Ridge), yang memperkecil nilai koefisien tanpa membuatnya nol.
- **solver:** Algoritma optimasi yang digunakan untuk menemukan koefisien model. Nilai yang diuji adalah:
  - **'liblinear'**: Cocok untuk masalah klasifikasi biner dan multi-kelas, terutama ketika jumlah fitur sangat besar.
  - **'saga'**: Algoritma yang lebih cepat dan dapat menangani data yang sangat besar, serta mendukung baik L1 dan L2 regularization.

  Proses ini juga menggunakan GridSearchCV agar proses tuning menjadi lebih sistematis dan dapat diulang. Parameter yang digunakan: 
- **cv=5:** Parameter ini mengatur jumlah lipatan (folds) pada cross-validation, di mana data dibagi menjadi 5 subset, model dilatih pada 4 bagian, dan dievaluasi pada 1 bagian yang tersisa.
- **scoring='accuracy':** Parameter ini menginstruksikan GridSearchCV untuk mengevaluasi model berdasarkan metrik akurasi.
- **n_jobs=-1:** Parameter ini memungkinkan penggunaan semua core CPU yang tersedia untuk mempercepat proses komputasi.
- **verbose=1:** Menampilkan informasi lebih detail saat proses tuning berjalan, seperti kemajuan pencarian hyperparameter.

**Parameter terbaik yang diperoleh dari proses hyperparameter tuning:** 
```python
Best parameters found:  {'C': 1, 'penalty': 'l2', 'solver': 'liblinear'}
```

Setelah membuat model, melakukan prediksi dan melihat akurasi dari model yang telah dibuat.
```python
# Prediksi dan evaluasi performa model
y_pred_log = best_log_reg_model.predict(X_test)

# Evaluate the model
accuracy_log = accuracy_score(y_test, y_pred_log)
print(f'Accuracy: {accuracy_log:.2f}')
```
Hasil akurasi dari model Logistic Regression ini adalah 0.85 atau setara dengan 85%.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menggunakan dua algoritma berbeda, yaitu Random Forest dan Logistic Regression

**Kelebihan Random Forest:**
1) Mampu menangani data kompleks dengan performa akurasi yang tinggi.
2) Ensemble banyak pohon membuatnya lebih tahan terhadap overfitting dibanding pohon keputusan tunggal.
3) Baik untuk data yang memiliki hubungan non-linear antar variabel.

**Kekurangan Random Forest:**
1) Butuh waktu lebih lama untuk melatih model, terutama dengan banyaknya pohon.
2) Sulit untuk menginterpretasikan bagaimana tiap fitur berkontribusi terhadap hasil.
3) Model menjadi berat untuk data dengan jumlah fitur atau sampel yang sangat besar.

**Kelebihan Logistic Regression:**
1) Sederhana dan mudah diinterpretasi.
2) Pelatihan model logistic regression relatif cepat, bahkan untuk dataset yang besar.
3) Model logistic regression memberikan output berupa probabilitas kelas, sehingga dapat digunakan untuk perhitungan risiko.

**Kekurangan Logistic Regression:**
1) Sulit menangani data dengan hubungan non-linear.
2) Rentan overfitting jika ada terlalu banyak fitur tanpa regularisasi.
3) Model logistic regression mungkin tidak cukup fleksibel untuk menangkap pola yang kompleks dalam data.

## Evaluation
Pada tahap evaluasi, tujuan utama adalah menilai performa model dalam memprediksi niat pembelian konsumen. Evaluasi ini sangat penting untuk memastikan bahwa model yang telah dibangun dapat memberikan hasil yang akurat dan relevan, terutama pada data yang belum pernah dilihat sebelumnya, yaitu data testing.

Keterkaitan dengan Problem Statement
Masalah yang ingin diselesaikan adalah memprediksi niat pembelian konsumen berdasarkan usia pelanggan, agar dapat memberikan rekomendasi produk yang lebih relevan bagi kelompok usia tertentu. Rekomendasi yang lebih sesuai dengan preferensi pelanggan akan meningkatkan kepuasan pelanggan, yang pada akhirnya berkontribusi pada loyalitas dan retensi pelanggan jangka panjang.

**Hasil Evaluasi Model**

Dua model yang digunakan, Random Forest dan Logistic Regression, di evaluasi menggunakan akurasi, precision, recall, f1-score, dan confusion matrix. Hasil evaluasi sebagai berikut:

**Random Forest**
  - precision: 0.96
  - recall: 0.94
  - f1-score: 0.95
  - support: 793

Proses ini memberikan evaluasi yang komprehensif tentang performa model klasifikasi Random Forest.
* Model klasifikasi memiliki performa yang sangat baik, dengan precision, recall, dan f1-score yang tinggi untuk kedua kelas (0 dan 1).
* Dengan akurasi keseluruhan 95%, model menunjukkan kemampuan yang sangat baik dalam memprediksi kelas dengan benar.
* Keduanya, macro average dan weighted average, menunjukkan nilai metrik yang konsisten, mengindikasikan bahwa model tidak hanya bagus dalam menangani kelas yang lebih besar tetapi juga kelas yang lebih kecil.
* Secara keseluruhan, hasil ini menunjukkan bahwa model telah dilatih dengan baik dan mampu generalisasi dengan baik pada data uji.

**Logistic Regression**
  - precision: 0.85
  - recall: 0.81
  - f1-score: 0.83
  - support: 793

Proses ini memberikan evaluasi yang komprehensif tentang performa model klasifikasi Logistic Regression.
* Model klasifikasi menunjukkan performa yang baik dengan akurasi 85%, lebih rendah dibanding model Random Forest.
* Keduanya, macro dan weighted average, menunjukkan nilai metrik yang sama, mengindikasikan bahwa model tidak hanya berhasil dalam menangani kelas yang lebih besar tetapi juga memiliki kinerja yang baik pada kelas yang lebih kecil.
* Secara keseluruhan, hasil ini menunjukkan bahwa model dilatih dengan cukup baik dan mampu memberikan prediksi yang akurat dan dapat diandalkan pada data uji. Walaupun baik, model Random Forest menggunguli model Logistic Regression dalam keakuratan performa model dalam mengklasifikasikan.

**Dampak Model terhadap Business Understanding:**
1) Pemanfaatan model klasifikasi dapat meningkatkan kepuasan pelanggan dengan memberikan rekomendasi produk yang lebih relevan bagi kelompok usia tertentu. Model ini membantu menganalisis preferensi pelanggan berdasarkan usia, memungkinkan perusahaan untuk memberikan rekomendasi produk yang sesuai dengan kebutuhan masing-masing kelompok usia.
2) Model prediksi yang paling efektif dalam mengklasifikasikan niat pembelian konsumen elektronik adalah model **Random Forest** dengan tingkat akurasi 95%.
3) Hasil klasifikasi ini memungkinkan personalisasi pengalaman belanja, meningkatkan relevansi produk yang ditawarkan, serta mengoptimalkan kampanye pemasaran yang lebih tepat sasaran. 
4) Model yang dibangun berhasil mencapai goals yang diharapkan, yaitu membangun model klasifikasi yang dapat memprediksi niat pembelian pelanggan berdasarkan variabel usia, dapat memilih model prediksi yang paling optimal untuk digunakan dalam sistem rekomendasi dan pengambilan keputusan bisnis, dan hasil klasifikasi ini akan berpotensi untuk memperbaiki strategi pemasaran dan pengembangan produk. Dengan memanfaatkan hasil prediksi niat pembelian, perusahaan dapat menargetkan kelompok pelanggan yang lebih mungkin untuk membeli produk tertentu.

Solusi statement yang direncanakan diawal proyek berdampak pada proses pembuatan model. Model Random Forest terbukti lebih efektif dalam menangani klasifikasi data kompleks, dibuktikan dengan hasil akurasi yang tinggi dan hasil evaluasi model seperti yang sudah dijelaskan sebelumnya. Model Logistic Regression menjadi pembanding dengan performa model Random Forest, walau akurasi yang didapatkan tidak melampaui akurasi Random Forest. Peran hyperparameter tuning pada pembuatan model ini berhasil memaksimalkan kinerja model.

**Rubrik/Kriteria Tambahan (Opsional)**: 
1) Precision: Mengukur seberapa banyak prediksi positif yang benar dari total prediksi positif yang dibuat oleh model.

    **Formula**:
    $$
    \text{Precision} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Positives (FP)}}
    $$

2) Recall: Mengukur seberapa banyak prediksi positif yang benar dari total data positif yang sebenarnya.

    **Formula**:
    $$
    \text{Recall} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Negatives (FN)}}
    $$

3) F1-Score: rata-rata harmonis dari precision dan recall. Ini memberikan gambaran seimbang antara kedua metrik.

    **Formula**:
    $$
    \text{F1-Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}
    $$

4) Support: Sebagai jumlah contoh dari kelas tertentu.
