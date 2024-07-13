# Laporan Proyek Machine Learning - Dyah Kumalarani Mahakerty

## Domain Proyek
Diabetes adalah salah satu penyakit kronis yang prevalensinya terus meningkat di seluruh dunia. Menurut Organisasi Kesehatan Dunia (WHO), diabetes merupakan penyebab utama morbiditas dan mortalitas, dengan estimasi sekitar 422 juta orang di seluruh dunia menderita diabetes pada tahun 2014, dan angka ini terus meningkat setiap tahunnya(WHO,2016). Diabetes dapat menyebabkan berbagai komplikasi serius, termasuk penyakit kardiovaskular, kerusakan saraf, gagal ginjal, dan amputasi anggota tubuh. Biaya ekonomi yang terkait dengan diabetes juga sangat besar, terutama di negara maju seperti Amerika Serikat, di mana total biaya yang diakibatkan oleh diabetes diperkirakan mencapai $327 miliar pada tahun 2017 (American Diabetes Association,2018). Oleh karena itu, deteksi dini dan pengelolaan diabetes yang efektif sangat penting untuk mengurangi beban kesehatan masyarakat.

**Rubrik/Kriteria Tambahan (Opsional)**:
Mengapa dan bagaimana masalah tersebut harus diselesaikan? Deteksi dini diabetes memungkinkan intervensi medis dan perubahan gaya hidup yang dapat memperlambat atau bahkan mencegah perkembangan komplikasi serius. Namun, metode konvensional untuk diagnosis diabetes biasanya memerlukan tes laboratorium yang mungkin tidak selalu tersedia, terutama di daerah terpencil atau di negara berkembang dengan sumber daya terbatas. Oleh karena itu, diperlukan solusi yang lebih cepat dan lebih mudah diakses untuk memprediksi risiko diabetes berdasarkan karakteristik kesehatan individu. 

Referensi: 
World Health Organization. (2016). Global report on diabetes. World Health Organization. Retrieved from WHO.
American Diabetes Association. (2018). Economic costs of diabetes in the U.S. in 2017. Diabetes Care, 41(5), 917-928. Retrieved from ADA.

## Business Understanding

Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

### Problem Statements
Adapun beberapa beberapa masalah yang diangkat adalah sebagai berikut
- Pernyataan Masalah 1:
Diabetes merupakan penyakit kronis yang prevalensinya terus meningkat dan dapat menyebabkan berbagai komplikasi serius jika tidak terdeteksi dan ditangani sejak dini. Metode konvensional untuk diagnosis diabetes biasanya memerlukan tes laboratorium yang mungkin tidak selalu tersedia, terutama di daerah terpencil atau negara berkembang dengan sumber daya terbatas.

- Pernyataan Masalah 2:
Tingginya biaya ekonomi yang terkait dengan diabetes, termasuk biaya perawatan kesehatan dan produktivitas yang hilang, memerlukan solusi yang lebih efisien untuk mengurangi beban ekonomi ini.

- Pernyataan Masalah 3:
Data medis yang tersedia sering kali tidak dimanfaatkan secara optimal untuk tujuan prediksi dan pencegahan, padahal data ini memiliki potensi besar untuk membantu dalam deteksi dini dan manajemen diabetes.


### Goals
Adapun goals yang ingin dicapai yaitu sebagai berikut 
- Jawaban Pernyataan Masalah 1:
Mengembangkan model prediktif berbasis machine learning yang dapat memprediksi risiko diabetes berdasarkan karakteristik kesehatan individu, sehingga memungkinkan deteksi dini tanpa memerlukan tes laboratorium yang mahal dan tidak selalu tersedia.

- Jawaban Pernyataan Masalah 2:
Mengurangi biaya ekonomi yang terkait dengan diabetes dengan menyediakan alat prediksi yang murah dan mudah diakses, yang dapat membantu dalam pengambilan keputusan klinis dan intervensi dini.

- Jawaban Pernyataan Masalah 3:
Memanfaatkan data medis yang ada untuk membangun model prediktif yang andal, yang dapat memberikan wawasan berharga tentang faktor risiko dan membantu dalam pencegahan serta pengelolaan diabetes.

**Rubrik/Kriteria Tambahan (Opsional)**:
### Solution statements
- Solution Statement 1:
Menggunakan beberapa algoritma machine learning untuk membangun model prediktif, termasuk:
Linear Regression: LinearRegression()
Lasso: Lasso()
Ridge: Ridge()
k-Neighbors Regression: KNeighborsRegressor()
Decision Tree: DecisionTreeRegressor()
Random Forest Regressor: RandomForestRegressor(n_estimators=100, random_state=0)
AdaBoost Regressor: AdaBoostRegressor()
XGBRegressor: XGBRegressor()

- Solution Statement 2:
Melakukan evaluasi model menggunakan metrik performa seperti Mean Squared Error (MSE), Mean Absolute Error (MAE), dan Root Mean Squared Error (RMSE) untuk memastikan akurasi dan keandalan prediksi.

- Solution Statement 3:
Melakukan improvement pada baseline model melalui hyperparameter tuning dan teknik lain seperti feature selection dan engineering untuk meningkatkan akurasi dan keandalan prediksi. Selain itu, melakukan validasi silang (cross-validation) untuk memastikan model tidak overfitting dan dapat digeneralisasi dengan baik pada data baru.

Dengan pendekatan ini, diharapkan dapat mengembangkan model prediktif yang efektif dalam mendeteksi risiko diabetes, sehingga dapat membantu dalam intervensi dini dan pengelolaan penyakit yang lebih baik.

## Data Understanding
Dataset ini berasal dari National Institute of Diabetes and Digestive and Kidney Diseases. Tujuan dari dataset ini adalah untuk memprediksi secara diagnostik apakah seorang pasien memiliki diabetes, berdasarkan pengukuran diagnostik tertentu yang termasuk dalam dataset. Beberapa batasan diberlakukan pada pemilihan data ini dari database yang lebih besar. Secara khusus, semua pasien di sini adalah perempuan berusia setidaknya 21 tahun dari keturunan Indian Pima. 

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

**Rubrik/Kriteria Tambahan (Opsional)**:
Exploratory Data Analysis (EDA)
Untuk memahami data lebih lanjut, beberapa tahapan eksplorasi data dan visualisasi akan dilakukan, antara lain:
- Statistik Deskriptif: 
Menghitung statistik dasar seperti mean, median, dan standard deviation untuk setiap variabel.
- Membuat pertanyaan proses bisnis untuk memahami data 
Beberapa pernyataannya adalah 
1. Berapa rata-rata BMI untuk usia 50 tahun?
```sh
#rangkuman analisis statistik
df.describe()
```

2. Berapa rata-rata glukosa untuk pasien yang positif diabetes (Outcome = 1)?
```sh
# Filter data untuk usia 50 tahun
df_age_50 = df[df['Age'] == 50]

# Hitung rata-rata BMI
average_bmi = df_age_50['BMI'].mean()
print(f"Rata-rata BMI untuk usia 50 tahun: {average_bmi:.2f}")
```
Jawaban : Rata-rata BMI untuk usia 50 tahun: 31.22
3. Bagaimana distribusi BMI untuk pasien yang memiliki tekanan darah di atas 80?
```sh
# Filter data untuk pasien diabetes (Outcome = 1)
df_diabetes = df[df['Outcome'] == 1]

# Hitung rata-rata glukosa
average_glucose_diabetes = df_diabetes['Glucose'].mean()
print(f"Rata-rata glukosa untuk pasien diabetes: {average_glucose_diabetes:.2f}")
```
Jawaban: Rata-rata glukosa untuk pasien diabetes: 141.26
4. Persentase Pasien yang Terkena Diabetes (Outcome = 1)
```sh
# Hitung persentase pasien yang terkena diabetes
percentage_diabetes = (df['Outcome'].mean()) * 100
print(f"Persentase pasien yang terkena diabetes: {percentage_diabetes:.2f}%")
```
Jawaban: Persentase pasien yang terkena diabetes: 34.90%
5. Pengaruh Tekanan Darah terhadap Diabetes
```sh
# Filter data untuk pasien dengan diabetes (Outcome = 1) dan tanpa diabetes (Outcome = 0)
df_diabetes = df[df['Outcome'] == 1]
df_non_diabetes = df[df['Outcome'] == 0]

# Hitung rata-rata tekanan darah pada pasien diabetes dan non-diabetes
average_bp_diabetes = df_diabetes['BloodPressure'].mean()
average_bp_non_diabetes = df_non_diabetes['BloodPressure'].mean()

print(f"Rata-rata tekanan darah pada pasien diabetes: {average_bp_diabetes:.2f}")
print(f"Rata-rata tekanan darah pada pasien non-diabetes: {average_bp_non_diabetes:.2f}")
```
Jawaban: Rata-rata tekanan darah pada pasien diabetes: 70.82
Rata-rata tekanan darah pada pasien non-diabetes: 68.18

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
Melakukan pemeriksaan terhadap adanya data duplikat dalam dataset. Data duplikat dapat mempengaruhi hasil analisis statistik dan model machine learning dengan cara yang tidak diinginkan. Jika ditemukan data duplikat, langkah selanjutnya adalah menghapusnya dari dataset.

Alasan Data Preparation
- Analisis Variabel Kategorikal dan Numerikal: Memastikan pemahaman yang jelas tentang jenis data yang tersedia untuk mempersiapkan langkah-langkah preprocessing selanjutnya dengan tepat.

- Pemeriksaan dan Penanganan Nilai yang Hilang: Menghindari bias dan mempertahankan integritas data dengan memastikan bahwa data yang hilang diisi dengan cara yang sesuai atau dihapus jika diperlukan.

- Pemeriksaan Data Duplikat: Memastikan keakuratan analisis dan model yang dibangun dengan menghilangkan pengaruh data yang tidak diperlukan.

Dengan menerapkan tahapan-tahapan ini, dataset dapat disiapkan dengan baik untuk tahap selanjutnya dalam membangun model prediktif untuk diabetes.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Kami menggunakan beberapa model klasifikasi untuk memprediksi apakah seorang pasien memiliki diabetes atau tidak berdasarkan fitur yang ada. Model yang digunakan antara lain:
Logistic Regression
K-Nearest Neighbors (KNeighborsClassifier)
Decision Tree Classifier
Random Forest Classifier
AdaBoost Classifier
XGBoost Classifier

1. **Melakukan Split Train dan Test**
Langkah pertama dalam pemodelan adalah membagi dataset menjadi set pelatihan dan set pengujian. Pembagian ini dilakukan dengan rasio 85:15, di mana 85% data digunakan untuk pelatihan model dan 15% digunakan untuk pengujian model. Berikut adalah kode untuk pembagian data:
```sh
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.15, shuffle=True, random_state=42)
```
2. **Model Building**
Berikut adalah beberapa model machine learning yang digunakan untuk membangun model prediktif diabetes:

Kelebihan dan Kekurangan Model
1. Logistic Regression:
Kelebihan: Sederhana dan mudah diinterpretasikan, bekerja dengan baik ketika hubungan antara fitur dan target adalah linear.
Kekurangan: Tidak mampu menangkap hubungan non-linear antara fitur dan target.

2. K-Neighbors Classifier:
Kelebihan: Mudah diimplementasikan, non-parametrik dan non-linear.
Kekurangan: Membutuhkan banyak memori dan waktu komputasi untuk dataset besar, performa menurun dengan fitur yang banyak (curse of dimensionality).

3. Decision Tree Classifier:
Kelebihan: Mudah diinterpretasikan, mampu menangkap hubungan non-linear, tidak membutuhkan banyak pra-pemrosesan data.
Kekurangan: Rentan terhadap overfitting, terutama pada dataset yang kecil.

4. Random Forest Classifier:
Kelebihan: Mengurangi overfitting, mampu menangani dataset dengan fitur yang banyak, robust terhadap missing values.
Kekurangan: Lebih kompleks dan membutuhkan lebih banyak waktu komputasi dibanding decision tree.

5. AdaBoost Classifier:
Kelebihan: Meningkatkan performa model dasar dengan menggabungkan beberapa model lemah, robust terhadap overfitting.
Kekurangan: Rentan terhadap data outliers dan noise.

6. XGBoost Classifier:
Kelebihan: Sangat efisien dan cepat, menangani missing values dengan baik, sering memberikan hasil terbaik dalam kompetisi.
Kekurangan: Lebih kompleks untuk diimplementasikan dan disetel (tuning) dibandingkan model lain.


3. **Mencari Model yang terbaik menggunakan Matrik Evaluation**
Matrik Evaluasi akan dijelaskan lebih jauh dibawah, untuk hasil dari matrik evaluasi ternyata model yang terbaik yang cocok dengan Diabetes ini adalah 
model **Logistic Regression** yang menunjukkan performa terbaik dengan nilai accuracy sebesar 0.77, serta nilai precision dan recall yang lebih tinggi untuk kelas 0.0 (non-diabetes). Meskipun precision dan recall untuk kelas 1.0 (diabetes) lebih rendah dibandingkan beberapa model lain, Logistic Regression tetap memberikan keseimbangan yang baik antara kedua kelas.

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

### Kesimpulan

Model Logistic Regression menunjukkan kinerja yang baik dalam memprediksi apakah seseorang memiliki diabetes, dengan akurasi yang tinggi dan nilai precision dan recall yang memuaskan. Namun, ada ruang untuk perbaikan terutama dalam meningkatkan recall untuk kelas diabetes, yang akan membantu dalam menangkap lebih banyak kasus diabetes yang sebenarnya.

Pemilihan metrik evaluasi ini membantu dalam memahami kekuatan dan kelemahan model dalam berbagai aspek, dan memberikan dasar yang kuat untuk pengambilan keputusan lebih lanjut dalam pengembangan dan penyempurnaan model prediksi diabetes.


**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

