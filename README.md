# Laporan Proyek Machine Learning - Aryo Daffa Khairuddin

## Project Overview

Banyak orang merasa kesulitan dalam menemukan produk yang sesuai dengan preferensi mereka ditengah banyaknya pilihan yang tersedia, sehingga dibutuhkan solusi yang dapat membantu menyederhanakan proses pencarian tersebut. Sistem rekomendasi menjadi salah satu solusinya karena mampu memberikan pengalaman belanja yang lebih personal, efisien, dan relevan. Dengan adanya sistem ini, pengguna dapat memperoleh saran produk yang sesuai tanpa harus menelusuri seluruh katalog secara manual, sehingga mempermudah dalam pencarian dan meningkatkan kepuasan pelanggan. Berdasarka penelitian oleh El-Demerdash et al. (2023) menjelaskan bahwa sistem rekomendasi dalam e-commerce fashion secara signifikan memengaruhi keputusan pembelian konsumen melalui pemanfaatan preferensi pribadi, tren terkini, serta data sosial pengguna.

Selain memanfaatkan riwayat interaksi pengguna, pendekatan modern dalam sistem rekomendasi juga mengintegrasikan analisis visual menggunakan teknologi kecerdasan buatan. Berdasarka penelitian oleh Chang et al. (2025) mengembangkan sistem rekomendasi berbasis Convolutional Neural Networks (CNN) yang mampu mengenali ciri visual dari produk fashion seperti warna, bentuk, dan gaya. Dengan pendekatan ini, rekomendasi menjadi lebih akurat bahkan ketika data interaksi pengguna masih terbatas. Oleh karena itu, pengembangan sistem rekomendasi berbasis AI menjadi strategi penting untuk meningkatkan daya saing dan retensi pengguna di sektor e-commerce fashion.

Refrensi:
- El-Demerdash, D., El-Sheikh, K., & Abou-Ghali, M. (2023). Fashion Recommendation System and its Impact on Consumers’ Purchase Decision Making. International Design Journal, 13(1), 195–206. [link](https://www.researchgate.net/publication/366780313_Fashion_Recommendation_System_and_its_Impact_on_Consumers'_Purchase_Decision_Making)
- Chang, C.-C., Wei, C.-H., Wang, Y.-H., Yang, C.-H. T., & Hsiao, S. (2025). Recommender System for Apparel Products Based on Image Recognition Using Convolutional Neural Networks. Engineering Proceedings, 89(1), 38. [link](https://www.mdpi.com/2673-4591/89/1/38)

## Business Understanding

### Problem Statements
- Bagaimana cara membantu pengguna menemukan produk fashion yang sesuai berdasarkan nama produk, kategori, brand, warna, dan ukuran?

- Bagaimana cara merekomendasikan produk yang relevan berdasarkan interaksi pengguna sebelumnya seperti rating?

### Goals
- Membangun sistem rekomendasi berdasarkan nama produk, kategori, brand, warna, dan ukuran yang serupa dengan atribut tersebut.

- Membangun sistem rekomendasi yang dapat memberikan produk sesuai dengan selera pengguna berdasarkan rating pengguna sebelumnya.

### Solution Approach
- Content-Based Filtering
  Sistem akan merekomendasikan produk berdasarkan kesamaan atribut seperti nama produk, kategori, brand, warna, dan ukuran. Misalnya, jika pengguna menyukai produk 
  "Dress, Men's Fashion, Adidas, Yellow, XL", sistem akan mencari produk serupa berdasarkan atribut yang sama. Proses ini menggunakan teknik cosine similarity 
  untuk mengukur kemiripan antar produk.

- Collaborative Filtering dengan Neural Collaborative Filtering (NCF)
  Sistem ini belajar dari rating pengguna untuk memprediksi produk yang mungkin disukai. Jika pengguna memberi rating tinggi pada produk seperti "T-shirt, Adidas", 
  sistem akan menyarankan produk serupa berdasarkan pola preferensi yang dipelajari menggunakan jaringan saraf, bahkan untuk produk yang belum dilihat pengguna 
  sebelumnya.
  
## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
