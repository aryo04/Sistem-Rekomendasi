# Laporan Proyek Machine Learning - Aryo Daffa Khairuddin

## Project Overview

Banyak orang merasa kesulitan dalam menemukan produk yang sesuai dengan preferensi mereka ditengah banyaknya pilihan yang tersedia, sehingga dibutuhkan solusi yang dapat membantu menyederhanakan proses pencarian tersebut. Sistem rekomendasi menjadi salah satu solusinya karena mampu memberikan pengalaman belanja yang lebih personal, efisien, dan relevan. Dengan adanya sistem ini, pengguna dapat memperoleh saran produk yang sesuai tanpa harus menelusuri seluruh katalog secara manual, sehingga mempermudah dalam pencarian dan meningkatkan kepuasan pelanggan. Berdasarkan penelitian oleh El-Demerdash et al. (2023) menjelaskan bahwa sistem rekomendasi dalam e-commerce fashion secara signifikan memengaruhi keputusan pembelian konsumen melalui pemanfaatan preferensi pribadi, tren terkini, serta data sosial pengguna.

Selain memanfaatkan riwayat interaksi pengguna, pendekatan modern dalam sistem rekomendasi juga mengintegrasikan analisis visual menggunakan teknologi kecerdasan buatan. Berdasarkan penelitian oleh Chang et al. (2025) mengembangkan sistem rekomendasi berbasis Convolutional Neural Networks (CNN) yang mampu mengenali ciri visual dari produk fashion seperti warna, bentuk, dan gaya. Melalui pendekatan ini, rekomendasi menjadi lebih akurat bahkan ketika data interaksi pengguna masih terbatas. Oleh karena itu, pengembangan sistem rekomendasi berbasis AI menjadi strategi penting untuk meningkatkan daya saing dan retensi pengguna di sektor e-commerce fashion.

Refrensi:
- El-Demerdash, D., El-Sheikh, K., & Abou-Ghali, M. (2023). Fashion Recommendation System and its Impact on Consumers’ Purchase Decision Making. International Design Journal, 13(1), 195–206. [link](https://www.researchgate.net/publication/366780313_Fashion_Recommendation_System_and_its_Impact_on_Consumers'_Purchase_Decision_Making)
- Chang, C.-C., Wei, C.-H., Wang, Y.-H., Yang, C.-H. T., & Hsiao, S. (2025). Recommender System for Apparel Products Based on Image Recognition Using Convolutional Neural Networks. Engineering Proceedings, 89(1), 38. [link](https://www.mdpi.com/2673-4591/89/1/38)

## Business Understanding

### Problem Statements
   1. Bagaimana distribusi Rating produk berdasarkan setiap Category?

   2. Bagaimana cara memberikan rekomendasi produk fashion yang relevan berdasarkan atribut produk seperti Product Name, Brand, Category, Color, dan Size?

### Goals
   1. Menganalisis distribusi rating produk berdasarkan setiap kategori untuk mengetahui kategori dengan rating tertinggi.

   2. Membangun sistem rekomendasi berbasis konten (Content-Based Filtering) yang menyarankan produk serupa berdasarkan fitur-fitur produk dalam dataset.

### Solution Approach
1. Visualization

   - Mengeksplorasi Category dan Rating untuk mengidentifikasi preferensi pengguna terhadap jenis fashion tertentu.

   - Menggunakan visualisasi seperti bar chart dan boxplot untuk menunjukkan distribusi rating per kategori.

2. Content-Based Filtering (CBF)

   - Menggunakan atribut produk seperti Product Name, Brand, Category, Color, dan Size untuk membangun profil produk.

   - Menggunakan teknik One-Hot Encoding  untuk mengubah produk menjadi representasi vektor.

   - Menggunakan Cosine Similarity dan Euclidean Distance untuk menemukan produk serupa dan memberikan rekomendasi.

## Data Understanding
Dataset yang digunakan berasal dari platform Kaggle dengan judul '[Fashion Product](https://www.kaggle.com/datasets/bhanupratapbiswas/fashion-products/data)' yang dibuat oleh Bhanupratap Biswas mengenai berbagai produk fashion dari beberapa merek dan kategori dan dataset ini terdiri dari 1000 baris dan 9 kolom.

### Variabel pada Dataset

| **Variabel** | **Deskripsi**                                                  | **Tipe Data**     |
| ------------ | -------------------------------------------------------------- | ----------------- |
| User ID      | Identifikasi unik untuk pengguna yang memberikan peringkat     | Numerik (int)     |
| Product ID   | Identifikasi unik untuk setiap produk fashion                  | Numerik (int)     |
| Product Name | Nama produk (T-shirt, Dress, Shoes, Jeans, Sweater)            | Kategorikal       |
| Brand        | Merek produk (Adidas, Nike, Zara, H\&M, Gucci)                 | Kategorikal       |
| Category     | Kategori produk (Men's Fashion, Women's Fashion, Kids')        | Kategorikal       |
| Price        | Harga produk                                                   | Numerik (int)     |
| Rating       | Peringkat produk yang diberikan pengguna (skala 1 sampai 5)    | Numerik (float)   |
| Color        | Warna produk (Black, White, Blue, Red, Green)                  | Kategorikal       |
| Size         | Ukuran produk (S, M, L, XL)                                    | Kategorikal       |

### Kondisi Awal Dataset
- Terdiri dari 1000 baris dan 9 kolom.
- Tipe data dalam dataset terdiri dari 5 kategorikal dan 4 numerik.
- Tidak terdapat outlier.
- Tidak terdapat rating dengan nilai 0.
- Tidak terdapat missing value.
- Tidak terdapat data yang duplikat.

### Eksploratory Data Analyst
1. Distribusi Variabel Kategorikal

![Distribusi Variabel Kategorikal](https://github.com/user-attachments/assets/285e112a-945c-4be8-881e-bdda49f0260a)

**Insight** :

- `Category` : Tiga kategori fashion (Men’s, Women’s, Kid’s) memiliki distribusi yang cukup seimbang, namun Kid’s Fashion sedikit lebih tinggi.

- `Brand` : Semua brand populer (Adidas, H&M, Zara, Gucci, Nike) memiliki jumlah produk yang hampir merata, dengan Nike sedikit lebih tinggi.

- `Color` : Warna White paling sering muncul, diikuti oleh Yellow dan Blue. Warna Red paling sedikit.

- `Size` : Distribusi merata dengan XL dan L sedikit lebih tinggi dibandingkan s dan m.

- `Product Name` : Produk Jeans dan Shoes paling tinggi, sementara Sweater memiliki jumlah paling sedikit.

2. Distribusi Rating per Kategori

![Distribusi Rating per Kategori](https://github.com/user-attachments/assets/df4111d2-a6a9-4f0a-b2ff-51bf9c1b2ec1)

**Insight** :

- Ketiga kategori (`Men's Fashion, Women's Fashion, dan Kids Fashion`) menunjukkan distribusi rating yang serupa, dengan rentang rating dari 1 hingga 5.

- Median rating dari ketiga kategori berada di sekitar 3, dengan:

  * `Women's Fashion` dan `Kid's Fashion` memiliki median sedikit lebih tinggi dari `Men's Fashion`.

  * Ini mengindikasikan bahwa produk di dua kategori tersebut cenderung mendapat penilaian lebih tinggi secara konsisten dibanding `Men's Fashion`.

- IQR terlihat cukup lebar di semua kategori, menunjukkan keragaman penilaian pengguna cukup besar.

3. Rata-rata Rating per Kategori

![Rata-rata Rating per Kategori](https://github.com/user-attachments/assets/d2b51dda-c5a9-4eb7-a1f2-75de207dc899)

**Insight** :

- `Kids' Fashion` memiliki rata-rata rating tertinggi

   Nilai rata-rata rating kategori ini sedikit di atas 3.0, menunjukkan bahwa secara umum, 
   produk-produk Kids' Fashion lebih disukai oleh pelanggan dibanding dua kategori lainnya.

- `Women's Fashion` berada di urutan kedua

   Rata-rata rating-nya tepat di angka 3.0, menandakan kepuasan pelanggan yang cukup baik dan 
   stabil.

- `Men's Fashion` memiliki rata-rata rating terendah

   Dengan rata-rata rating sedikit di bawah 3.0, Men's Fashion tampaknya memiliki performa 
   penilaian pengguna yang sedikit lebih rendah dibandingkan dua kategori lainnya.

4. Distribusi Variabel Numerik

![Distribusi Variabel Numerik](https://github.com/user-attachments/assets/a851bc49-6c5a-4fce-a2e0-c6d8d86b2729)

**Insight** :

- Harga produk tersebar merata di rentang 10 hingga 100 dan distribusi harga cenderung datar, menunjukkan ketersediaan produk di berbagai level harga secara seimbang.

- Rating tersebar dari 1 hingga 5, dengan puncak pada rating 3 dan Rrating 1 dan 5 juga cukup tinggi, menunjukkan pengalaman pengguna yang beragam—baik sangat puas maupun sangat tidak puas.

## Data Preparation
Berdasarkan kondisi awal dataset, tidak diperlukan lagi tahapan untuk melakukan pengangan rating dengan nilai 0, pengangan missing value, menghapus data duplikat, dan menangani outlier, sehingga hanya perlu melakukan tahap sebagai berikut:

1. Seleksi Fitur
   ```
   features = ['Product Name', 'Brand', 'Category', 'Color', 'Size']
   data_features = df[features]
   ```
- Seleksi fitur dilakukan untuk menentukan atribut yang paling relevan dalam menghasilkan rekomendasi yang bermakna. Fitur Product Name, Brand, Category, Color, dan Size dipilih karena mewakili karakteristik utama produk fashion yang memengaruhi preferensi pengguna.

2. Encoding
   ```
   encoder = OneHotEncoder(sparse_output=False, handle_unknown='ignore')
   encoded_features = encoder.fit_transform(data_features)
   encoded_df = pd.DataFrame(encoded_features, columns=encoder.get_feature_names_out(features))
   ```
- Fitur seperti Product Name, Brand, Category, Color, dan Size bersifat kategorikal, sedangkan cosine similarity memerlukan data dalam format numerik. Jadi, digunakan One-Hot Encoding untuk mengubah setiap kategori menjadi vektor biner, memungkinkan perhitungan kesamaan matematis antar produk dan sistem dapat mengukur jarak atau kesamaan antar produk berdasarkan atribut ini.

3. Penggabungan Data
   ```
   encoded_df = pd.concat([encoded_df, df[['Product ID', 'Product Name', 'Brand', 'Category', 
   'Color', 'Size', 'Rating', 'Price']]], axis=1)
   ```
- Setelah encoding, DataFrame hanya berisi vektor biner yang sulit diinterpretasikan tanpa konteks asli. Menambahkan kolom referensi seperti Product ID, Product Name, Brand, Category, Color, Size, Rating, dan Price memungkinkan pengguna untuk memahami produk yang direkomendasikan dengan jelas.


**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Dalam proyek ini, sistem rekomendasi dikembangkan dengan pendekatan Content Based Filtering dan menggunakan dua algoritma , yaitu Cosine Similarity dan Euclidean Distance. Kedua algoritma ini menggunakan representasi vektor hasil encoding atribut produk sebagai dasar perhitungan kemiripan antar item.

### Solusi 1: Cosine Similarity
- Perhitungan Cosine Similarity:

   Cosine Similarity menghitung kesamaan antara dua vektor berdasarkan sudut di antara keduanya. Vektor dibentuk dari atribut produk yang telah diubah menjadi 
   representasi numerik melalui encoding.
   
   Rumus perhitungan Cosine Similarity antara dua vektor A dan B:
   
   ![Rumus perhitungan Cosine Similarity](https://github.com/user-attachments/assets/d57245ae-ce75-4e86-9c10-5b36faffec3a)
   
   Nilai cosine similarity berkisar antara 0 hingga 1. Semakin mendekati 1, semakin mirip dua vektor tersebut.

 - Fungsi Rekomendasi
   Langkah-langkah:
   
   - Mengencode data input menggunakan encoder yang sama.
   
   - Menghitung nilai cosine similarity antara input dan seluruh data.
   
   - Mengurutkan skor dari yang tertinggi.
   
   - Mengambil Top-N produk paling mirip sebagai hasil rekomendasi. 

### Solusi 2: Euclidean Distance
- Perhitungan Euclidean Distance
  Euclidean Distance menghitung jarak antar dua vektor dalam ruang berdimensi banyak:
  
  ![image](https://github.com/user-attachments/assets/1b63fdb4-559d-43de-aa96-2bcacbb10e98)

  Agar dapat digunakan sebagai skor kesamaan (semakin tinggi berarti semakin mirip), maka dilakukan transformasi:

  ![image](https://github.com/user-attachments/assets/515d8385-01bf-4f36-bf90-8f844aa5ec72)

  Nilai similarity akan semakin besar jika jarak semakin kecil, dan sebaliknya.

- Fungsi Rekomendasi
  Langkah-langkah fungsi:
   
  - Melakukan encoding terhadap atribut input.
   
  - Menghitung jarak Euclidean antara input dengan semua produk dalam dataset.
   
  - Mengubah hasil jarak menjadi skor similarity.
   
  - Mengurutkan hasil berdasarkan skor tertinggi.
   
  - Mengambil Top-N produk sebagai hasil rekomendasi.

### Kelebihan dan Kekurangan

| Pendekatan         | Kelebihan                                                         | Kekurangan                                                         |
| ------------------ | ----------------------------------------------------------------- | ------------------------------------------------------------------ |
| Cosine Similarity  |  Tidak terpengaruh oleh panjang vektor (skala)                    |  Tidak mempertimbangkan jarak absolut antar fitur                 |
|                    |  Cocok untuk data yang sparse (banyak nol)                        |  Hanya fokus pada arah atau pola kemunculan atribut               |
| Euclidean Distance |  Lebih intuitif secara geometris (jarak langsung antar titik)     |  Sensitif terhadap fitur dominan jika data tidak dinormalisasi    |
|                    |  Cocok jika semua fitur dianggap memiliki kontribusi yang setara  |  Bisa memberikan skor rendah meski atribut sebenarnya hampir sama |

### Contoh Output Top-5 Recommendation   
- Rekomendasi Cosine Similarity dengan input Shoes, Zara, Men's Fashion, White, S

  ![image](https://github.com/user-attachments/assets/25b88681-26bc-4634-98b2-0dc178edccf4)

- Rekomendasi Euclidean Distance dengan input  Shoes, Zara, Men's Fashion, White, S

  ![image](https://github.com/user-attachments/assets/c010101a-30db-44c9-9dac-5407a69f9049)

## Evaluation
Sistem rekomendasi ini menggunakan dua metrik utama untuk mengukur kualitas rekomendasi, yaitu Precision@K dan Recall@K. Metrik ini sesuai dengan tujuan sistem yang memberikan rekomendasi Top-N produk berdasarkan kesamaan atribut.

1. Precision@K

   Definisi:

   Precision@K mengukur seberapa tepat rekomendasi yang diberikan dalam daftar Top-K item. Artinya, dari K item yang direkomendasikan, berapa proporsi yang benar- 
   benar relevan dengan preferensi pengguna.

   Formula:
   
   `Precision@K = Jumlah item relevan yang direkomendasikan / K`

   Keterangan:

   - K adalah jumlah item yang direkomendasikan (misalnya 5 jika menggunakan Top-5).
   
   - Item relevan adalah produk yang sesuai dengan preferensi pengguna berdasarkan atribut atau skor kemiripan yang melewati threshold tertentu.

   Cara Kerja:

   - Sistem memilih K item terbaik (misalnya K=5) berdasarkan skor kemiripan (similarity score) atau jarak (distance).

   - Precision dihitung dengan menghitung berapa banyak dari K item tersebut yang relevan (sesuai preferensi pengguna).

   - Precision tinggi berarti rekomendasi yang diberikan mayoritas relevan, sehingga pengguna mendapatkan rekomendasi berkualitas dan tidak “banyak sampah”.

2. Recall@K
   
   Definisi:
   
   Recall@K mengukur seberapa lengkap rekomendasi yang diberikan dalam menemukan semua item relevan yang tersedia di dataset. Artinya, dari semua item relevan 
   yang ada, berapa persen yang berhasil direkomendasikan dalam Top-K.
   
   Formula:
   
   `Recall@K= Jumlah item relevan yang direkomendasikan / Jumlah total item relevan`
   
   Keterangan:

   - Jumlah total item relevan adalah semua produk yang sesuai dengan preferensi pengguna dalam keseluruhan dataset.

   - Jumlah item relevan yang direkomendasikan adalah produk relevan yang berhasil dimunculkan dalam rekomendasi Top-K.
   
   Cara Kerja:

   - Sistem merekomendasikan K item teratas.

   - Recall dihitung dengan membandingkan berapa banyak dari item relevan yang berhasil muncul di dalam rekomendasi tersebut dibandingkan total item relevan yang 
     sebenarnya ada.

   - Recall tinggi berarti sistem tidak melewatkan banyak item relevan, sehingga pengguna mendapat rekomendasi yang lebih lengkap.

### Hasil Evaluasi
Dengan input Shoes, Zara, Men's Fashion, White, S sebagai testnya.

1. Cosine Similarty
   | Product ID | Product Name | Brand | Category      | Color | Size | Rating | Price | Similarity Score |
   | ---------- | ------------ | ----- | ------------- | ----- | ---- | ------ | ----- | ---------------- |
   | 4          | Shoes        | Zara  | Men's Fashion | White | S    | 1.0495 | 23    | 1.0              |
   | 236        | Shoes        | Zara  | Men's Fashion | White | S    | 1.7183 | 44    | 1.0              |
   | 668        | Shoes        | Zara  | Men's Fashion | White | S    | 1.8423 | 11    | 1.0              |
   | 714        | Shoes        | Zara  | Men's Fashion | White | S    | 2.4915 | 35    | 1.0              |
   | 93         | Shoes        | Nike  | Men's Fashion | White | S    | 4.9281 | 70    | 0.8              |

   - Precision@5: 0.80
   - Recall@5: 1.00
   - Total Item Relevan: 4

2. Ecludean Distances
   | Product ID | Product Name | Brand  | Category        | Color  | Size | Rating | Price | Similarity Score |
   | ---------- | ------------ | ------ | --------------- | ------ | ---- | ------ | ----- | ---------------- |
   | 3          | Dress        | Adidas | Women's Fashion | Yellow | XL   | 3.3379 | 44    | 1.0              |
   | 214        | Dress        | Adidas | Women's Fashion | Yellow | XL   | 1.7939 | 98    | 1.0              |
   | 386        | Dress        | Adidas | Women's Fashion | Yellow | XL   | 3.5784 | 17    | 1.0              |
   | 51         | Jeans        | Adidas | Women's Fashion | Yellow | XL   | 3.8430 | 67    | 0.414            |
   | 157        | Dress        | Adidas | Women's Fashion | Yellow | S    | 3.9818 | 67    | 0.414            |

   - Precision@5: 0.60
   - Recall@5: 1.00
   - Total Item Relevan: 3
   
### Interpretasi Hasil Evaluasi
- Pada test case ini, kedua metode Cosine Similarity dan Euclidean Distance menghasilkan nilai Precision@5 dan Recall@5 yang sama, yaitu precision 0.80 dan recall 1.00.

- Artinya, dari 5 produk yang direkomendasikan, 4 di antaranya relevan dengan preferensi pengguna (product name 'Shoes', brand 'Zara', kategori "Men's Fashion", warna 'White', dan ukuran 'S').

- Sistem berhasil merekomendasikan semua produk relevan yang tersedia (recall 1.00), sekaligus menjaga ketepatan rekomendasi cukup tinggi (precision 0.80).

- Perbedaan skor similarity pada item terakhir di Euclidean Distance menunjukkan ada perbedaan tingkat kemiripan, namun tidak mempengaruhi metrik precision dan recall dalam kasus ini.
