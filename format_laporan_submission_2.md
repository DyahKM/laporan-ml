# Laporan Proyek Machine Learning - Dyah Kumalarani Mahakerty

## Project Overview
Industri film saat ini mengalami pertumbuhan yang sangat pesat dengan ratusan film baru dirilis setiap tahunnya. Dengan begitu banyaknya pilihan film yang tersedia, pengguna sering kali merasa kewalahan dan kesulitan dalam memilih film yang sesuai dengan preferensi mereka. Tantangan utama yang dihadapi oleh pengguna dalam memilih film meliputi:
- Overload Informasi: Pengguna dihadapkan pada ribuan pilihan film, yang membuat mereka kesulitan untuk menemukan film yang sesuai dengan selera mereka.
- Waktu yang Terbatas: Pengguna memiliki waktu terbatas untuk menelusuri katalog film yang sangat besar, sehingga mereka membutuhkan cara yang cepat dan efisien untuk menemukan film yang mereka sukai.
- Preferensi yang Beragam: Setiap pengguna memiliki preferensi yang unik terhadap genre, aktor, sutradara, dan berbagai atribut film lainnya, sehingga rekomendasi yang bersifat umum tidak selalu efektif.

Pentingnya Sistem Rekomendasi Film
Sistem rekomendasi film dapat memberikan solusi yang efektif untuk mengatasi masalah-masalah di atas. Berikut adalah beberapa alasan mengapa sistem rekomendasi film penting:

1. Personalisasi Konten: Sistem rekomendasi dapat mempersonalisasi pengalaman menonton dengan menyarankan film yang sesuai dengan preferensi individu, sehingga meningkatkan kepuasan pengguna.
2. Meningkatkan Keterlibatan Pengguna: Rekomendasi yang relevan dapat meningkatkan keterlibatan pengguna, membuat mereka lebih sering menonton dan menikmati film.
3. Mengurangi Beban Pengguna: Dengan memberikan rekomendasi yang tepat, sistem ini dapat mengurangi beban pengguna dalam menelusuri dan memilih film, membuat proses pemilihan menjadi lebih mudah dan menyenangkan.
4. Optimisasi Penawaran: Sistem rekomendasi dapat membantu dalam mengoptimalkan penawaran film, memastikan bahwa setiap pengguna menemukan konten yang menarik bagi mereka.

Menurut sebuah studi oleh Ricci et al. (2011), sistem rekomendasi dapat secara signifikan mengurangi masalah overload informasi dengan menyaring konten yang relevan bagi pengguna. Selain itu, rekomendasi yang akurat dapat meningkatkan loyalitas pengguna terhadap platform yang menyediakan layanan ini, serta memaksimalkan pendapatan perusahaan.

Referensi
Ricci, F., Rokach, L., & Shapira, B. (2011). Designing Effective Recommender Systems. Springer. http://www.springerlink.com/content/978-3-642-25694-3

## Business Understanding
### Problem Statements

Berikut adalah beberapa masalah yang ditemui:
1. Kelebihan Pilihan Film: Dengan ribuan film yang dirilis setiap tahunnya, pengguna sering kali mengalami kesulitan dalam memilih film yang sesuai dengan selera mereka. Hal ini menyebabkan pengalaman menonton menjadi kurang memuaskan dan memerlukan waktu yang lama untuk menelusuri berbagai pilihan.

2. Efektivitas Rekomendasi yang Terbatas: Sistem rekomendasi yang ada mungkin tidak selalu mampu memberikan rekomendasi yang akurat, terutama dalam skenario dengan data sparsity atau ketika pengguna memiliki preferensi yang sangat spesifik.

### Goals

Tujuan dibuatnya proyek ini adalah: 
1. Mengurangi Overload Informasi: Mengembangkan sistem rekomendasi yang dapat membantu pengguna menemukan film yang sesuai dengan selera mereka dengan lebih efisien, sehingga mengurangi waktu yang dibutuhkan untuk menelusuri dan memilih film.

2. Meningkatkan Akurasi Rekomendasi: Menggunakan model Singular Value Decomposition (SVD) untuk memberikan rekomendasi yang lebih akurat berdasarkan data rating pengguna, serta mengatasi tantangan data sparsity dan variabilitas preferensi.

### Solution statements
1. Model Singular Value Decomposition (SVD): Menggunakan SVD untuk mengidentifikasi dan memanfaatkan fitur laten dalam data rating film. SVD dapat membantu dalam mengurangi dimensi data dan menemukan pola yang relevan untuk memprediksi rating film yang belum ditonton oleh pengguna. Dengan demikian, SVD dapat meningkatkan akurasi rekomendasi.

2. Evaluasi dengan Metrik Akurasi dan Kualitas: Menggunakan metrik evaluasi seperti Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), dan hit rate untuk menilai efektivitas model rekomendasi. Metrik ini akan membantu dalam mengukur seberapa baik model dalam memberikan rekomendasi yang relevan dan memuaskan bagi pengguna.

3. Pendekatan Collaborative Filtering: Menggunakan collaborative filtering untuk mengidentifikasi pengguna dengan preferensi yang serupa dan memberikan rekomendasi berdasarkan pola rating mereka. Pendekatan ini akan membantu dalam memberikan rekomendasi yang lebih tepat dengan mempertimbangkan preferensi kolektif dari pengguna lain yang memiliki kesamaan minat.

Dengan pendekatan ini, proyek ini bertujuan untuk mengatasi pernyataan masalah yang ada dan mencapai tujuan yang telah ditetapkan, sehingga meningkatkan pengalaman menonton film bagi pengguna.

## Data Understanding
Dataset yang digunakan adalah tentang dataset dunia film yang dapat didownload di [MovieLens-100K](https://www.kaggle.com/datasets/prajitdatta/movielens-100k-dataset/data). Pada database itu memiliki banyak sekali data pendukung, akan tetapi pada proyek ini hanya fokus pada 2 dataset yaitu 

1. u.item: Berisi informasi tentang film. Dataset ini memiliki 722 Data yang sudah bersih dimana tidak terdapat data Null ataupun Data Duplikat. 
Format data adalah sebagai berikut:
movie id: ID unik film.
movie title: Judul film.
release date: Tanggal rilis film.
video release date: Tanggal rilis video (jika ada).
IMDb URL: Tautan ke halaman IMDb film.
unknown: Kategori genre yang tidak diketahui.
Action, Adventure, Animation, Children's, Comedy, Crime, Documentary, Drama, Fantasy, Film-Noir, Horror, Musical, Mystery, Romance, Sci-Fi, Thriller, War, Western: Genre film. Setiap kolom genre adalah biner (1 jika film termasuk genre tersebut, 0 jika tidak).
Kolom-kolom genre adalah fitur yang penting untuk analisis konten dan personalisasi rekomendasi.

2. u.data: Berisi data rating film oleh pengguna. Data ini berisi 100000 rating oleh 943 user pada 1682 item. Setiap pengguna telah memberi peringkat setidaknya 20 film. Pengguna dan item diberi nomor secara berurutan dari 1. Data diurutkan secara acak. Ini adalah daftar yang dipisahkan tab untuk id pengguna, id item, peringkat, dan stempel waktu. Tidak terdapat data Null ataupun Data Duplikat pada data ini. Format data adalah sebagai berikut:
user id: ID unik pengguna.
item id: ID film.
rating: Rating yang diberikan pengguna (dalam rentang 1 hingga 5).
timestamp: Waktu rating diberikan (dalam format UNIX timestamp).
Data ini menyediakan informasi tentang interaksi pengguna dengan film dan merupakan dasar untuk membangun sistem rekomendasi.

Untuk lebih paham mengenai data set yang ada, berikut adalah beberapa Explorator Data Analysis: 
1. Nilai Min dan Max Rata-rata Rating
Min: Rating terendah yang diberikan adalah 1.0.
Max: Rating tertinggi yang diberikan adalah 5.0.
Kesimpulan: Rating dalam dataset ini memiliki rentang dari 1 hingga 5, dengan 1 sebagai rating terendah dan 5 sebagai rating tertinggi. Ini menunjukkan bahwa rating cenderung berfokus pada rentang yang positif.
Berikut adalah grafiknya 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/minmax.png)
Grafik menunjukkan distribusi yang mirip dengan distribusi long tail, di mana hanya sedikit pengguna yang memberikan banyak rating. Ini adalah pola yang umum dalam banyak sistem rekomendasi. Selain itu, Pengguna yang Aktif Memberikan Banyak Rating: Ada sedikit pengguna yang memberikan banyak rating (di atas 200), tetapi jumlah mereka sangat kecil dibandingkan dengan pengguna yang memberikan sedikit rating.

2. Film Paling Populer
Top 10 film dengan jumlah rating terbanyak:
Star Wars (1977): 583 rating
Contact (1997): 509 rating
Fargo (1996): 508 rating
Return of the Jedi (1983): 507 rating
Liar Liar (1997): 485 rating
English Patient, The (1996): 481 rating
Scream (1996): 478 rating
Toy Story (1995): 452 rating
Air Force One (1997): 431 rating
Independence Day (ID4) (1996): 429 rating
Kesimpulan: Film-film di daftar ini adalah yang paling sering dinilai oleh pengguna, menunjukkan bahwa mereka memiliki popularitas yang tinggi.

3. Pengguna Paling Aktif
Top 10 pengguna yang memberikan rating terbanyak:
User ID 405: 737 rating
User ID 655: 685 rating
User ID 13: 636 rating
User ID 450: 540 rating
User ID 276: 518 rating
User ID 416: 493 rating
User ID 537: 490 rating
User ID 303: 484 rating
User ID 234: 480 rating
User ID 393: 448 rating
Kesimpulan: Pengguna di daftar ini adalah yang paling aktif dalam memberikan rating, menunjukkan bahwa mereka mungkin lebih terlibat dalam platform atau memiliki minat yang sangat tinggi terhadap film.

4. Film dengan Rata-rata Rating Tertinggi
Top 10 film dengan rata-rata rating tertinggi:
They Made Me a Criminal (1939): 5.0
Marlene Dietrich: Shadow and Light (1996): 5.0
Saint of Fort Washington, The (1993): 5.0
Someone Else's America (1995): 5.0
Star Kid (1997): 5.0
Great Day in Harlem, A (1994): 5.0
Aiqing wansui (1994): 5.0
Santa with Muscles (1996): 5.0
Prefontaine (1997): 5.0
Entertaining Angels: The Dorothy Day Story (1996): 5.0
Kesimpulan: Film-film ini mendapatkan rating tertinggi dari pengguna, menunjukkan bahwa mereka dianggap sangat memuaskan oleh mereka yang menilai.

5. Film yang Paling Lama Dirilis
Top 10 film dengan tahun rilis tertua:
Nosferatu (1922): 1922-01-01
Scarlet Letter, The (1926): 1926-01-01
Blue Angel, The (1930): 1930-01-01
M (1931): 1931-01-01
Farewell to Arms, A (1932): 1932-01-01
Duck Soup (1933): 1933-01-01
Liebelei (1933): 1933-01-01
Gay Divorcee, The (1934): 1934-01-01
Of Human Bondage (1934): 1934-01-01
It Happened One Night (1934): 1934-01-01
Kesimpulan: Film-film ini adalah yang paling lama dirilis, dengan beberapa film berusia lebih dari 90 tahun, menunjukkan bahwa dataset ini mencakup berbagai era film.

## Data Preparation
Pada tahap Data Preparation, beberapa teknik dilakukan untuk memastikan data siap digunakan dalam proses modeling. Tahapan ini meliputi ekstraksi fitur, penggabungan data, dan pembersihan data. Berikut adalah langkah-langkah yang diterapkan:

- Feature Extraction Rating
1. Mengonversi Data ke dalam Daftar Tuple: Data rating dikonversi menjadi daftar tuple dengan format (userId, movieId, rating) untuk memudahkan analisis lebih lanjut.
2. Menghitung Jumlah Rating untuk Setiap movieId: Jumlah rating untuk setiap movieId dihitung menggunakan struktur data defaultdict untuk menyimpan dan menghitung frekuensi rating.
3. Mengurutkan movieId Berdasarkan Jumlah Rating: movieId diurutkan berdasarkan jumlah rating yang diterima, dari yang terbanyak hingga yang paling sedikit.
 
- Feature Extraction Item
1. Rename Kolom: Nama kolom pada dataset film diganti dengan nama kolom baru yang telah ditentukan agar mudah dipahami.
```sh
new_columns = [
    'movieId', 'movie title', 'release date', 'video release date', 'IMDb URL', 'unknown', 'Action', 'Adventure',
    'Animation', 'Children', 'Comedy', 'Crime', 'Documentary', 'Drama', 'Fantasy', 'Film-Noir', 'Horror',
    'Musical', 'Mystery', 'Romance', 'Sci-Fi', 'Thriller', 'War', 'Western'
]
```
- Merge Rating dan Item
Penggabungan Data: Data rating digabungkan dengan data film berdasarkan movieId untuk mengaitkan rating dengan informasi film.
- Membuat Tabel Pivot
Pivot Table: Tabel pivot dibuat untuk menyusun data dalam format yang lebih terstruktur, dengan userId sebagai baris, movieId sebagai kolom, dan rating sebagai nilai. Tabel ini mempermudah analisis dan modelisasi.
- Checking Missing Values and Duplicates Data
Pemeriksaan Nilai yang Hilang dan Data Duplikat: Data diperiksa untuk nilai yang hilang dan data duplikat. Dalam kasus ini, tidak ditemukan nilai yang hilang atau data duplikat, sehingga data dianggap sudah bersih.

- Split Train and Test 
Melakukan split train/test 75/25 untuk mengukur akurasi. Selain itu juga, Split train/test “leave one out” untuk mengevaluasi rekomendasi top-N. 
1. Split Train/Test 75/25:
Proses ini digunakan untuk mengukur akurasi model dalam memprediksi rating yang belum diketahui dengan menggunakan metrik evaluasi seperti MAE dan RMSE. 

2. Split Train/Test “Leave One Out”:
Proses ini digunakan untuk mengevaluasi kemampuan model dalam memberikan rekomendasi top-N yang relevan. Ini dilakukan dengan menyimulasikan skenario di mana setiap pengguna memiliki satu item yang belum mereka rating, dan kita mencoba untuk merekomendasikan item tersebut.

## Modeling
Pada tahap ini, model sistem rekomendasi dibangun menggunakan teknik Singular Value Decomposition (SVD). Proses ini bertujuan untuk memberikan rekomendasi film yang paling sesuai dengan preferensi pengguna berdasarkan data rating yang ada. 
Secara matematis, SVD mendekomposisi matriks A menjadi sebuah matriks diagonal dan dua matriks unitary:
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/SVD.png)
Setelah data diproses, mulai membangun model dengan menggunakan SVD, yang merupakan pendekatan populer dalam collaborative filtering. Rating dari pengguna merepresentasikan aspek-aspek yang dihasilkan oleh manusia tentang film tersebut. Namun, beberapa karakteristik tidak terlihat jelas tetapi diperlukan untuk prediksi rating. Fitur laten adalah kumpulan dari fitur-fitur tersembunyi. Meskipun tidak tahu secara pasti apa yang setiap fitur laten wakili, namun satu fitur bisa diasumsikan menunjukkan bahwa seorang pengguna menyukai film komedi, sementara fitur laten lain bisa menunjukkan bahwa pengguna menyukai film animasi, dan sebagainya.

Prediksi rating 
𝑃(𝑢,𝑖) dihitung untuk setiap item i, yaitu item yang belum diberi rating oleh pengguna aktif untuk setiap pengguna. Setelah mendapatkan himpunan tetangga pengguna aktif, skor kemiripan diterapkan sebagai bobot untuk memprediksi item yang tidak diberi peringkat oleh pengguna aktif. Rekomendasi dibuat dengan menambahkan jumlah rating yang diharapkan pada item-item terkait, dibobotkan dengan skor kemiripan, dinormalisasi menggunakan jumlah nilai kemiripan, dan menghasilkan film Top N. Daftar film ini kemudian disarankan kepada pengguna saat ini.
Berikut adalah rincian dari tahapan dan hasil rekomendasi
1. Inisialisasi dan Pelatihan Model: Model SVD diinisialisasi dan dilatih menggunakan data latih yang telah disiapkan.
```sh
alg = SVD()
alg.fit(fullTrainSet)
]
```
2. Menghitung Rekomendasi: Setelah model dilatih, prediksi dilakukan untuk mengidentifikasi film-film yang paling sesuai untuk pengguna berdasarkan data rating yang tersedia.
```sh
predictions = alg.test(GetAntiTestSetForUser())
```
3. Mengumpulkan dan Menyusun Rekomendasi: Hasil prediksi diolah untuk menyusun daftar rekomendasi berdasarkan rating yang diperkirakan.
```sh
recommendations = []

print("\nWe recommend:")
for userID, movieID, actualRating, estimatedRating, _ in predictions:
    intMovieID = int(movieID)
    recommendations.append((intMovieID, estimatedRating))

recommendations.sort(key=lambda x: x[1], reverse=True)

for ratings in recommendations[:10]:
    print(getMovieName(ratings[0]), ratings[1])
```
4. Hasil Rekomendasi
Berikut adalah hasil rekomendasi untuk film yang paling sesuai dengan preferensi pengguna berdasarkan model SVD:
```sh
We recommend:
1. Annie Hall (1977) - 4.44
2. Somewhere in Time (1980) - 4.33
3. Cool Hand Luke (1967) - 4.28
4. It Happened One Night (1934) - 4.12
5. Tomorrow Never Dies (1997) - 4.11
6. Mr. Magoo (1997) - 4.10
7. Sirens (1994) - 4.07
8. Pump Up the Volume (1990) - 4.06
9. Jupiter's Wife (1994) - 4.04
10. Local Hero (1983) - 4.03
```
## Evaluation
Tentu, berikut adalah ringkasan evaluasi model rekomendasi yang telah dilakukan:

### 1. Matriks Evaluasi yang Digunakan

- **Mean Absolute Error (MAE)**: Mengukur rata-rata besarnya kesalahan antara nilai prediksi dan nilai aktual. 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/maerec.png)

- **Root Mean Squared Error (RMSE)**: Mengukur rata-rata kesalahan prediksi yang dikuadratkan. 
![image](https://raw.githubusercontent.com/DyahKM/laporan-ml/main/rmserec.png)
- **Hit Rate (HR)**: Mengukur seberapa sering model dapat merekomendasikan item yang tepat.
  
- **Cumulative Hit Rate (cHR)**: Mengukur kemampuan model untuk merekomendasikan item yang disukai pengguna berdasarkan ambang batas tertentu.

- **Average Reciprocal Hit Rank (ARHR)**: Mengukur peringkat rata-rata rekomendasi yang diberikan oleh model.

- **User Coverage**: Mengukur persentase pengguna yang memiliki setidaknya satu rekomendasi yang relevan.
  
- **Diversity**: Mengukur seberapa beragam rekomendasi yang diberikan oleh model. Di mana \(S\) adalah skor kesamaan rata-rata antara setiap pasangan rekomendasi yang mungkin untuk pengguna tertentu.

### 2. Hasil Evaluasi

- **MAE**: 0.743
- **RMSE**: 0.943
- **Hit Rate (HR)**: 0.038
- **Cumulative Hit Rate (cHR)**: 0.038
- **Average Reciprocal Hit Rank (ARHR)**: 0.012
- **User Coverage**: 0.965
- **Diversity**: 0.029

### 3. Kesimpulan dari Tiap Hasil
- Akurasi Prediktif:
RMSE (Root Mean Squared Error): 0.943
MAE (Mean Absolute Error): 0.743
Interpretasi: Nilai RMSE dan MAE yang lebih rendah menunjukkan bahwa model memiliki kemampuan prediksi yang baik dalam memprediksi rating film oleh pengguna. Namun, nilai ini juga menunjukkan bahwa ada sedikit perbedaan antara rating aktual dan rating yang diprediksi.

- Evaluasi Top-N Rekomendasi:
Hit Rate (HR): 0.038
Cumulative Hit Rate (cHR): 0.038
Average Reciprocal Hit Rank (ARHR): 0.012
Interpretasi: Nilai HR dan cHR yang rendah menunjukkan bahwa model jarang merekomendasikan film yang benar-benar disukai oleh pengguna dalam top-N rekomendasi. Nilai ARHR yang rendah menunjukkan bahwa rekomendasi yang benar sering kali berada di peringkat yang lebih rendah dalam daftar top-N.

- Evaluasi Lainnya:
Coverage: 0.965
Diversity: 0.029
Interpretasi: Tingkat coverage yang tinggi menunjukkan bahwa model mampu memberikan rekomendasi yang memenuhi kriteria minimum bagi sebagian besar pengguna. Namun, nilai diversity yang rendah menunjukkan bahwa rekomendasi cenderung kurang beragam.

Dampak Terhadap Business Understanding
- Menjawab Problem Statement:
Problem Statement: Membangun sistem rekomendasi yang dapat meningkatkan keterlibatan pengguna dengan memberikan rekomendasi film yang relevan dan personal.
Evaluasi: Berdasarkan hasil evaluasi, model SVD menunjukkan performa yang baik dalam hal akurasi prediktif tetapi kurang optimal dalam memberikan rekomendasi yang benar-benar relevan kepada pengguna.

- Mencapai Goals yang Diharapkan:
Goals: Meningkatkan keterlibatan pengguna dan kepuasan dengan memberikan rekomendasi film yang sesuai dengan preferensi mereka.
Evaluasi: Meskipun model dapat memprediksi rating dengan akurasi yang baik, kualitas rekomendasi top-N masih perlu ditingkatkan. Hit Rate dan ARHR yang rendah menunjukkan bahwa pengguna tidak sering menemukan rekomendasi film yang benar-benar mereka sukai dalam daftar top-N, yang dapat mengurangi tingkat keterlibatan dan kepuasan pengguna.

- Dampak Solusi yang Direncanakan:
Solusi Statement: Menggunakan model collaborative filtering berbasis SVD untuk memberikan rekomendasi yang personal.
Dampak: Meskipun model memberikan beberapa rekomendasi yang relevan, masih ada ruang untuk peningkatan dalam hal diversifikasi dan relevansi rekomendasi. Meningkatkan nilai diversity dapat membantu memberikan pilihan film yang lebih beragam kepada pengguna, yang pada gilirannya dapat meningkatkan kepuasan pengguna dan keterlibatan mereka dengan platform.


Kesimpulan Keseluruhan
Secara keseluruhan, model SVD yang dibangun telah menunjukkan performa yang baik dalam hal akurasi prediksi tetapi kurang optimal dalam memberikan rekomendasi top-N yang relevan dan beragam. Untuk mencapai tujuan meningkatkan keterlibatan dan kepuasan pengguna, perlu dilakukan peningkatan lebih lanjut pada aspek diversifikasi dan relevansi rekomendasi. Strategi seperti hybrid recommender systems atau penggunaan teknik-teknik tambahan seperti context-aware recommendations dapat dipertimbangkan untuk mengatasi kelemahan yang ada dan mencapai tujuan bisnis secara lebih efektif.