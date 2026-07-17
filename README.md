# UAS Kecerdasan Buatan

## Judul Proyek

**Klasifikasi Kualitas Air Layak Konsumsi Menggunakan Algoritma Decision Tree dan K-Nearest Neighbor**

## Identitas Kelompok

| Nama | Keterangan |
|---|---|
| Muhamad Rojaka | 2406027 |
| Yusrina Fauziyyah | 2406106 |

## Deskripsi Singkat Proyek

Proyek ini bertujuan untuk membangun model klasifikasi kualitas air berdasarkan kandungan kimia dan mikroorganisme. Dataset yang digunakan adalah `waterquality.csv` dengan target klasifikasi `is_safe`, yaitu apakah air termasuk aman (`1`) atau tidak aman (`0`).

Model machine learning yang digunakan adalah:

1. **Decision Tree Classifier**
2. **K-Nearest Neighbor (KNN)**

Kedua model dibandingkan menggunakan metrik evaluasi **accuracy**, **precision**, **recall**, **F1-score**, dan **confusion matrix**.

## Struktur Repository

```text
UAS-KecerdasanBuatan/
├── README.md
├── Laporan_uas.md
├── uas_model.ipynb
└── data/
    ├── waterquality.csv
    └── Jurnal/
        └── Daftar_Jurnal.md
```

## Dataset

Dataset berada pada folder:

```text
data/dataset/waterquality.csv
```

Dataset memiliki 21 kolom, yaitu 20 fitur input dan 1 target klasifikasi.

Target:

| Nilai | Keterangan |
|---|---|
| 0 | Air tidak aman |
| 1 | Air aman |

## Langkah Pengerjaan

1. Mengumpulkan dataset kualitas air.
2. Membaca dataset menggunakan Python dan Pandas.
3. Melakukan pengecekan struktur data, tipe data, data kosong, dan data bermasalah.
4. Membersihkan nilai error `#NUM!` pada kolom `ammonia` dan `is_safe`.
5. Mengubah seluruh kolom menjadi tipe numerik.
6. Menghapus data kosong dan data duplikat.
7. Melakukan Exploratory Data Analysis (EDA), seperti distribusi target, histogram fitur, dan korelasi antar fitur.
8. Memisahkan data menjadi fitur (`X`) dan target (`y`).
9. Membagi dataset menjadi data latih dan data uji menggunakan rasio 80:20.
10. Melatih model Decision Tree dan KNN.
11. Mengevaluasi model menggunakan confusion matrix, accuracy, precision, recall, dan F1-score.
12. Membandingkan hasil kedua model dan menentukan model terbaik.
13. Menulis kesimpulan dan rekomendasi pengembangan.

## Cara Menjalankan Proyek

### 1. Clone Repository

```bash
git clone https://github.com/username/UAS-KecerdasanBuatan.git
cd UAS-KecerdasanBuatan
```

### 2. Install Library

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Jalankan Notebook

```bash
jupyter notebook uas_model.ipynb
```

Lalu jalankan seluruh cell dari atas ke bawah.

## Ringkasan Hasil Model

Berdasarkan pengujian awal dengan pembagian data 80:20 dan `random_state=42`, hasil evaluasi model adalah sebagai berikut:

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Decision Tree | 0.9581 | 0.8212 | 0.8077 | 0.8144 |
| KNN | 0.9113 | 0.7326 | 0.3462 | 0.4701 |

Model terbaik pada pengujian ini adalah **Decision Tree**, karena memiliki nilai accuracy dan F1-score yang lebih tinggi dibandingkan KNN. Selain itu, Decision Tree lebih baik dalam mendeteksi kelas air aman (`1`) berdasarkan nilai recall.

## Catatan

Dataset memiliki ketidakseimbangan kelas. Jumlah data air tidak aman jauh lebih banyak dibandingkan data air aman. Oleh karena itu, evaluasi tidak hanya melihat accuracy, tetapi juga precision, recall, dan F1-score.
