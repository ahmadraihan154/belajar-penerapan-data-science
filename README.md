# Nama : Ahmad Raihan
# Modul : Belajar Penerapan Data Science
# Submission Pertama: Menyelesaikan Permasalahan Human Resources 

## Struktur Direktori
Adapun struktur direktori yang digunakan pada submission ini adalah:
  1. model – Berisi file model yang telah dilatih untuk memprediksi potensi attrition pada karyawan.
  2. notebook – Berisi notebook (Jupyter Notebook) yang memuat seluruh proses analisis dan pemodelan.
  3. prediction – Berisi skrip yang digunakan untuk melakukan prediksi terhadap data baru.
  4. README – File markdown yang menjelaskan deskripsi proyek, alur pengerjaan, hingga kesimpulan akhir.
  5. raihan-dashboard – Berisi dokumentasi berupa kumpulan screenshot dashboard yang telah dibuat.
  6. raihan-video – Berisi video penjelasan terkait dashboard serta rekomendasi bisnis yang diberikan.
  7. metabase.db.mv.db – File database Metabase yang menyimpan konfigurasi dashboard interaktif yang telah dikembangkan.
  8. requirements.txt – Berisi daftar pustaka dan dependensi yang dibutuhkan untuk menjalankan proyek.

## 1. Business Understanding
![attrition-rate](https://github.com/user-attachments/assets/8ed89705-2428-4ad6-81ed-7e77bc3b14aa)
### 1.1 Latar Belakang
Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Ia memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri. 
Walaupun telah menjadi menjadi perusahaan yang cukup besar, Jaya Jaya Maju masih cukup kesulitan dalam mengelola karyawan. Hal ini berimbas tingginya attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan) hingga lebih dari 10%.
Untuk mencegah hal ini semakin parah, manajer departemen HR ingin meminta bantuan Anda mengidentifikasi berbagai faktor yang mempengaruhi tingginya attrition rate tersebut. Selain itu, ia juga meminta Anda untuk membuat business dashboard untuk membantunya memonitori berbagai faktor tersebut.

### 1.1 Problem Statements
Berdasarkan latar belakang yang telah dijelaskan, berikut adalah tiga permasalahan utama yang ingin dijawab dalam proyek ini:

1. Apa faktor-faktor yang menyebabkan karyawan keluar dari perusahaan?  
2. Bagaimana membangun model prediktif untuk mengidentifikasi karyawan yang berpotensi keluar?  
3. Bagaimana cara menyajikan hasil analisis dan prediksi tersebut dalam bentuk dashboard yang informatif?

### 1.2 Goals
Proyek ini memiliki goals sebagai berikut:
1. Mengidentifikasi faktor-faktor utama yang memengaruhi keputusan karyawan untuk keluar dari perusahaan.
2. Membangun model prediktif berbasis machine learning untuk memprediksi karyawan yang berpotensi keluar.
3. Menyediakan business dashboard yang dapat membantu tim HR dalam memantau kondisi tenaga kerja dan mengambil tindakan preventif secara lebih terukur.

### 1.3 Solution Statements
- Berikut merupakan tahapan-tahapan yang dilakukan dalam menyelesaikan proyek ini:

  1. **Exploratory Data Analysis (EDA)**: Melakukan eksplorasi dan pemahaman mendalam terhadap data melalui visualisasi dan analisis statistik untuk mengidentifikasi pola serta fitur-fitur yang mungkin berkaitan erat dengan attrition karyawan.

  2. **Data Preprocessing**: Melakukan serangkaian proses pembersihan dan transformasi data, termasuk perhitungan korelasi antar fitur, encoding variabel kategorikal, penyeimbangan data menggunakan teknik SMOTE, serta seleksi fitur untuk meningkatkan performa model.

  3. **Modeling dan Evaluasi**: Menerapkan berbagai algoritma machine learning seperti Decision Tree, Random Forest, dan Gradient Boosting untuk membangun model prediktif. Evaluasi dilakukan menggunakan metrik seperti Accuracy, Precision, Recall, dan F1-Score guna menentukan model dengan kinerja terbaik.

  4. **Prediksi**: Menggunakan model terbaik yang telah terpilih untuk melakukan prediksi terhadap kemungkinan seorang karyawan akan keluar, dengan tujuan mendukung pengambilan keputusan yang proaktif oleh tim HR.

  5. **Pembuatan Dashboard Interaktif**: Membangun dashboard yang informatif dan mudah dipahami sebagai media visualisasi hasil analisis dan prediksi, sehingga dapat digunakan sebagai alat bantu strategis oleh manajemen dan tim HRD.

## 2. Data Preparation
### 2.1 **Dataset**
Dataset yang digunakan dalam proyek ini adalah **[Dataset Karyawan Jaya Jaya Maju](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)**, yang disediakan sesuai dengan instruksi pada submission proyek ini.

## 3. Tahapan Pengerjaan
### 3.1 Membuka notebook.ipynb
- Pastikan seluruh **dependensi** telah terinstal sesuai dengan daftar pada **`requirements.txt`**.
- Jalankan seluruh isi **notebook.ipynb** di **Google Colab** atau IDE sejenis untuk melihat hasil dari **analisis data**, temuan, dan **insight** yang diperoleh.

### 2. Menjalankan prediction.py
- Pastikan seluruh **dependensi** telah terinstal sesuai dengan daftar pada **`requirements.txt`**.
- File `prediction.py` dapat dijalankan secara langsung menggunakan **VSCode** atau IDE lokal lain yang mendukung Python.

- Script ini memuat:
  - **Fungsi preprocessing sederhana** (`simple_preprocessing`) untuk menyesuaikan data input dengan fitur yang digunakan model.
  - **Model yang telah dilatih** (`model.joblib`) yang dimuat menggunakan `joblib`.
  - **Data baru** yang dibuat secara acak untuk simulasi prediksi.
  - **Prediksi** terhadap data tersebut untuk menentukan apakah karyawan akan keluar (`Attrition: Yes/No`).

- Untuk menjalankan prediksi:
  1. Pastikan file `model.joblib` berada dalam direktori yang sama.
  2. Jalankan file `prediction.py` di VSCode.
  3. Hasil prediksi akan ditampilkan langsung di terminal/console dan juga ditambahkan ke data yang telah dibuat.

#### **3. Menjalankan Dashboard**
Untuk mengakses **dashboard** secara lokal, Anda dapat menjalankan **Metabase** menggunakan **Docker**. Pastikan aplikasi **Docker** sudah terinstal di perangkat Anda.

**Langkah-langkah untuk menjalankan Metabase menggunakan Docker**:
1. **pull image Metabase dari Docker Hub** dengan perintah:
   ```bash
   docker pull metabase/metabase:latest
   ```

2. **Jalankan container Metabase** dengan perintah:
   ```bash
   docker run -p 3000:3000 --name metabase metabase/metabase
   ```

3. **Login ke Metabase dengan url : http://localhost:3000/setup** menggunakan kredensial berikut:
   - **Username**: `root@mail.com`
   - **Password**: `root123`

## 4. Hasil 
###  4.1 Faktor Penyebab Attrition 
- Berdasarkan hasil **analisis EDA** dan modeling menggunakan **Random Forest**, berikut adalah 10 fitur yang paling berpengaruh terhadap keputusan karyawan untuk keluar dari perusahaan:

1. **OverTime (Yes)**
   - **OverTime** menunjukkan pengaruh paling besar terhadap **attrition** dengan skor **importance** **0.207373**.
   - Karyawan yang bekerja lembur memiliki kecenderungan untuk keluar lebih tinggi, kemungkinan karena **beban kerja** yang berlebihan mengarah pada kelelahan dan stres.
   - **Analisis EDA** menguatkan temuan ini, di mana karyawan yang bekerja lembur memiliki tingkat **attrition** yang sangat tinggi dibandingkan yang tidak.

2. **MonthlyIncome**
   - Dengan skor **importance** **0.118629**, **MonthlyIncome** menjadi faktor penting dalam menentukan keputusan karyawan untuk keluar.
   - Karyawan dengan pendapatan yang lebih rendah mungkin merasa kurang dihargai dan mencari peluang pekerjaan yang lebih menguntungkan.
   - **Analisis EDA** juga menunjukkan bahwa karyawan dengan gaji rendah lebih cenderung mengundurkan diri, yang sejalan dengan temuan model.

3. **StockOptionLevel**
   - **StockOptionLevel** memiliki skor **importance** **0.109691**, yang mengindikasikan pengaruh besar pada keputusan karyawan untuk bertahan.
   - Karyawan tanpa insentif saham (**StockOptionLevel = 0**) lebih cenderung mengundurkan diri, karena mereka tidak merasa memiliki insentif untuk tetap bertahan.
   - **Analisis EDA** mengonfirmasi bahwa karyawan yang tidak memiliki opsi saham lebih sering mengundurkan diri, mendukung hasil model.

4. **Age**
   - **Age** memberikan skor **importance** sebesar **0.101372**.
   - Karyawan yang lebih muda sering berpindah pekerjaan untuk mengeksplorasi kesempatan karir baru, sementara karyawan yang lebih tua cenderung lebih stabil dan terikat.
   - **Analisis EDA** menunjukkan bahwa karyawan yang lebih muda memiliki tingkat **attrition** yang lebih tinggi, sejalan dengan hasil model.

5. **JobLevel**
   - Dengan skor **importance** **0.096370**, **JobLevel** juga berpengaruh terhadap keputusan karyawan untuk keluar.
   - Karyawan di **level 1** (entry-level) memiliki kecenderungan lebih tinggi untuk keluar, karena mereka mungkin mencari peluang untuk berkembang secara profesional.
   - **Analisis EDA** memperlihatkan bahwa karyawan di level entry lebih sering keluar dibandingkan karyawan di level yang lebih tinggi.

6. **TotalWorkingYears**
   - **TotalWorkingYears** memiliki skor **importance** **0.095571**.
   - Karyawan dengan pengalaman kerja yang lebih sedikit lebih mudah berpindah pekerjaan, karena mereka mungkin belum merasa terlalu terikat pada perusahaan.
   - **Analisis EDA** juga menunjukkan bahwa karyawan dengan pengalaman kerja lebih sedikit lebih sering mengundurkan diri, yang mendukung hasil model.

7. **YearsAtCompany**
   - Skor **importance** untuk **YearsAtCompany** adalah **0.081127**.
   - Karyawan yang telah lama bekerja di perusahaan mungkin merasa lebih loyal, namun jika mereka tidak melihat peluang berkembang, mereka lebih cenderung untuk keluar.
   - **Analisis EDA** menunjukkan bahwa karyawan yang lebih lama di perusahaan memiliki tingkat **attrition** yang lebih rendah, mendukung temuan model.

8. **YearsWithCurrManager**
   - **YearsWithCurrManager** memiliki skor **importance** **0.079371**.
   - Karyawan yang memiliki hubungan lebih pendek dengan manajer mereka lebih sering keluar, mungkin karena kurangnya dukungan atau ketidakcocokan dalam kepemimpinan.
   - **Analisis EDA** mengungkapkan bahwa karyawan dengan hubungan manajer yang lebih singkat cenderung lebih tinggi tingkat **attrition**-nya.

9. **YearsInCurrentRole**
   - **YearsInCurrentRole** memiliki skor **importance** **0.067539**.
   - Karyawan yang lama berada dalam peran yang sama tanpa tantangan baru mungkin merasa stagnan dan mencari pekerjaan baru yang menawarkan peluang berkembang.
   - **Analisis EDA** menunjukkan bahwa karyawan yang lebih lama dalam posisi yang sama memiliki kecenderungan lebih tinggi untuk keluar, yang konsisten dengan hasil model.

10. **MaritalStatus (Single)**
    - **MaritalStatus (Single)** memiliki skor **importance** **0.042957**.
    - Karyawan yang belum menikah lebih cenderung berpindah pekerjaan karena mereka tidak memiliki komitmen keluarga yang mengikat mereka untuk tetap di satu tempat.
    - **Analisis EDA** mendukung temuan ini, di mana karyawan yang berstatus single memiliki tingkat **attrition** yang lebih tinggi.

### 4.2 Model Prediktif
- Berdasarkan hasil evaluasi menggunakan metrik accuracy, precision, recall, f1-score, serta analisis melalui confusion matrix, dapat disimpulkan bahwa **model Random Forest memiliki performa terbaik di antara model Decision Tree dan Gradient Boosting untuk dataset yang tidak seimbang**.

- Hal ini ditunjukkan oleh nilai evaluasi berikut:
  - Accuracy: 84.91%
  - Precision: 64.00%
  - Recall: 41.03%
  - F1-Score: 50.00%

| Model               | Accuracy | Precision | Recall  | F1 Score |
|---------------------|----------|-----------|---------|----------|
| Decision Tree       | 0.7453   | 0.3256    | 0.359   | 0.3415   |
| Random Forest       | 0.8491   | 0.6400    | 0.410   | 0.5000   |
| Gradient Boosting   | 0.8160   | 0.5000    | 0.359   | 0.4179   |

### 4.3 Rekomendasi Action
- Adapun beberapa rekomendasi yang dapat diberikan agar dapat mengurangi potensi attrition pada karyawan adalah sebagai berikut:
1. Mengatur Beban Kerja karyawan
  - Karyawan yang sering lembur atau merasa terjebak di posisi yang sama cenderung lebih cepat keluar. Sebaiknya, pastikan karyawan tidak bekerja secara berlebihan. Selain itu, berikan kesempatan buat mereka yang di level entry untuk naik jabatan atau mencoba posisi baru agar mereka merasa berkembang.

2. Meninjau Penghasilan dan Insentif
  - Karyawan dengan gaji rendah dan tanpa insentif saham lebih cenderung mencari peluang lain di perusahaan yang berbeda. Pastikan gaji mereka sesuai dengan kontribusinya, dan jangan lupa pertimbangkan untuk memberikan insentif kepada mereka. Ini bisa membuat mereka merasa lebih dihargai dan betah terhadap perusahaannya lebih lama.

3. Petimbangkan Peluang Pengembangan Karir
  - Karyawan yang merasa nggak ada kesempatan berkembang di perusahaan lebih cenderung keluar. Jadi, penting untuk memberi mereka jalur karir yang jelas dan peluang buat belajar hal baru.

4. Berikan Manfaat yang Sesuai dengan Demografi Karyawan
  - Karyawan muda dan single cenderung lebih mudah berpindah kerja karena belum banyak tanggungan dan terbuka terhadap peluang pekerjaan lain yang menurut mereka lebih menarik dari pada perusahaan ini berikan. Untuk menekan potensi attrition dari kelompok ini, perusahaan bisa menawarkan fleksibilitas kerja seperti opsi remote, kesempatan pengembangan diri, serta reward yang relevan seperti voucher, tiket hiburan, dsb. Pendekatan ini lebih sesuai dengan gaya hidup mereka dan dapat meningkatkan retensi.

### 5. Kesimpulan
- Dengan memahami faktor-faktor utama yang mempengaruhi **attrition** karyawan dan menggunakan **model prediktif** yang efektif, perusahaan dapat **mengambil langkah-langkah proaktif** untuk mempertahankan karyawan dan mengurangi tingkat attrition. Rekomendasi ini, jika diterapkan dengan tepat, dapat membantu meningkatkan **kepuasan karyawan** dan mengurangi biaya perekrutan ulang.
