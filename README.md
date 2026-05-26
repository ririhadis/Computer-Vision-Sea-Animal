# Computer Vision for Sea Animal 🌊🐠

Proyek ini berfokus pada klasifikasi citra makhluk hidup bawah laut menggunakan pendekatan *Deep Learning*. Eksperimen ini membandingkan arsitektur *Convolutional Neural Network* (CNN) buatan sendiri (*custom model*) dengan metode *Transfer Learning* menggunakan model yang sudah terlatih (*pre-trained models*) untuk menemukan akurasi terbaik.

## 📸 Pengolahan Dataset & Augmentasi Data

Dataset yang digunakan terdiri dari foto-foto binatang laut yang diambil langsung dari lingkungan bawah air. Untuk mengatasi keterbatasan jumlah data dan meningkatkan variasi gambar, proyek ini menerapkan strategi berikut:

* **Offline Augmentation**: Proses augmentasi gambar dilakukan secara manual terlebih dahulu sebelum pelatihan dan disimpan ke dalam penyimpanan (Google Drive).
* **Data Splitting**: Dataset asli dibagi secara proporsional menjadi tiga bagian, yaitu data pelatihan (*train*), validasi (*validation*), dan pengujian (*test*).
* **Ekspansi Data Latih**: Seluruh hasil gambar augmentasi digabungkan secara khusus ke dalam folder *train* untuk memperkaya pemahaman model selama masa pelatihan, sementara data validasi dan uji tetap menggunakan gambar asli yang bersih dari manipulasi.

## 📊 Eksperimen Arsitektur & Performa Model

Proyek ini menguji tiga skema arsitektur *Deep Learning* yang berbeda. Berikut adalah ringkasan hasil performa dari masing-masing model setelah diurutkan dari akurasi pengujian tertinggi:


| No | Arsitektur Model | Akurasi Pelatihan (Train Acc) | Akurasi Pengujian (Test Acc) | Analisis Kondisi Model |
| :---: | :--- | :---: | :---: | :--- |
| **1** | **Transfer Learning: EfficientNetB0 + Fine Tuning** | **90.75%** | **86.19%** | **Model Terbaik (Stabil & Generalisasi Baik)** |
| 2 | Transfer Learning: MobileNetV2 + Fine Tuning | 88.49% | 77.61% | Cukup Baik (*Overfitting* Ringan) |
| 3 | Custom CNN (Conv2D + MaxPooling) | 90.30% | 51.17% | *Overfitting* Parah (Menghafal Data Latih) |

### 📌 Kesimpulan Analisis
* Penggunaan **Transfer Learning (EfficientNetB0)** dengan teknik *fine-tuning* menghasilkan performa paling optimal dengan akurasi uji mencapai **86.19%** dan selisih eror yang tipis dengan data latih, menandakan model mampu mengenali objek baru dengan baik.
* Model **Custom CNN** mengalami *overfitting* yang cukup tinggi (selisih akurasi mencapai ~39%). Hal ini menunjukkan arsitektur mandiri tersebut membutuhkan penambahan teknik regularisasi seperti *Dropout*, *Batch Normalization*, atau penyesuaian kapasitas jaringan saraf.

## 🛠️ Panduan Instalasi & Penggunaan

1. Clone repositori ini ke komputer Anda:
   ```bash
   git clone https://github.com
   ```

2. Pasang semua pustaka (*dependencies*) yang diperlukan:
   ```bash
   pip install -r requirements.txt
   ```
