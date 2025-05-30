# Laporan Proyek Machine Learning - Aryo Daffa Khairuddin

## Project Overview

Banyak orang sering kesulitan dalam menemukan fashion yang sesuai dengan preferensi mereka dengan banyaknya pilihan yang tersedia. Sistem rekomendasi menjadi salah satu solusinya karena dapat memberikan pengalaman belanja yang lebih personal, efisien, dan relevan. Dengan adanya sistem ini, pengguna dapat memperoleh saran produk yang sesuai tanpa harus menelusuri seluruh katalog secara manual, sehingga mempermudah dalam pencarian dan meningkatkan kepuasan pelanggan. Berdasarka penelitian oleh El-Demerdash et al. (2023) menjelaskan bahwa sistem rekomendasi dalam e-commerce fashion secara signifikan memengaruhi keputusan pembelian konsumen melalui pemanfaatan preferensi pribadi, tren terkini, serta data sosial pengguna.

Selain memanfaatkan riwayat interaksi pengguna, pendekatan modern dalam sistem rekomendasi juga mengintegrasikan analisis visual menggunakan teknologi kecerdasan buatan. Berdasarka penelitian oleh Chang et al. (2025) mengembangkan sistem rekomendasi berbasis Convolutional Neural Networks (CNN) yang mampu mengenali ciri visual dari produk fashion seperti warna, bentuk, dan gaya. Dengan pendekatan ini, rekomendasi menjadi lebih akurat bahkan ketika data interaksi pengguna masih terbatas. Oleh karena itu, pengembangan sistem rekomendasi berbasis AI menjadi strategi penting untuk meningkatkan daya saing dan retensi pengguna di sektor e-commerce fashion.

Refrensi:
- El-Demerdash, D., El-Sheikh, K., & Abou-Ghali, M. (2023). Fashion Recommendation System and its Impact on Consumers’ Purchase Decision Making. International Design Journal, 13(1), 195–206. [link](https://www.researchgate.net/publication/366780313_Fashion_Recommendation_System_and_its_Impact_on_Consumers'_Purchase_Decision_Making)
- Chang, C.-C., Wei, C.-H., Wang, Y.-H., Yang, C.-H. T., & Hsiao, S. (2025). Recommender System for Apparel Products Based on Image Recognition Using Convolutional Neural Networks. Engineering Proceedings, 89(1), 38. [link](https://www.mdpi.com/2673-4591/89/1/38)

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

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
