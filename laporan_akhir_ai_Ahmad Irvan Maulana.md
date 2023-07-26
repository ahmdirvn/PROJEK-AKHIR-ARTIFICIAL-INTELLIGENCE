# Laporan Akhir Kecerdasan Buatan - Kelompok 3

Anggota Kelompok :

1.  Ahmad Irvan Maulana – NIM. 3.34.21.0.03

2.  Dimas Rachman Maulana - NIM. 3.34.21.0.09

## Domain Proyek

Investor tertarik untuk berinvestasi dalam emas karena ada dua alasan utama yang meliputi perlindungan nilai investasi dan potensi keuntungan jangka Panjang \[1\]. Pertama, mereka melihat emas sebagai cara untuk melindungi nilai kekayaan mereka dari *fluktuasi* ekonomi dan inflasi yang dapat mengancam portofolio mereka. Emas dianggap sebagai aset *safe-haven* yang stabil dalam nilai \[2\], sehingga berfungsi sebagai perlindungan penting dalam situasi ketidakpastian pasar saham dan komoditas.Kedua, investor mencari potensi keuntungan jangka panjang dari investasi emas. Harga emas telah terbukti mengalami kenaikan nilai secara berkelanjutan dalam beberapa periode waktu tertentu, mencerminkan pertumbuhan nilai investasi yang menguntungkan. Potensi pertumbuhan ini didorong oleh permintaan yang terus meningkat dari berbagai sektor, termasuk industri perhiasan, teknologi, dan minat dari investor *institusional* dan individu.

Namun, berinvestasi dalam emas juga membawa risiko yang perlu dipertimbangkan secara matang. Harga emas dipengaruhi oleh berbagai faktor eksternal seperti perubahan kebijakan moneter, ketidakstabilan geopolitik, krisis ekonomi global, dan *fluktuasi* nilai tukar mata uang\[3\]. Risiko-risiko ini dapat menyebabkan harga emas berubah secara tajam dan sulit diprediksi.Oleh karena itu, peramalan atau *time series forecasting* menjadi pendekatan penting bagi para investor dalam mengelola risiko investasi emas dengan lebih baik. Dengan menggunakan analisis peramalan, investor dapat memahami pola dan tren harga emas berdasarkan data historis, sehingga dapat memprediksi pergerakan harga di masa depan.\[4\]

Peramalan, juga dikenal sebagai *forecasting* dalam bahasa Inggris, adalah suatu metode atau teknik untuk memprediksi atau mengestimasi keadaan di masa depan berdasarkan data dan informasi yang telah ada pada periode masa lalu \[5\]. Dalam konteks analisis keuangan dan investasi, peramalan sangat relevan dalam memprediksi pergerakan harga aset, termasuk harga emas, saham, mata uang, dan komoditas lainnya. Peramalan juga digunakan dalam berbagai bidang lain, seperti ekonomi, manajemen persediaan, pemasaran, dan perencanaan bisnis. Teknik peramalan melibatkan penggunaan berbagai model matematis atau statistik yang berdasarkan pada data *historis* dan pola yang teridentifikasi untuk membuat prediksi yang lebih akurat di masa depan.

## Business Understanding

Setiap tahun, harga emas mengalami fluktuasi yang dipengaruhi oleh berbagai faktor eksternal seperti perubahan dalam kebijakan moneter, ketidakstabilan geopolitik, krisis ekonomi global, dan perubahan nilai tukar mata uang. Dalam menghadapi tantangan ini, diperlukan penggunaan model machine learning yang dapat melakukan prediksi harga emas secara akurat dengan mempertimbangkan data historis dan faktor-faktor eksternal yang mempengaruhinya. Dengan adanya model peramalan yang andal, para investor dan pelaku pasar dapat membuat keputusan investasi yang lebih cerdas, sementara bagi calon konsumen emas, mereka dapat memahami tren pasar dan menentukan timing yang tepat untuk membeli atau menjual emas sesuai dengan kebutuhan dan tujuan mereka.

#### Problem Statements

Berdasarkan pada permasalahan di atas, *problem statements* dari proyek ini adalah sebagai berikut:

1.  Bagaimana melakukan analisis terhadap data harga Emas?

2.  Bagaimana melakukan preprocessing data agar sesuai dengan kebutuhan pelatihan model?

3.  Bagaimana membangun model yang efektif untuk melakukan time series forecasting dengan akurat?

#### Goals

Tujuan dari proyek yang kami kerjakan adalah sebagai berikut

1.  Melakukan analisis dan pengolahan data secara optimal agar sesuai dengan kebutuhan model machine learning.

2.  Menggunakan model machine learning untuk melakukan prediksi harga emas dengan tingkat akurasi yang tinggi.

3.  Membantu para investor dalam mengambil keputusan pembelian emas yang lebih cerdas dan terinformasi.

#### Solution Statements

Solusi dari problem statement yang akan dilakukan pada projek ini adalah sebagai berikut.

1.  Melakukan analisa deskriptif, eksplorasi, dan data preprocessing data dengan tujuan mendapatkan pemahaman yang lebih baik tentang data tersebut. Langkah-langkah yang dapat dilakukan mencakup:

- Mengatasi nilai yang hilang (missing value) pada data.

- Mencari hubungan korelasi antara variabel dependen dan variabel independen.

- Menangani data outlier dengan menggunakan metode IQR (Interquartile Range).

- Spliting / Pembagian data menjadi *data training* dan *test set*. Pembagian ini dilakukan dengan perbandingan 80% pada data training dan 20% pada data test. Kami menggunakan perbandingan ini karena data yang kami gunakan cukup banyak, jadi 20 % sudah cukup untuk data test.

- Mencari model yang tepat dan membangun model untuk memprediksi nilai kontinu, khususnya untuk memprediksi harga di masa depan.

2.  Algoritma yang akan kami gunakan yaitu:

- K-Nearest Neighbors

- Support Vector Machine (Support Vector Regression)

3.  Melakukan peningkatan akurasi dengan menggunakan *hyperparameter tunning* pada model yang dibuat agar lebih optimal. Peningkatan ini akan menggunakan salah satu Teknik pada *hyperparameter tunning* yaitu *Teknik Grid Search.*

## Data Understanding

Dalam proyek ini kami menggunakan dataset yang diperoleh dari Kaggle. Anda dapat mengakses dataset yang digunakan dengan mengunjungi tautan berikut: [Gold Prices](https://www.kaggle.com/datasets/kamyababedi/gold-prices). Dataset ini mencakup beberapa variabel sebagai berikut:

- Date: Variabel ini mencatat tanggal saat data harga emas dicatat.

- Open: Variabel ini mencatat harga pembukaan, yaitu harga pada saat emas mulai diperdagangkan pada hari tersebut.

- High: Variabel ini mencatat harga tertinggi yang dicapai oleh emas pada hari tersebut.

- Low: Variabel ini mencatat harga terendah yang dicapai oleh emas pada hari tersebut.

- Close: Variabel ini mencatat harga penutupan, yaitu harga pada saat emas berhenti diperdagangkan pada hari tersebut.

- Adj Close: Variabel ini mencatat harga penutupan pada hari tersebut dan telah disesuaikan dengan right issue,stock split,stock reverse.

- Volume: Variabel ini mencatat volume transaksi yang terjadi pada emas pada hari tersebut.

Dataset tersebut terdapat 6 fitur numerical dan 1 fitur kategorikal. Berikut adalah statistic dari data numerical :

| **index** | **Open**          | **High**           | **Low**            | **Close**         | **Adj Close**     | **Volume**         |
|-----------|-------------------|--------------------|--------------------|-------------------|-------------------|--------------------|
| **count** | 5227.0            | 5227.0             | 5227.0             | 5227.0            | 5227.0            | 5227.0             |
| **mean**  | 1030.794707208789 | 1036.018476895703  | 1025.1554103138672 | 1030.656113416211 | 1030.656113416211 | 4320.45234375      |
| **std**   | 479.7143849091615 | 482.60775431041264 | 476.4425467999651  | 479.5811338386414 | 479.5811338386414 | 24476.507055963164 |
| **min**   | 255.0             | 256.100006         | 255.0              | 255.100006        | 255.100006        | 0.0                |
| **25%**   | 570.299988        | 574.350006         | 568.0              | 570.899994        | 570.899994        | 20.0               |
| **50%**   | 1171.300049       | 1176.5             | 1165.0             | 1171.099976       | 1171.099976       | 101.0              |
| **75%**   | 1333.6499635      | 1341.0             | 1326.199951        | 1333.8500365      | 1333.8500365      | 403.5              |
| **max**   | 2045.5            | 2063.0             | 2040.0             | 2051.5            | 2051.5            | 386334.0           |

Pada tahapan ini, kami akan mengeksplorasi data guna mendapat pemahaman mengenai dataset, seperti struktur dan karakteristik data, serta mencari potensi dan meminimalisir potensi terjadinya masalah atau eror yang mungkin akan muncul. Sebelum memasuki tahapan data processing, kita perlu melewati beberapa proses diantaranya :

- Memberikan informasi terkait jumlah data, keberadaan nilai yang hilang (missing value), adanya data yang duplikat, korelasi antar kolom, serta distribusi data.
- Menangani data NaN dengan mengganti menggunakan nilai mean ,Menangani outlayer

![alt text](https://i.postimg.cc/kRmskWKh/image1.jpg)



- Melakukan Unvariate Analysis

  ![alt text](https://i.postimg.cc/mzNpZdLG/image2.jpg)

- Melakukan Multivariate Analysis.

Pada tahapan ini kami melakukan Multivariate Analysis yang di fokuskan pada Adj Close terhadap fitur lainya seperti open,high,low,close dan volume. Dan hasil dari tahapan ini yaitu Adj Close memiliki korelasi kuat dengan open high low dan close. Namun pada volume korelasinya hanya sedikit/sedang.

![](https://i.postimg.cc/14B7LY7G/image3.jpg)

Kami juga menggunakan visualisasi heatmap untuk membuat visualisasi korelasi lebih jelas. Dan hasil menunjukan hal yang sama yaitu semua fitur memiliki korelasi kuat kecuali fitur volume. Oleh karena itu kami memakai semua fitur sebagai variable dependen kecuali fitur volume.

 										![](https://i.postimg.cc/sGj6MpxG/image4.jpg)

## Data Preparation

Teknik data preparation yang dilakukan pada proyek ini adalah sebagai berikut :

1.  Penanganan Missing Value : Pada kasus ini dalam menangani Missing Value menggunakan metode penggantian nilai NaN menjadi nilai Mean setiap kolom

2.  Pembagian Dataset : Dataset akan dibagi menjadi dua bagian, yaitu train data dan test data. Train data akan digunakan untuk melatih model, sedangkan test data akan digunakan untuk memvalidasi sejauh mana model telah menghasilkan prediksi yang akurat. Ratio yang umum digunakan dalam pembagian dataset adalah 80:20, di mana 80% data menjadi train data dan 20% data menjadi test data. Oleh karena itu, kita akan mengikuti rasio tersebut. Pembagian dataset akan dilakukan menggunakan modul "train_test_split" dari pustaka scikit-learn. Setelah pembagian dataset dilakukan, jumlah sampel pada data latih akan menjadi 3600 sampel, sementara jumlah sampel pada data test akan menjadi 900 sampel, dari total jumlah sampel pada dataset sebanyak 4500 sampel.

3.  Removing unnecessary features : Karena fitur Date dan Volume tidak dibutuhkan, keduanya akan dihapus dari dataset. Selain itu, fitur Close juga tidak diperlukan karena Adj Close lebih akurat, sehingga fitur Close juga akan dihapus dari dataset.

4.  Data Normalization : Normalisasi data dilakukan dengan tujuan agar model dapat beroperasi secara lebih optimal tanpa harus memproses data dengan skala yang besar. Normalisasi mengubah data ke dalam rentang tertentu. Pada proyek ini, kami akan menggunakan MinMaxScaler untuk melakukan normalisasi data, sehingga data akan dinormalisasi dalam rentang 0 hingga 1.

## Modelling

Tahapan modelling adalah tahapan dimana dilakukanya proses untuk melatih data sehingga dihasilkan model yang akurat atau memiliki performa yang baik. Seperti yang telah disebutkan sebelumnya bahwa pada proyek ini kami menggunakan 2 model yaitu Support Vector Regression dan K- Nearest Neighbors, berikut merupakan alasan kami memilih 2 model tersebut :

**Support Vector Regression**

SVR sebenarnya memiliki konsepan yang hamper sama dengan SVM, namun SVM lebih sering digunakan dalam proyek klasifikasi. SVR akan berusaha mencari solusi / jalan yang dapat menampung sebanyak banyaknya sample dalam jarak tertentu, sedangkan SVM bekerja dengan berusaha mencari margin terbesar. Alasan utama dalam menggunakan model ini yaitu sesuai yang diajarkan oleh dosen kami.

Dalam model SVR, terdapat beberapa hyperparameter yang digunakan:

- Kernel: Hyperparameter ini digunakan untuk menghitung matriks kernel sebelumnya, yang memungkinkan transformasi data ke dalam ruang fitur yang lebih tinggi.

- C: Hyperparameter ini adalah parameter regularisasi yang bertujuan untuk menyeimbangkan antara kesalahan prediksi pada contoh pelatihan dan upaya memaksimalkan margin fungsi keputusan.

- Gamma: Nilai rendah menandakan pengaruh yang lebih jauh, sementara nilai tinggi menandakan pengaruh yang lebih dekat.

Kelebihan :

- Lebih efektif dalam menangani data dengan dimensi yang tinggi, yaitu data yang memiliki banyak fitur.

- Lebih efisien dalam penggunaan memori karena hanya menggunakan subset dari titik-titik pelatihan.

kekurangan:

- Sulit untuk diaplikasikan pada data skala besar karena waktu eksekusi yang lama dan kebutuhan memori yang tinggi.

**K-Nearest Neighbors**

K-Nearest Neighbors (KNN) adalah algoritma yang bekerja dengan mengklasifikasi data yang baru dan didasarkan pada kemiripan data dengan sejumlah data (k) yang sudah ada pada dataset. Alasan utama dalam menggunakan model ini yaitu sesuai yang diajarkan oleh dosen kami.

- n_neighbors: Jumlah tetangga yang diperlukan untuk menentukan posisi atau klasifikasi data baru.

Kelebihan :

- Dapat menangani data yang masih mengandung noise (data yang tidak sempurna atau mengalami gangguan).

- Sangat efektif ketika jumlah data dalam dataset sangat besar.

- Mudah diimplementasikan dan dipahami.

Kekurangan :

- Rentan terhadap pengaruh outlier (data yang jauh berbeda dengan mayoritas data lainnya).

- Rentan terhadap fitur-fitur yang kurang informatif, yang dapat menyebabkan hasil klasifikasi yang kurang akurat.

##  Evaluation

- Metrik evaluasi yang digunakan untuk model machine learning ini adalah mean squared error (mse), yang berfungsi untuk mengukur seberapa akurat garis regresi dalam memetakan titik-titik data.

> ![](https://i.postimg.cc/2LrdHrNs/image5.png)

- dimana : n = jumlah titik data Yi = nilai sesungguhnya Yi_hat = nilai prediksi Menampilkan hasil akurasi dari beberapa model yang dipakai :

> ![](https://i.postimg.cc/BPpTkkqX/image6.jpg)
>
> ![](https://i.postimg.cc/CBjHHdXC/image7.jpg)
>
> Pada proyek kali ini model yang berjalan lebih optimal yaitu K-Nearest Neighbors. Namun selesih antara SVR dengan K – Nearest Neighbors sangatlah kecil . Tetapi pada perhitungan akurasi model hasil tertinggi yaitu K-Nearest Neighbors yang memiliki nilai lebih tinggi.

## Conclussion 

1.  Untuk menganalisis data harga emas dengan tujuan pemahaman terhadap dataset dapat dilakukan dengan memahami maksud dari kolom kolom pada dataset,pada praktikum ini yaitu Date: Variabel ini mencatat tanggal saat data harga emas dicatat.Open: Variabel ini mencatat harga pembukaan, yaitu harga pada saat emas mulai diperdagangkan pada hari tersebut.High: Variabel ini mencatat harga tertinggi yang dicapai oleh emas pada hari tersebut.Low: Variabel ini mencatat harga terendah yang dicapai oleh emas pada hari tersebut.Close: Variabel ini mencatat harga penutupan, yaitu harga pada saat emas berhenti diperdagangkan pada hari tersebut.

Adj Close: Variabel ini mencatat harga penutupan pada hari tersebut dan telah disesuaikan dengan right issue,stock split,stock reverse.Volume: Variabel ini mencatat volume transaksi yang terjadi pada emas pada hari tersebut. Lalu juga dapat dengan cara menjalankan fungsi df.describe () untuk mengetahui statistic dataset.

2.  Selain itu kita juga dapat melakukan analisis terhadap data dengan mencari tau kolom kolom yang memiliki korelasi terhadap Adj Close

3.  Tahapan sebelum proses / preprocessing yang kami lakukan adalah dengan melakukan manipulasi data seperti mengatasi missing value dengan nilai mean, menghapus data yang tidak memiliki korelasi yang signifikan dengan *Adj Close*, dan menangani data outlier dengan menggunakan metode IQR (Interquartile Range).

4.  Berdasarkan hasil pengujian 2 model, yaitu K-Nearest Neigbors dan SVR diperoleh hasil bahwa algoritma K- Nearest Neighbors memiliki performa yang paling baik yaitu akurasi lebih tinggi dibandingkan algortima SVR.

5.  Menggunakan hyperparameter tunning dengan Teknik grid search untuk mendapatkan akurasi tinggi / performa terbaik model.

## Referensi

\[1\] Christanti, N., & Mahastanti, L. A. (2011). Faktor-Faktor yang Dipertimbangkan Investor dalam Melakukan Investasi. Jurnal Manajemen Teori dan Terapan, 4(3), 37. [E journal.unair.ac.id](https://www.bing.com/ck/a?!&&p=5ea261b6a7857b6bJmltdHM9MTY4OTcyNDgwMCZpZ3VpZD0xODNmMjc2Ny0yNzE1LTZmOTEtMWM0Yy0zNTZhMjY0MzZlOWUmaW5zaWQ9NTIwMA&ptn=3&hsh=3&fclid=183f2767-2715-6f91-1c4c-356a26436e9e&psq=Investor+tertarik+untuk+berinvestasi+dalam+emas+karena+ada+dua+alasan+utama+yang+meliputi+perlindungan+nilai+investasi+dan+potensi+keuntungan+jangka+panjang+article&u=a1aHR0cHM6Ly9lLWpvdXJuYWwudW5haXIuYWMuaWQvSk1UVC9hcnRpY2xlL2Rvd25sb2FkLzI0MjQvMTc3OQ&ntb=1)

\[2\] Muchamad Nafi. (2023, 20 Juli). Penyebab Harga Emas Naik dan Turun. [Katadata.co.id. https://katadata.co.id/muchamadnafi/ekonopedia/61a5e157aa929/penyebab-harga-emas-naik-dan-turun](Katadata.co.id.%20https:/katadata.co.id/muchamadnafi/ekonopedia/61a5e157aa929/penyebab-harga-emas-naik-dan-turun)

\[3\] Shafiee, S., & Topal, E. (2010). An overview of global gold market and gold price forecasting. Resources policy, 35(3), 178-189.

\[4\] Aulia, A., Aprianti, B., Supriyanto, Y., & Rozikin, C. (2022). Prediksi Harga Emas dengan Menggunakan Algoritma Support Vector Regression (Svr) dan Linear Regression (LR). Jurnal Ilmiah Wahana Pendidikan, 8(5), 84-88. <https://doi.org/10.5281/zenodo.6408864>

\[5\] Petropoulos, F., Apiletti, D., Assimakopoulos, V., Babai, M. Z., Barrow, D. K., Taieb, S. B., ... & Ziel, F. (2022). Forecasting: theory and practice. International Journal of Forecasting, 38(3), 705-871. <https://doi.org/10.1016/j.ijforecast.2021.11.001>

\[6\] Andriani, W., Gunawan, G., & Prayoga, A. E. (2023). PREDIKSI NILAI EMAS MENGGUNAKAN ALGORITMA REGRESI LINEAR. Jurnal Ilmiah Informatika Komputer, 28(1), 27-35.

---Ini adalah bagian akhir laporan---
