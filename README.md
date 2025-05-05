
# Klasifikasi Gambar untuk Dataset Sayuran

Proyek ini melakukan klasifikasi gambar pada dataset sayuran yang terdiri dari 15 kelas berbeda. Gambar yang digunakan merupakan gambar sayuran, dan tujuan dari proyek ini adalah untuk mengklasifikasikan gambar tersebut ke dalam kelas yang sesuai menggunakan jaringan saraf konvolusional (CNN). Dataset ini terdiri dari 15.000 gambar, yang dibagi menjadi tiga bagian: pelatihan (training), validasi (validation), dan pengujian (testing).

## Dataset

- **Total Gambar:** 15.000 gambar
- **Ukuran Gambar:** 224x224 piksel (RGB)
- **Jumlah Kelas:** 15 kategori sayuran, antara lain:
  1. Bean (Kacang)
  2. Bitter Gourd (Pare)
  3. Bottle Gourd (Labu Botol)
  4. Brinjal (Terong)
  5. Broccoli (Brokoli)
  6. Cabbage (Kol)
  7. Capsicum (Paprika)
  8. Carrot (Wortel)
  9. Cauliflower (Kembang Kol)
  10. Cucumber (Mentimun)
  11. Papaya (Pepaya)
  12. Potato (Kentang)
  13. Pumpkin (Labuh)
  14. Radish (Lobak)
  15. Tomato (Tomat)

## Arsitektur Model

Model ini menggunakan arsitektur Jaringan Saraf Konvolusional (CNN) dengan lapisan-lapisan sebagai berikut:

| Layer (type)                     | Output Shape           | Param #       |
|-----------------------------------|------------------------|---------------|
| `conv2d` (Conv2D)                | (None, 222, 222, 20)   | 560           |
| `conv2d_1` (Conv2D)              | (None, 220, 220, 20)   | 3,620         |
| `max_pooling2d` (MaxPooling2D)   | (None, 110, 110, 20)   | 0             |
| `conv2d_2` (Conv2D)              | (None, 108, 108, 50)   | 9,050         |
| `conv2d_3` (Conv2D)              | (None, 106, 106, 50)   | 22,550        |
| `max_pooling2d_1` (MaxPooling2D) | (None, 53, 53, 50)     | 0             |
| `flatten` (Flatten)              | (None, 140450)         | 0             |
| `dropout` (Dropout)              | (None, 140450)         | 0             |
| `dense` (Dense)                  | (None, 15)             | 2,106,765     |

## Kinerja Model

Model ini mencapai hasil berikut pada dataset pengujian:

| Kelas             | Precision | Recall | F1-score | Support |
|-------------------|-----------|--------|----------|---------|
| Bean              | 0.95      | 0.95   | 0.95     | 200     |
| Bitter Gourd      | 0.94      | 0.94   | 0.94     | 200     |
| Bottle Gourd      | 0.94      | 0.96   | 0.95     | 200     |
| Brinjal           | 0.92      | 0.92   | 0.92     | 200     |
| Broccoli          | 0.87      | 0.97   | 0.92     | 200     |
| Cabbage           | 0.94      | 0.95   | 0.95     | 200     |
| Capsicum          | 0.98      | 0.98   | 0.98     | 200     |
| Carrot            | 1.00      | 0.98   | 0.99     | 200     |
| Cauliflower       | 0.93      | 0.94   | 0.94     | 200     |
| Cucumber          | 0.97      | 0.85   | 0.91     | 200     |
| Papaya            | 0.92      | 0.95   | 0.94     | 200     |
| Potato            | 0.99      | 0.94   | 0.97     | 200     |
| Pumpkin           | 0.92      | 0.92   | 0.92     | 200     |
| Radish            | 0.99      | 1.00   | 0.99     | 200     |
| Tomato            | 0.98      | 0.93   | 0.95     | 200     |

**Akurasi Total:** 0.95 (95%)

**Rata-rata Makro:** 0.95 (Precision), 0.95 (Recall), 0.95 (F1-score)

**Rata-rata Terbobot:** 0.95 (Precision), 0.95 (Recall), 0.95 (F1-score)

## Konversi Model

Model yang sudah dilatih telah dikonversi ke dalam format berikut:

- **TensorFlow Lite (TFLite)**
- **TensorFlow.js (TFJS)**
- **SavedModel**

Format-format ini memungkinkan model untuk di-deploy pada berbagai platform, termasuk perangkat mobile dan aplikasi web.

## Persyaratan

Pastikan untuk menginstal dependensi yang diperlukan untuk menjalankan model dengan menggunakan file `requirements.txt` yang sudah disediakan.

```bash
pip install -r requirements.txt
```

## Cara Menjalankan

1. Clone repositori ini ke mesin lokal Anda.
2. Instal dependensi menggunakan file requirements.txt:

```bash
pip install -r requirements.txt
```

3. Tempatkan gambar Anda dalam format yang benar (224x224 RGB) untuk klasifikasi.
4. Jalankan skrip untuk pelatihan, validasi, atau pengujian sesuai kebutuhan.
5. Gunakan model yang sudah dikonversi untuk inferensi pada platform mobile atau web.

## Pengakuan

Proyek ini dibangun menggunakan TensorFlow dan Keras. Terima kasih kepada semua kontributor dan pustaka open-source yang digunakan dalam proyek ini.
