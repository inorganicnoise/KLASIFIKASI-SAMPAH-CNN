# ♻️ Klasifikasi Jenis Sampah Menggunakan Convolutional Neural Network (CNN)

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

Proyek ini merupakan implementasi **Deep Learning untuk klasifikasi jenis sampah** sebagai bentuk dukungan terhadap **SDG 12: Responsible Consumption and Production (Konsumsi dan Produksi yang Bertanggung Jawab)**.

Melalui pemanfaatan teknologi Artificial Intelligence (AI), proyek ini bertujuan membantu proses identifikasi jenis sampah berdasarkan gambar sehingga dapat mendukung kesadaran dan kegiatan pemilahan sampah.

---

## 👥 Anggota Kelompok

| No. | Nama Anggota | NIM |
|---|---|---|
| 1 | Elsya Sagitha Damayanti S | F1G125029 |
| 2 | Rahmah Hidayah Lahompu | F1G125047 |
| 3 | Ridha Septiani K | F1G125075 |

**Program Studi Ilmu Komputer**  
**Fakultas Matematika dan Ilmu Pengetahuan Alam**  
**Universitas Halu Oleo**

---

## 📌 Deskripsi Proyek

Proyek ini mengembangkan model klasifikasi gambar sampah menggunakan metode **Convolutional Neural Network (CNN)**. Model dirancang untuk mengenali karakteristik visual gambar, seperti bentuk, warna, tekstur, dan pola, kemudian mengelompokkannya ke dalam empat kategori sampah.

Model CNN dibangun dan dilatih dari awal (*from scratch*) menggunakan TensorFlow/Keras, tanpa menggunakan Transfer Learning maupun model pre-trained. Dengan pendekatan ini, model mempelajari fitur gambar secara langsung dari dataset yang digunakan.

Empat kategori sampah yang diklasifikasikan adalah:

1. Food Organics
2. Metal
3. Paper
4. Plastic

Proyek ini menggunakan dataset RealWaste dan dikembangkan melalui Google Colab. Model yang telah dilatih juga digunakan untuk melakukan prediksi terhadap gambar sampah baru.

## 🎯 Latar Belakang

Sampah merupakan salah satu permasalahan lingkungan yang membutuhkan perhatian, termasuk di lingkungan perguruan tinggi. Salah satu tantangan dalam pengelolaan sampah adalah proses pemilahan berdasarkan jenis materialnya.

Perkembangan teknologi Artificial Intelligence, khususnya Deep Learning, memungkinkan komputer mengenali objek melalui gambar. Salah satu metode yang dapat digunakan adalah Convolutional Neural Network (CNN), yang mampu mempelajari fitur visual secara otomatis.

Berdasarkan hal tersebut, proyek ini menerapkan CNN untuk mengklasifikasikan empat jenis sampah berdasarkan citra gambar. Pengembangan ini diharapkan dapat menjadi salah satu bentuk pemanfaatan teknologi dalam mendukung pengelolaan sampah dan tujuan SDG 12.

## 🎯 Tujuan Proyek

1. Membangun model CNN menggunakan TensorFlow/Keras untuk klasifikasi gambar sampah.
2. Mengidentifikasi empat kategori sampah berdasarkan karakteristik visual gambar.
3. Menerapkan teknik preprocessing dan data augmentation pada dataset.
4. Menggunakan class weight untuk membantu menangani ketidakseimbangan jumlah gambar antar kelas.
5. Mengevaluasi performa model menggunakan accuracy, precision, recall, F1-score, dan confusion matrix.
6. Menguji kemampuan model dalam memprediksi gambar sampah baru.

## ❓ Rumusan Masalah

1. Bagaimana membangun model CNN untuk mengklasifikasikan jenis sampah berdasarkan citra gambar?
2. Bagaimana penerapan preprocessing dan data augmentation dalam proses pelatihan model?
3. Bagaimana performa model dalam mengklasifikasikan empat kategori sampah pada data testing?
4. Bagaimana kemampuan model dalam mengenali gambar sampah baru di luar data pelatihan?

---

## 🗑️ Dataset

Dataset yang digunakan adalah **RealWaste Dataset** yang diperoleh melalui Kaggle.

🔗 **Sumber Dataset:** [RealWaste - Kaggle](https://www.kaggle.com/datasets/joebeachcapital/realwaste)

RealWaste merupakan dataset citra sampah yang berisi berbagai jenis material sampah. Dalam proyek ini, dataset difokuskan pada empat kategori, yaitu Food Organics, Metal, Paper, dan Plastic.

### 📊 Informasi Dataset

| Keterangan | Detail |
|---|---|
| Nama Dataset | RealWaste |
| Sumber | Kaggle |
| Total gambar yang digunakan | 2.622 gambar |
| Jumlah kategori | 4 kelas |
| Ukuran gambar input | 224 × 224 piksel |
| Format gambar | RGB |
| Jenis tugas | Image Classification |

### 🏷️ Kategori Klasifikasi

| No. | Kategori | Jumlah Gambar |
|---|---|---:|
| 1 | Food Organics | 411 |
| 2 | Metal | 790 |
| 3 | Paper | 500 |
| 4 | Plastic | 921 |
| | **Total** | **2.622** |

### ✂️ Pembagian Dataset

Dataset dibagi menggunakan library `split-folders` dengan rasio 70% untuk training, 15% untuk validation, dan 15% untuk testing. Pembagian menggunakan `seed=42` agar hasilnya dapat direproduksi.

| Bagian | Proporsi | Jumlah Gambar |
|---|---:|---:|
| Training Set | 70% | 1.834 |
| Validation Set | 15% | 392 |
| Testing Set | 15% | 396 |
| **Total** | **100%** | **2.622** |

Distribusi jumlah gambar antar kategori tidak seimbang. Oleh karena itu, digunakan teknik class weight dalam proses pelatihan untuk membantu mengurangi pengaruh ketidakseimbangan tersebut.

---

## 🧠 Metode dan Teknologi

### 1. Convolutional Neural Network (CNN)

CNN merupakan salah satu arsitektur Deep Learning yang banyak digunakan untuk pengolahan citra. CNN dapat mempelajari fitur visual gambar melalui lapisan konvolusi dan pooling.

Dalam proyek ini, CNN dibangun dari awal (*from scratch*) menggunakan beberapa lapisan Conv2D, MaxPooling2D, Flatten, dan Dense.

### 2. Teknologi yang Digunakan

| Komponen | Teknologi |
|---|---|
| Bahasa Pemrograman | Python |
| Framework Deep Learning | TensorFlow / Keras |
| Pengembangan Model | Google Colab |
| Pengunduhan Dataset | KaggleHub |
| Pembagian Dataset | split-folders |
| Pengolahan Data | NumPy, Pillow |
| Visualisasi | Matplotlib |
| Evaluasi Model | Scikit-learn |
| Version Control | Git & GitHub |

---

## ⚙️ Tahapan Pengembangan

### 1. Pengumpulan Dataset

Dataset RealWaste diunduh dari Kaggle menggunakan library `kagglehub`. Dari sembilan kategori yang tersedia, proyek ini memilih empat kategori, yaitu Food Organics, Metal, Paper, dan Plastic.

### 2. Exploratory Data Analysis (EDA)

Tahap EDA dilakukan untuk mengetahui struktur dataset, jumlah gambar pada setiap kategori, serta melihat contoh gambar dari masing-masing kelas.

### 3. Pembagian Dataset

Dataset dibagi menjadi tiga bagian, yaitu training, validation, dan testing dengan rasio 70:15:15 menggunakan library `split-folders`.

### 4. Preprocessing Data

Tahap preprocessing dilakukan dengan:

- Memuat gambar dari folder berdasarkan kategori.
- Mengubah ukuran gambar menjadi 224 × 224 piksel.
- Menggunakan batch size sebesar 32.
- Mengubah gambar menjadi format yang dapat diproses oleh model.
- Melakukan normalisasi nilai piksel menggunakan `Rescaling(1./255)` ke rentang 0–1.

### 5. Data Augmentation

Data augmentation digunakan untuk memberikan variasi pada gambar training melalui beberapa teknik:

- Random Horizontal Flip.
- Random Rotation.
- Random Zoom.

Teknik ini bertujuan membantu model mempelajari variasi tampilan gambar dan mengurangi kecenderungan menghafal data training.

### 6. Penerapan Class Weight

Class weight dihitung berdasarkan jumlah gambar pada setiap kategori di data training. Bobot tersebut digunakan selama pelatihan untuk membantu model memperhatikan kelas yang memiliki jumlah gambar lebih sedikit.

### 7. Pembuatan Arsitektur CNN

Model CNN dibangun menggunakan TensorFlow/Keras dengan susunan lapisan sebagai berikut:

1. Input Layer dengan ukuran gambar 224 × 224 × 3.
2. Data Augmentation.
3. Rescaling.
4. Conv2D dan MaxPooling2D sebanyak empat blok.
5. Flatten.
6. Dense dengan 64 neuron dan aktivasi ReLU.
7. Dropout sebesar 0,5.
8. Output Layer dengan 4 neuron dan aktivasi Softmax.

### 8. Kompilasi Model

Model dikompilasi menggunakan:

- Optimizer: Adam.
- Learning Rate: 0,0005.
- Loss Function: Sparse Categorical Crossentropy.
- Evaluation Metric: Accuracy.

### 9. Training Model

Model dilatih menggunakan data training dan validation dengan maksimal 40 epoch. Proses pelatihan menggunakan class weight serta callback Early Stopping dan ReduceLROnPlateau untuk membantu mengontrol proses pembelajaran.

### 10. Evaluasi Model

Evaluasi dilakukan menggunakan data testing untuk mengetahui kemampuan model dalam mengklasifikasikan empat kategori sampah.

Metrik evaluasi yang digunakan meliputi:

- Accuracy.
- Precision.
- Recall.
- F1-Score.
- Confusion Matrix.

Selain itu, ditampilkan grafik training accuracy, validation accuracy, training loss, dan validation loss.

### 11. Penyimpanan Model

Model CNN yang telah dilatih disimpan dalam format `.keras` dengan nama `waste_classifier_cnn.keras`. Nama kelas disimpan dalam file `class_names.json` agar dapat digunakan kembali ketika melakukan prediksi.

### 12. Pengujian Gambar Baru

Pengujian dilakukan dengan mengunggah gambar sampah baru melalui Google Colab. Gambar diproses terlebih dahulu, kemudian dimasukkan ke model untuk menghasilkan kategori prediksi, confidence score, dan probabilitas setiap kelas.

---

## 📊 Hasil Evaluasi Model

Model dievaluasi menggunakan 396 gambar pada data testing.

### Hasil Akhir Evaluasi

| Metrik | Nilai |
|---|---:|
| Test Accuracy | **63,64%** |
| Test Loss | 0,8756 |
| Weighted Precision | 0,64 |
| Weighted Recall | 0,64 |
| Weighted F1-Score | 0,63 |
| Macro F1-Score | 0,65 |

### Classification Report

| Kategori | Precision | Recall | F1-Score | Support |
|---|---:|---:|---:|---:|
| Food Organics | 0,70 | 1,00 | 0,82 | 63 |
| Metal | 0,57 | 0,55 | 0,56 | 119 |
| Paper | 0,60 | 0,72 | 0,65 | 75 |
| Plastic | 0,68 | 0,50 | 0,57 | 139 |
| **Weighted Average** | **0,64** | **0,64** | **0,63** | **396** |

### Pembahasan Hasil

Berdasarkan hasil pengujian, model memperoleh accuracy sebesar 63,64% pada 396 gambar testing.

Kategori Food Organics memperoleh nilai recall sebesar 1,00 dan F1-score sebesar 0,82. Hal ini menunjukkan bahwa seluruh gambar Food Organics pada data testing berhasil dikenali oleh model.

Sementara itu, kategori Metal memperoleh F1-score sebesar 0,56 dan Plastic sebesar 0,57. Kedua kategori tersebut masih memiliki tantangan dalam proses klasifikasi, yang dapat dipengaruhi oleh kemiripan karakteristik visual dan variasi tampilan gambar.

Hasil evaluasi menunjukkan bahwa model sudah dapat melakukan klasifikasi terhadap empat kategori sampah, tetapi performanya masih dapat ditingkatkan melalui pengembangan arsitektur, penambahan data, dan penyempurnaan proses pelatihan.

---

## 💾 Penyimpanan Model

Model dan nama kelas disimpan agar dapat digunakan kembali tanpa harus melakukan pelatihan dari awal.

| Nama File | Keterangan |
|---|---|
| `waste_classifier_cnn.keras` | Model CNN hasil pelatihan |
| `model_final.keras` | Salinan model yang diunduh dari Google Colab |
| `class_names.json` | Daftar nama kategori sampah |

Model disimpan menggunakan format Keras sehingga dapat dimuat kembali menggunakan TensorFlow/Keras.

Contoh kode untuk memuat model:

```python
import tensorflow as tf
import json

model = tf.keras.models.load_model("waste_classifier_cnn.keras")

with open("class_names.json", "r") as f:
    class_names = json.load(f)
```

---

## 🚀 Saran Pengembangan

Beberapa hal yang dapat dikembangkan lebih lanjut dari proyek ini adalah:

- Menambah jumlah gambar pada setiap kategori agar model memperoleh variasi data yang lebih banyak.
- Meningkatkan performa model melalui penyesuaian arsitektur CNN dan hyperparameter.
- Menguji model menggunakan lebih banyak gambar sampah yang diambil langsung dari lingkungan kampus.
- Mencoba arsitektur CNN lain sebagai pembanding.
- Mengembangkan aplikasi berbasis web atau mobile agar model lebih mudah digunakan oleh masyarakat.

---

## 📚 Kesimpulan

Proyek ini berhasil mengimplementasikan Convolutional Neural Network menggunakan TensorFlow/Keras untuk mengklasifikasikan empat kategori sampah, yaitu Food Organics, Metal, Paper, dan Plastic, berdasarkan dataset RealWaste.

Model dibangun dan dilatih dari awal dengan menerapkan preprocessing, data augmentation, class weight, Dropout, serta callback untuk membantu proses pelatihan.

Berdasarkan evaluasi pada 396 gambar testing, model memperoleh accuracy sebesar **63,64%** dan weighted F1-score sebesar **0,63**. Hasil tersebut menunjukkan bahwa model sudah mampu mengenali beberapa karakteristik gambar sampah, tetapi masih memerlukan pengembangan untuk meningkatkan ketepatan klasifikasinya.

Melalui proyek ini, pemanfaatan Deep Learning diharapkan dapat menjadi salah satu bentuk dukungan teknologi terhadap identifikasi dan pemilahan sampah sebagai bagian dari upaya mendukung **SDG 12: Konsumsi dan Produksi yang Bertanggung Jawab**.

---

## 📚 Referensi

1. Single, S., Iranmanesh, S., & Raad, R. (2023). RealWaste: A novel real-life data set for landfill waste classification using deep learning. *Information, 14*(12), 633. https://doi.org/10.3390/info14120633

2. Kaggle. (n.d.). *RealWaste Dataset*. https://www.kaggle.com/datasets/joebeachcapital/realwaste

3. United Nations. (n.d.). *Goal 12: Ensure sustainable consumption and production patterns*. https://sdgs.un.org/goals/goal12

4. TensorFlow. (n.d.). *TensorFlow Documentation*. https://www.tensorflow.org/
