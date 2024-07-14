# Laporan Proyek Machine Learning - Dyah Kumalarani Mahakerty

## Domain Proyek
Diabetes adalah salah satu penyakit kronis yang prevalensinya terus meningkat di seluruh dunia. Menurut Organisasi Kesehatan Dunia (WHO), diabetes merupakan penyebab utama morbiditas dan mortalitas, dengan estimasi sekitar 422 juta orang di seluruh dunia menderita diabetes pada tahun 2014, dan angka ini terus meningkat setiap tahunnya (WHO,2016). Diabetes dapat menyebabkan berbagai komplikasi serius, termasuk penyakit kardiovaskular, kerusakan saraf, gagal ginjal, dan amputasi anggota tubuh. Biaya ekonomi yang terkait dengan diabetes juga sangat besar, terutama di negara maju seperti Amerika Serikat, di mana total biaya yang diakibatkan oleh diabetes diperkirakan mencapai $327 miliar pada tahun 2017 (American Diabetes Association,2018). Oleh karena itu, deteksi dini dan pengelolaan diabetes yang efektif sangat penting untuk mengurangi beban kesehatan masyarakat sehingga diperlukan solusi yang lebih cepat dan lebih mudah diakses yaitu melalui pengembangan sistem prediksi berbasis machine learning yang dapat mendeteksi risiko diabetes pada tahap awal dengan menggunakan karakteristik kesehatan individu. Sistem ini dirancang untuk memberikan prediksi yang cepat dan akurat mengenai kemungkinan seseorang menderita diabetes sehingga membantu Decision Support selanjutnya, bagaimana gaya hidupnya, dan sebagainya. 

Referensi: 
World Health Organization. (2016). Global report on diabetes. World Health Organization. Retrieved from WHO.
American Diabetes Association. (2018). Economic costs of diabetes in the U.S. in 2017. Diabetes Care, 41(5), 917-928. Retrieved from ADA.


## Business Understanding
### Problem Statements
Adapun beberapa masalah yang diangkat adalah sebagai berikut:

1. Deteksi Dini Diabetes
Diabetes merupakan penyakit kronis yang prevalensinya terus meningkat dan dapat menyebabkan berbagai komplikasi serius jika tidak terdeteksi dan ditangani sejak dini. Pendekatan konvensional untuk diagnosis diabetes biasanya memerlukan tes laboratorium yang mahal dan tidak selalu tersedia, terutama di daerah terpencil atau negara berkembang dengan sumber daya terbatas.

2. Optimalisasi Penggunaan Data Medis
Data medis yang tersedia sering kali tidak dimanfaatkan secara optimal untuk tujuan prediksi dan pencegahan. Padahal, data ini memiliki potensi besar untuk membantu dalam deteksi dini dan manajemen diabetes melalui model prediktif yang akurat.

3. Pendukung Keputusan Klinis
Kebutuhan akan alat bantu yang dapat mendukung pengambilan keputusan klinis yang lebih cepat dan tepat sangat penting untuk meningkatkan kualitas perawatan pasien dan memungkinkan intervensi dini yang lebih efektif dalam mengelola risiko diabetes.


### Goals
Adapun goals yang ingin dicapai yaitu sebagai berikut 
1. Membangun Model Prediktif
Mengembangkan model prediktif berbasis machine learning yang akurat dan andal untuk memprediksi risiko diabetes berdasarkan karakteristik kesehatan individu, seperti kadar glukosa darah, tekanan darah, ketebalan kulit, kadar insulin, dan indeks massa tubuh (BMI).

2. Mendukung Pengambilan Keputusan Klinis
Menyediakan alat bantu bagi tenaga medis untuk pengambilan keputusan klinis yang lebih cepat dan tepat, sehingga dapat meningkatkan kualitas perawatan pasien dan memungkinkan intervensi dini yang lebih efektif dalam mengelola risiko diabetes.

3. Memanfaatkan Data Medis
Mengoptimalkan penggunaan data medis yang mudah diakses dan diukur untuk membangun sistem pendukung keputusan yang efisien, yang dapat memberikan wawasan berharga mengenai faktor risiko dan membantu dalam pencegahan serta pengelolaan diabetes.


### Solution statements
Untuk mencapai tujuan tersebut, beberapa solusi yang diusulkan adalah:

1. Penggunaan Algoritma Machine Learning
Menggunakan beberapa algoritma machine learning untuk membangun model prediktif, termasuk:
Logistic Regression
k-Neighbors Classifier
Decision Tree Classifier
Random Forest Classifier
AdaBoost Classifier
XGBClassifier

2. Evaluasi Model
Melakukan evaluasi model menggunakan metrik performa seperti precision, recall, f1-score, dan akurasi untuk memastikan akurasi dan keandalan prediksi.

3. Peningkatan Model
Melakukan improvement pada baseline model melalui hyperparameter tuning dan teknik lain seperti feature selection dan engineering untuk meningkatkan akurasi dan keandalan prediksi. Selain itu, melakukan validasi silang (cross-validation) untuk memastikan model tidak overfitting dan dapat digeneralisasi dengan baik pada data baru.

Dengan pendekatan ini, diharapkan dapat mengembangkan model prediktif yang efektif dalam mendeteksi risiko diabetes, sehingga dapat membantu dalam intervensi dini dan pengelolaan penyakit yang lebih baik.

## Data Understanding
Dataset ini berasal dari National Institute of Diabetes and Digestive and Kidney Diseases. Tujuan dari dataset ini adalah untuk memprediksi secara diagnostik apakah seorang pasien memiliki diabetes, berdasarkan pengukuran diagnostik tertentu yang termasuk dalam dataset. Beberapa batasan diberlakukan pada pemilihan data ini dari database yang lebih besar. Secara khusus, semua pasien di sini adalah perempuan berusia setidaknya 21 tahun dari keturunan Indian Pima. Dataset ini berjumlah 768 data.

Dataset dapat diunduh di : https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset/data 

### Variabel-variabel pada Diabetes dataset adalah sebagai berikut:
- Pregnancies: Jumlah kehamilan
- Glucose: Kadar glukosa dalam darah
- BloodPressure: Tekanan darah (mm Hg)
- SkinThickness: Ketebalan kulit (mm)
- Insulin: Kadar insulin dalam darah (mu U/ml)
- BMI: Indeks massa tubuh (berat dalam kg/(tinggi dalam m)^2)
- DiabetesPedigreeFunction: Fungsi silsilah diabetes (kemungkinan diabetes berdasarkan riwayat keluarga)
- Age: Usia (tahun)
- Outcome: Hasil diagnosis diabetes (1 jika positif diabetes, 0 jika negatif)


Exploratory Data Analysis (EDA)
Untuk memahami data lebih lanjut, beberapa tahapan eksplorasi data dan visualisasi akan dilakukan, antara lain:
- Statistik Deskriptif: 
Menghitung statistik dasar seperti mean, median, dan standard deviation untuk setiap variabel.
- Membuat pertanyaan proses bisnis untuk memahami data 
Beberapa pernyataannya adalah 
1. Berapa rata-rata BMI untuk usia 50 tahun?
Rata-rata BMI untuk usia 50 tahun
Jawaban: Rata-rata BMI untuk usia 50 tahun: 31.22
Kesimpulan: BMI rata-rata 31.22 menunjukkan bahwa pasien berusia 50 tahun cenderung berada dalam kategori overweight atau obesitas. Ini mengindikasikan bahwa usia 50 tahun memiliki risiko yang lebih tinggi terkait masalah kesehatan yang berkaitan dengan kelebihan berat badan, termasuk diabetes.

2. Rata-rata glukosa untuk pasien yang positif diabetes (Outcome = 1)
Jawaban: Rata-rata glukosa untuk pasien diabetes: 141.26
Kesimpulan: Rata-rata glukosa 141.26 pada pasien yang positif diabetes menunjukkan bahwa pasien dengan diabetes cenderung memiliki kadar glukosa darah yang lebih tinggi dari normal. Ini menunjukkan pentingnya pengelolaan kadar glukosa darah untuk mencegah komplikasi lebih lanjut dari diabetes.
3. Bagaimana distribusi BMI untuk pasien yang memiliki tekanan darah di atas 80?
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/BMI.png)
Berdasarkan grafik distribusi BMI untuk pasien yang memiliki tekanan darah di atas 80, berikut adalah kesimpulan dan insight yang dapat diambil:
Kesimpulan: 
Distribusi BMI untuk pasien dengan tekanan darah di atas 80 menunjukkan distribusi yang mirip dengan distribusi normal, dengan puncak pada kisaran BMI 30-35. Sebagian besar pasien dengan tekanan darah di atas 80 memiliki BMI antara 25 dan 40, yang mengindikasikan bahwa mayoritas pasien dalam kelompok ini berada dalam kategori overweight atau obesitas.
Hubungan antara Tekanan Darah dan BMI:
Pasien dengan tekanan darah di atas 80 cenderung memiliki BMI yang lebih tinggi, yang menunjukkan hubungan antara obesitas dan tekanan darah tinggi. Obesitas adalah faktor risiko yang diketahui untuk hipertensi, dan data ini mendukung hubungan tersebut.

4. Persentase Pasien yang Terkena Diabetes (Outcome = 1)
Jawaban: Persentase pasien yang terkena diabetes: 34.90%
Kesimpulan:  Persentase 34.90% menunjukkan bahwa sekitar sepertiga dari populasi sampel menderita diabetes. Ini merupakan angka yang signifikan dan menunjukkan perlunya intervensi kesehatan masyarakat untuk mengurangi prevalensi diabetes melalui pendidikan, pencegahan, dan pengelolaan penyakit yang lebih baik.

5. Pengaruh Tekanan Darah terhadap Diabetes
Jawaban: Rata-rata tekanan darah pada pasien diabetes: 70.82
Rata-rata tekanan darah pada pasien non-diabetes: 68.18
Kesimpulan: Meski perbedaan tekanan darah antara pasien diabetes dan non-diabetes tidak terlalu besar, tekanan darah rata-rata yang lebih tinggi pada pasien diabetes menunjukkan adanya kecenderungan tekanan darah yang lebih tinggi pada pasien diabetes. Ini mungkin mengindikasikan bahwa pasien diabetes cenderung memiliki masalah tekanan darah yang memerlukan pengelolaan lebih lanjut untuk mencegah komplikasi kardiovaskular.

- Visualisasi Hubungan Antar Variabel:
1. Menggunakan heatmap untuk melihat korelasi antar variabel.
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/heeatmap.png)
2. Mengidentifikasi distribusi data menggunakan histograms atau boxplots.
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/boxplot.png)
Dengan langkah-langkah ini, diharapkan dapat diperoleh pemahaman yang mendalam tentang karakteristik data dan faktor-faktor yang mempengaruhi risiko diabetes, yang selanjutnya akan digunakan untuk membangun model prediktif yang andal.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

- Teknik Data Preparation

1. Analisis Variabel Kategorikal dan Numerikal:
Variabel kategorikal dan numerikal diidentifikasi untuk memahami jenis data yang tersedia. Misalnya, variabel Outcome (target) merupakan variabel kategorikal dengan nilai 0 dan 1, sedangkan variabel numerikal seperti Glucose, BloodPressure, dan lainnya memiliki nilai numerik yang berbeda.


2. Pemeriksaan dan Penanganan Missing Value:
Dilakukan pemeriksaan terhadap nilai yang hilang (missing values) pada dataset. Langkah-langkah yang dilakukan termasuk:
Menghitung jumlah nilai yang hilang untuk setiap variabel.
Memutuskan strategi penanganan nilai yang hilang, seperti imputasi menggunakan mean atau median, atau menghapus baris data yang memiliki nilai yang hilang tergantung pada distribusi data dan signifikansinya terhadap analisis.

3. Pemeriksaan Data Duplikat:
Melakukan pemeriksaan terhadap adanya data duplikat dalam dataset. Data duplikat dapat mempengaruhi hasil analisis statistik dan model machine learning dengan cara yang tidak diinginkan. Dan pada data ini tidak ditemukan data duplikat. 

4. Data Scaling 
Scaling atau normalisasi data dilakukan untuk memastikan bahwa semua variabel numerikal memiliki skala yang sama. Hal ini penting dalam proses pemodelan machine learning, terutama untuk algoritma yang sensitif terhadap skala data, seperti regresi linier, k-NN, dan neural networks. Pada Data ini digunakan MinMaxScaler dari sklearn digunakan untuk melakukan scaling data. Teknik ini mengubah nilai data sehingga berada dalam rentang tertentu, biasanya 0 hingga 1.

5. Melakukan Split Train dan Test
Selanjutnya membagi dataset menjadi set pelatihan dan set pengujian. Pembagian ini dilakukan dengan rasio 85:15, di mana 85% data digunakan untuk pelatihan model dan 15% digunakan untuk pengujian model. Berikut adalah kode untuk pembagian data:
```sh
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.15, shuffle=True, random_state=42)
```

Alasan Data Preparation
- Analisis Variabel Kategorikal dan Numerikal: Memastikan pemahaman yang jelas tentang jenis data yang tersedia untuk mempersiapkan langkah-langkah preprocessing selanjutnya dengan tepat.

- Pemeriksaan dan Penanganan Nilai yang Hilang: Menghindari bias dan mempertahankan integritas data dengan memastikan bahwa data yang hilang diisi dengan cara yang sesuai atau dihapus jika diperlukan.

- Pemeriksaan Data Duplikat: Memastikan keakuratan analisis dan model yang dibangun dengan menghilangkan pengaruh data yang tidak diperlukan.

- Data Scaling : Menghindari Bias: Scaling mencegah fitur dengan skala yang lebih besar mendominasi dalam proses pembelajaran model.

- Melakukan Split Train dan Test : Validasi model pada data baru, identifikasi overfitting dan underfitting, dan pengukuran Kinerja yang Akurat. 

Dengan menerapkan tahapan-tahapan ini, dataset dapat disiapkan dengan baik untuk tahap selanjutnya dalam membangun model prediktif untuk diabetes.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Kami menggunakan beberapa model klasifikasi untuk memprediksi apakah seorang pasien memiliki diabetes atau tidak berdasarkan fitur yang ada. Model yang digunakan antara lain:
Logistic Regression
K-Nearest Neighbors (KNeighborsClassifier)
Decision Tree Classifier
Random Forest Classifier
AdaBoost Classifier
XGBoost Classifier

**Model Building**
Berikut adalah beberapa model machine learning yang digunakan untuk membangun model prediktif diabetes:

Kelebihan dan Kekurangan Model
1. Logistic Regression:
Cara Kerja: Logistic Regression menggunakan fungsi logistik untuk memodelkan probabilitas suatu kejadian berdasarkan regresi linear. Ini sangat efektif untuk masalah klasifikasi biner.
Library yang Digunakan: sklearn.linear_model
Kelebihan: Sederhana dan mudah diinterpretasikan, bekerja dengan baik ketika hubungan antara fitur dan target adalah linear.
Kekurangan: Tidak mampu menangkap hubungan non-linear antara fitur dan target.

2. K-Neighbors Classifier:
Cara Kerja: K-Neighbors Classifier (KNN) menentukan kelas dari titik data baru berdasarkan mayoritas kelas dari k tetangga terdekat dalam ruang fitur.
Library yang Digunakan: sklearn.neighbors
Kelebihan: Mudah diimplementasikan, non-parametrik dan non-linear.
Kekurangan: Membutuhkan banyak memori dan waktu komputasi untuk dataset besar, performa menurun dengan fitur yang banyak (curse of dimensionality).

3. Decision Tree Classifier:
Cara Kerja: Decision Tree mempartisi ruang fitur menjadi daerah yang memiliki label yang sama dengan membuat pohon keputusan dari fitur-fitur yang membagi data dengan cara yang paling informatif.
Library yang Digunakan: sklearn.tree
Kelebihan: Mudah diinterpretasikan, mampu menangkap hubungan non-linear, tidak membutuhkan banyak pra-pemrosesan data.
Kekurangan: Rentan terhadap overfitting, terutama pada dataset yang kecil.

4. Random Forest Classifier:
Cara Kerja: Random Forest membangun banyak pohon keputusan (decision trees) dan menggabungkan hasilnya untuk meningkatkan akurasi dan mengurangi overfitting.
Library yang Digunakan: sklearn.ensemble
Kelebihan: Mengurangi overfitting, mampu menangani dataset dengan fitur yang banyak, robust terhadap missing values.
Kekurangan: Lebih kompleks dan membutuhkan lebih banyak waktu komputasi dibanding decision tree.

5. AdaBoost Classifier:
Cara Kerja: AdaBoost menggabungkan beberapa model lemah (misalnya, pohon keputusan sederhana) dengan memberi bobot lebih pada kesalahan dari model sebelumnya untuk meningkatkan akurasi keseluruhan.
Library yang Digunakan: sklearn.ensemble
Kelebihan: Meningkatkan performa model dasar dengan menggabungkan beberapa model lemah, robust terhadap overfitting.
Kekurangan: Rentan terhadap data outliers dan noise.

6. XGBoost Classifier:
Cara Kerja: XGBoost adalah algoritma boosting yang dioptimalkan untuk efisiensi dan kecepatan. Ini bekerja dengan membangun model secara iteratif dan memperbaiki kesalahan dari model sebelumnya.
Library yang Digunakan: xgboost
Kelebihan: Sangat efisien dan cepat, menangani missing values dengan baik, sering memberikan hasil terbaik dalam kompetisi.
Kekurangan: Lebih kompleks untuk diimplementasikan dan disetel (tuning) dibandingkan model lain.


**Mencari Model yang terbaik menggunakan Matrik Evaluation**
Matrik Evaluasi akan dijelaskan lebih jauh dibawah, untuk hasil dari matrik evaluasi ternyata model yang terbaik yang cocok dengan Diabetes. 
Berikut ini tabel perbandingan hasil dari setiap model 

| Model                    | Precision (0) | Precision (1) | Recall (0) | Recall (1) | F1-score (0) | F1-score (1) | Accuracy | Macro Avg Precision | Macro Avg Recall | Macro Avg F1-score | Weighted Avg Precision | Weighted Avg Recall | Weighted Avg F1-score |
|--------------------------|---------------|---------------|------------|------------|--------------|--------------|----------|---------------------|------------------|--------------------|-----------------------|---------------------|----------------------|
| Logistic Regression      | 0.80          | 0.69          | 0.86       | 0.60       | 0.83         | 0.64         | 0.77     | 0.74                | 0.73             | 0.73               | 0.76                  | 0.77                | 0.76                 |
| k-Neighbors Classifier   | 0.80          | 0.60          | 0.78       | 0.62       | 0.79         | 0.61         | 0.72     | 0.70                | 0.70             | 0.70               | 0.73                  | 0.72                | 0.73                 |
| Decision Tree Classifier | 0.80          | 0.61          | 0.79       | 0.62       | 0.79         | 0.62         | 0.73     | 0.70                | 0.71             | 0.71               | 0.73                  | 0.73                | 0.73                 |
| Random Forest Classifier | 0.81          | 0.59          | 0.75       | 0.68       | 0.78         | 0.63         | 0.72     | 0.70                | 0.71             | 0.70               | 0.74                  | 0.72                | 0.73                 |
| AdaBoost Classifier      | 0.80          | 0.58          | 0.75       | 0.65       | 0.78         | 0.61         | 0.72     | 0.69                | 0.70             | 0.69               | 0.73                  | 0.72                | 0.72                 |
| XGBClassifier            | 0.81          | 0.56          | 0.72       | 0.68       | 0.76         | 0.61         | 0.71     | 0.69                | 0.70             | 0.69               | 0.72                  | 0.71                | 0.71                 |


Dari tabel diatas didapatkan bahwa model **Logistic Regression** dimana memiliki nilai yang selalu tinggi dibandingkan dengan model yang lain yang menunjukkan performa terbaik dengan nilai accuracy sebesar 0.77, serta nilai precision dan recall yang lebih tinggi untuk kelas 0.0 (non-diabetes). Meskipun precision dan recall untuk kelas 1.0 (diabetes) lebih rendah dibandingkan beberapa model lain, Logistic Regression tetap memberikan keseimbangan yang baik antara kedua kelas.

Alasan Pemilihan Logistic Regression:

1. Kinerja Baik pada Data Imbang: Logistic Regression bekerja dengan baik pada dataset yang tidak memiliki imbalance yang ekstrem antara kelas.
2. Interpretabilitas: Model ini mudah diinterpretasikan dan dapat memberikan wawasan yang jelas tentang pengaruh masing-masing fitur terhadap prediksi.
3. Stabilitas: Logistic Regression memiliki performa yang lebih stabil dan konsisten dibandingkan model-model lain yang rentan terhadap overfitting seperti Decision Tree.

## Evaluation
Pada bagian ini, kita akan membahas metrik evaluasi yang digunakan untuk menilai kinerja model machine learning dalam memprediksi apakah seseorang memiliki diabetes berdasarkan karakteristik mereka. Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi, precision, recall, dan F1 score. Berikut adalah penjelasan masing-masing metrik dan hasil evaluasinya.

### Metrik Evaluasi

1. **Akurasi (Accuracy):**
   Akurasi adalah proporsi prediksi yang benar terhadap total prediksi yang dilakukan. Akurasi memberikan gambaran umum tentang seberapa baik model dalam mengklasifikasikan semua kelas.
Formula: 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/a.png)

2. **Precision:**
   Precision adalah proporsi prediksi positif yang benar terhadap total prediksi positif. Precision mengukur keakuratan dari prediksi positif model.
Formula: 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/precision.png)

3. **Recall:**
   Recall adalah proporsi prediksi positif yang benar terhadap total kejadian aktual positif. Recall mengukur kemampuan model untuk menemukan semua kejadian positif.
Formula: 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/recall.png)

4. **F1 Score:**
   F1 Score adalah rata-rata harmonik dari precision dan recall. F1 Score memberikan keseimbangan antara precision dan recall.
Formula: 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/f1.png)

### Hasil Evaluasi

Berdasarkan hasil klasifikasi dari beberapa model, berikut adalah hasil evaluasi untuk model Logistic Regression, yang terpilih sebagai model terbaik:

#### Logistic Regression
- **Precision (class 0.0):** 0.80
- **Recall (class 0.0):** 0.86
- **F1-score (class 0.0):** 0.83
- **Precision (class 1.0):** 0.69
- **Recall (class 1.0):** 0.60
- **F1-score (class 1.0):** 0.64
- **Accuracy:** 0.77

#### Analisis Hasil

1. **Akurasi:**
   Model Logistic Regression memiliki akurasi sebesar 77%, yang menunjukkan bahwa model ini mampu mengklasifikasikan dengan benar 77% dari seluruh prediksi yang dilakukan. Akurasi yang relatif tinggi ini menunjukkan bahwa model memiliki kinerja yang baik secara keseluruhan.

2. **Precision:**
   - Untuk kelas 0.0 (non-diabetes), precision sebesar 0.80 menunjukkan bahwa dari semua prediksi positif non-diabetes, 80% adalah benar.
   - Untuk kelas 1.0 (diabetes), precision sebesar 0.69 menunjukkan bahwa dari semua prediksi positif diabetes, 69% adalah benar.


3. **Recall:**
   - Untuk kelas 0.0 (non-diabetes), recall sebesar 0.86 menunjukkan bahwa model berhasil menemukan 86% dari semua kejadian aktual non-diabetes.
   - Untuk kelas 1.0 (diabetes), recall sebesar 0.60 menunjukkan bahwa model berhasil menemukan 60% dari semua kejadian aktual diabetes.

4. **F1 Score:**
   - Untuk kelas 0.0 (non-diabetes), F1-score sebesar 0.83 menunjukkan keseimbangan yang baik antara precision dan recall.
   - Untuk kelas 1.0 (diabetes), F1-score sebesar 0.64 menunjukkan bahwa ada ruang untuk perbaikan dalam menyeimbangkan precision dan recall.

### Evaluasi Model dan Dampaknya terhadap Business Understanding

Setelah melalui tahap evaluasi model machine learning dengan menggunakan metrik akurasi, precision, recall, dan F1 score, berikut adalah analisis dampak model terhadap pemahaman bisnis yang telah ditetapkan.

1. Apakah Model Sudah Menjawab Problem Statement?
- Deteksi Dini Diabetes
Problem Statement: Perlunya deteksi dini diabetes yang cepat, murah, dan dapat diakses tanpa memerlukan tes laboratorium yang mahal dan tidak selalu tersedia.
Hasil Evaluasi: Berdasarkan hasil evaluasi, model Logistic Regression menunjukkan akurasi sebesar 77%, sementara k-Neighbors Classifier menunjukkan akurasi 72%. Model ini menunjukkan kemampuan yang baik dalam mengidentifikasi pasien yang berisiko diabetes, sehingga dapat membantu dalam deteksi dini tanpa memerlukan tes laboratorium yang mahal.

- Optimalisasi Penggunaan Data Medis
Problem Statement: Data medis yang tersedia sering kali tidak dimanfaatkan secara optimal untuk tujuan prediksi dan pencegahan diabetes.
Hasil Evaluasi: Model prediktif yang dibangun memanfaatkan data medis yang ada secara efektif untuk memprediksi risiko diabetes. Hasil evaluasi menunjukkan bahwa model ini dapat memberikan wawasan berharga mengenai faktor risiko diabetes, yang dapat digunakan untuk tujuan prediksi dan pencegahan.

- Pendukung Keputusan Klinis
Problem Statement: Kebutuhan akan alat bantu yang dapat mendukung pengambilan keputusan klinis yang lebih cepat dan tepat.
Hasil Evaluasi: Model prediktif ini dapat digunakan sebagai alat bantu bagi tenaga medis dalam pengambilan keputusan klinis yang lebih cepat dan tepat. Dengan akurasi yang cukup tinggi, model ini dapat diandalkan untuk memberikan rekomendasi berbasis data.

2. Apakah Model Berhasil Mencapai Goals yang Diharapkan?
- Membangun Model Prediktif
Goal: Mengembangkan model prediktif berbasis machine learning yang akurat dan andal untuk memprediksi risiko diabetes.
Hasil Evaluasi: Model Logistic Regression memberikan performa terbaik dengan akurasi 77%, menunjukkan bahwa model ini dapat memprediksi risiko diabetes dengan baik.

- Mendukung Pengambilan Keputusan Klinis
Goal: Menyediakan alat bantu bagi tenaga medis untuk pengambilan keputusan klinis yang lebih cepat dan tepat.
Hasil Evaluasi: Dengan precision, recall, dan F1 score yang cukup baik, model ini dapat diandalkan untuk mendukung pengambilan keputusan klinis, membantu tenaga medis dalam mengidentifikasi pasien yang berisiko diabetes dengan lebih cepat dan tepat.

- Memanfaatkan Data Medis
Goal: Mengoptimalkan penggunaan data medis untuk membangun sistem pendukung keputusan yang efisien.
Hasil Evaluasi: Data medis yang tersedia telah dimanfaatkan secara optimal untuk membangun model prediktif yang andal. Model ini memberikan wawasan mengenai faktor risiko diabetes dan membantu dalam pencegahan serta pengelolaan diabetes.

3. Apakah Solusi yang Direncanakan Berdampak?
- Penggunaan Algoritma Machine Learning
Solusi: Menggunakan beberapa algoritma machine learning untuk membangun model prediktif.
Dampak: Evaluasi menunjukkan bahwa algoritma Logistic Regression memberikan performa terbaik, diikuti oleh k-Neighbors Classifier. Ini menunjukkan bahwa penggunaan algoritma machine learning efektif dalam membangun model prediktif untuk deteksi dini diabetes.

- Evaluasi Model
Solusi: Melakukan evaluasi model menggunakan metrik performa.
Dampak: Evaluasi model menunjukkan bahwa Logistic Regression memiliki performa terbaik dengan akurasi 77%, yang menunjukkan bahwa model ini andal dan akurat dalam memprediksi risiko diabetes.

- Peningkatan Model
Solusi: Melakukan improvement pada baseline model melalui hyperparameter tuning dan teknik lain seperti feature selection dan engineering.
Dampak: Model Logistic Regression telah di-tuning untuk mencapai performa terbaiknya. Cross-validation juga dilakukan untuk memastikan model tidak overfitting dan dapat digeneralisasi dengan baik pada data baru.

### Kesimpulan

Model Logistic Regression menunjukkan kinerja yang baik dalam memprediksi apakah seseorang memiliki diabetes, dengan akurasi yang tinggi dan nilai precision dan recall yang memuaskan. Namun, ada ruang untuk perbaikan terutama dalam meningkatkan recall untuk kelas diabetes, yang akan membantu dalam menangkap lebih banyak kasus diabetes yang sebenarnya.

Pemilihan metrik evaluasi ini membantu dalam memahami kekuatan dan kelemahan model dalam berbagai aspek, dan memberikan dasar yang kuat untuk pengambilan keputusan lebih lanjut dalam pengembangan dan penyempurnaan model prediksi diabetes.

