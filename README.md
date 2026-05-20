Computer Vision for Sea Animal"

Proyek ini menggunakan data set binatang laut yang banyak diambil didalam air.
Augmentasi proyek ini dilakukan secara manual (off-line augmentation) yang disimpan ke dalam drive,
dimana data asli di lakukan proses augmentasi dan disimpan ke dalam folder sendiri.
Kemudian dataset asli dibagi menjadi train, validation dan test. Data gambar augmentasi digabung ke dalam
folder train

## 🛠️ Cara Instalasi
```bsh
pip install -r requirements.txt
```

## Arsitektur
Project ini menggunakan tiga skema arsitektur
1. CNN menggunakan Conv2D dan MaxPooling dengan akurasi train 90.30% dan akurasi test 51.17%
2. Transfer Learning MobileNetV2 dan fine tuning dengan akurasi train 88.49% dan akurasi test 77.61%
3. Transfer Learning EfficientNetB0 dan fine tuning dengan akurasi train 90.75% dan akurasi test 86.19%

