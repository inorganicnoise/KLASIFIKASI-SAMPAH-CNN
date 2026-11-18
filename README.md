
# Project Deep Learning - SDGs 12 Konsumsi dan Produksi yang Bertanggung Jawab

## ♻️ Implementasi Transfer Learning Berbasis CNN untuk Klasifikasi Jenis Sampah di Lingkungan Kampus

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

Proyek ini berkaitan dengan **SDG 12: Responsible Consumption and Production (Konsumsi dan Produksi yang Bertanggung Jawab)**.

SDG 12 menekankan pentingnya pola konsumsi dan produksi yang bertanggung jawab, termasuk pengurangan limbah serta peningkatan pengelolaan sampah.

Melalui penerapan teknologi Deep Learning, proyek ini mendukung proses identifikasi jenis sampah sebagai salah satu upaya untuk meningkatkan kesadaran dan efektivitas pemilahan sampah.

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

Proyek ini merupakan implementasi Deep Learning untuk mengembangkan sistem klasifikasi otomatis jenis sampah berdasarkan citra gambar (*image classification*) ke dalam empat kategori: Food Organics, Metal, Paper, dan Plastic.

Sistem dirancang untuk mengenali dan mengelompokkan berbagai jenis sampah berdasarkan karakteristik visualnya, seperti bentuk, warna, tekstur, dan pola.

Model yang digunakan adalah Convolutional Neural Network (CNN) murni, yaitu arsitektur CNN yang dirancang dan dilatih dari awal (from scratch) menggunakan TensorFlow/Keras, tanpa transfer learning dan tanpa model pre-trained. Seluruh bobot model dilatih hanya dari dataset RealWaste.

Proyek ini berfokus pada pemanfaatan teknologi Artificial Intelligence (AI) untuk membantu proses identifikasi dan pemilahan sampah, khususnya dalam konteks lingkungan perguruan tinggi.

## 🎯 Latar Belakang

Sampah merupakan salah satu permasalahan lingkungan yang masih sering dijumpai, termasuk di lingkungan perguruan tinggi. Proses pemilahan sampah masih menjadi tantangan karena sampah yang tercampur menyulitkan pengelolaan dan daur ulang.

Seiring perkembangan Deep Learning, klasifikasi citra dapat dimanfaatkan untuk mengenali jenis sampah secara otomatis berdasarkan karakteristik visualnya. CNN dipilih karena mampu mempelajari fitur visual seperti bentuk, tekstur, dan pola secara otomatis dari gambar.

Proyek ini menerapkan CNN yang dibangun dari awal untuk mengklasifikasikan empat kategori sampah sebagai bentuk pemanfaatan teknologi AI dalam mendukung pengelolaan sampah sesuai SDG 12.

## 🎯 Tujuan Proyek

1. Membangun model CNN dari awal (tanpa transfer learning) untuk klasifikasi jenis sampah.
2. Mengidentifikasi empat kategori sampah (Food Organics, Metal, Paper, Plastic) berdasarkan citra.
3. Mengevaluasi performa model menggunakan accuracy, precision, recall, F1-score, dan confusion matrix.
4. Menganalisis pengaruh teknik augmentasi data, class weight, dan regularisasi terhadap performa model.

## ❓ Rumusan Masalah

1. Bagaimana membangun model CNN dari awal untuk mengklasifikasikan empat jenis sampah berdasarkan gambar?
2. Bagaimana performa model CNN pada data uji dan pada gambar di luar dataset?
3. Kategori sampah mana yang paling sulit dibedakan oleh model, dan apa penyebabnya?
4. Bagaimana pengaruh augmentasi data, class weight, dan Batch Normalization terhadap kestabilan pelatihan?

---

## 🗑️ Dataset

Dataset yang digunakan dalam proyek ini adalah **RealWaste Dataset** yang diperoleh melalui platform Kaggle.

🔗 **Sumber Dataset:** [RealWaste - Kaggle](https://www.kaggle.com/datasets/joebeachcapital/realwaste)

RealWaste merupakan dataset citra sampah yang berisi gambar berbagai jenis material sampah. Dataset ini digunakan untuk melatih dan menguji kemampuan model dalam mengenali serta mengklasifikasikan jenis sampah berdasarkan karakteristik visualnya. RealWaste berisi 4.752 gambar dalam 9 kategori. Dari kategori tersebut, proyek ini hanya memakai 4 kategori:

### 📊 Informasi Dataset

| Keterangan | Detail |
|---|---|
| Nama Dataset | RealWaste |
| Sumber | Kaggle |
| Total Gambar | 4.752 gambar |
| Jumlah Kategori | 9 kelas |
| Format Gambar | RGB |
| Resolusi | 524 × 524 piksel |
| Jenis Tugas | Image Classification |

### 🏷️ Kategori Klasifikasi

| No. | Kategori | Jumlah Gambar |
|---|---|---:|
| 1 | Food Organics | 411 |
| 2 | Metal | 790 |
| 3 | Paper | 500 |
| 4 | Plastic | 921 |
| | **Total** | **2.622** |

### ✂️ Pembagian Dataset

Dataset dibagi dengan library split-folders (seed=42) dengan rasio 70% : 15% : 15%.

| Kategori | Training | Validation | Testing |
|---|---:|---:|---:|
| Food Organics | 287 | 61 | 63 |
| Metal | 553 | 118 | 119 |
| Paper | 350 | 75 | 75 |
| Plastic | 644 | 138 | 139 |
| **Total** | **1.834** | **392** | **396** |

Jumlah gambar tidak seimbang antar kategori, sehingga digunakan class weight saat pelatihan.

---

## 🧠 Metode dan Teknologi

### 1. Convolutional Neural Network (CNN)

CNN merupakan arsitektur Deep Learning yang banyak digunakan dalam pengolahan citra. CNN mampu mempelajari karakteristik visual gambar melalui proses ekstraksi fitur, seperti bentuk, tekstur, dan pola.

### Arsitektur Model

| Komponen | Keterangan |
|---|---|
| Input | Gambar RGB 224 × 224 piksel |
| Rescaling (1/255) | Normalisasi piksel di dalam model, sehingga prediksi memakai gambar mentah 0-255 |
| Data Augmentation | RandomFlip (horizontal dan vertikal), RandomRotation (0,1), RandomZoom (0,15), RandomTranslation (0,1); aktif hanya saat training |
| Blok Konvolusi 1-4 | Masing-masing 2 × [Conv2D 3×3 + BatchNormalization (momentum 0,9) + ReLU] lalu MaxPooling2D; jumlah filter 32, 64, 128, 256 |
| GlobalAveragePooling2D | Meringkas *feature map* menjadi vektor fitur (parameter jauh lebih sedikit dibanding Flatten) |
| Dense (128, ReLU) + Dropout (0,5) | Lapisan klasifikasi dan regularisasi |
| Dense (4, softmax) | Probabilitas untuk 4 kategori |

### Konfigurasi Pelatihan

| Parameter | Nilai |
|---|---|
| Optimizer | Adam, learning rate 0,0005 |
| Loss | Sparse categorical crossentropy |
| Batch size | 32 |
| Epoch maksimum | 50 |
| Class weight | `balanced` (dihitung dari data training) |
| Early Stopping | Memantau `val_loss`, patience 10, mengembalikan bobot terbaik |
| ReduceLROnPlateau | Faktor 0,5, patience 3 |

### 🛠️ Teknologi yang Digunakan

| Komponen | Teknologi |
|---|---|
| Bahasa Pemrograman | Python |
| Framework Deep Learning | TensorFlow / Keras |
| Metode | CNN murni (from scratch) |
| Pengembangan Model | Google Colab |
| Pengunduhan Dataset | KaggleHub |
| Pembagian Dataset | split-folders |
| Pengolahan Data | NumPy, Pillow |
| Visualisasi | Matplotlib |
| Evaluasi Model | Scikit-learn |
| Version Control | Git & GitHub |

---

## ⚙️ Tahapan Pengembangan

1. **Pengumpulan Dataset** - mengunduh RealWaste dari Kaggle dengan `kagglehub`.
2. **Seleksi Kelas dan EDA** - memilih 4 kategori, memeriksa jumlah gambar per kelas, dan menampilkan contoh gambar.
3. **Pembagian Dataset** - training 70%, validation 15%, testing 15% (`seed=42`).
4. **Data Tambahan (opsional)** - foto tambahan dengan latar beragam dimasukkan ke training set saja (`data_tambahan/`).
5. **Preprocessing dan Pipeline** - memuat gambar 224 × 224, batch size 32, `cache` dan `prefetch`; normalisasi dilakukan di dalam model.
6. **Class Weight** - menghitung bobot kelas dari data training.
7. **Pemodelan** - membangun CNN dengan augmentation, Batch Normalization, dan Dropout.
8. **Training** - Adam, Early Stopping, dan ReduceLROnPlateau.
9. **Evaluasi** - accuracy, classification report, confusion matrix, dan diagnosis distribusi prediksi.
10. **Uji Foto di Luar Dataset** - evaluasi pada folder `tes_luar/` yang tidak dipakai untuk training.
11. **Penyimpanan Model** - `waste_classifier_cnn.keras` dan `class_names.json`.
12. **Prediksi Gambar Baru** - mengunggah gambar, menampilkan kategori prediksi, confidence, dan peringatan jika model kurang yakin.

---

## 📊 Hasil Evaluasi Model

Pada percobaan awal, kurva akurasi dan loss validasi sangat tidak stabil (akurasi validasi naik-turun antara sekitar 0,30 dan 0,67 dan loss validasi melonjak hingga di atas 2), sementara akurasi training naik mulus hingga sekitar 0,80. Pola ini diduga akibat ketidakcocokan statistik Batch Normalization antara mode training (data ber-augmentation) dan mode evaluasi.

| Metrik | Nilai |
|---|---:|
| Akurasi training (akhir) | 80,1% |
| Akurasi validasi (akhir) | 53,6% |
| Akurasi test | 66,2% |

Hasil per kategori pada data test (dihitung dari confusion matrix):

| Kategori | Jumlah Test | Diprediksi | Benar | Recall | Precision |
|---|---:|---:|---:|---:|---:|
| Food Organics | 63 | 77 | 57 | 90,5% | 74,0% |
| Metal | 119 | 90 | 63 | 52,9% | 70,0% |
| Paper | 75 | 35 | 25 | 33,3% | 71,4% |
| Plastic | 139 | 194 | 117 | 84,2% | 60,3% |

Kesalahan terbanyak: Metal diprediksi sebagai Plastic (39 gambar) dan Paper diprediksi sebagai Plastic (33 gambar). Plastic menjadi kelas "penampung" (diprediksi 194 kali padahal aslinya 139).

### Hasil Akhir (Setelah Fine-Tuning)

| Metrik | Nilai (Weighted Average) |
|---|---:|
| Accuracy | 85,95% |
| Precision | 86,14% |
| Recall | 85,95% |
| F1-Score | 85,94% |

### F1-Score per Kategori

| Kategori | Sebelum | Sesudah |
|---|---:|---:|
| Cardboard | 0,85 | 0,86 |
| Food Organics | 0,88 | 0,90 |
| Glass | 0,82 | 0,88 |
| Metal | 0,81 | 0,84 |
| Miscellaneous Trash | 0,66 | 0,73 |
| Paper | 0,83 | 0,86 |
| Plastic | 0,76 | 0,84 |
| Textile Trash | 0,89 | 0,91 |
| Vegetation | 0,95 | 0,98 |

### Pembahasan

- Fine-tuning meningkatkan akurasi pengujian dari 81,92% menjadi 85,95% dan menurunkan test loss, dengan peningkatan F1-score pada seluruh kategori.
- Kategori dengan performa terbaik adalah **Vegetation** (F1 0,98) dan **Textile Trash** (F1 0,91), yang memiliki ciri visual lebih khas.
- Kategori dengan performa terendah adalah **Miscellaneous Trash** (F1 0,73), karena kelas ini mencakup beragam jenis sampah dengan tampilan visual yang bervariasi.
- Pada tahap fine-tuning, akurasi training mencapai sekitar 99%, sedangkan akurasi validasi sekitar 85%. Selisih ini menunjukkan adanya indikasi *overfitting*, sehingga model masih dapat ditingkatkan.

---

## 🌐 Aplikasi Web

Model akhir diimplementasikan dalam aplikasi web berbasis Streamlit. Pengguna dapat mengunggah gambar sampah (`jpg`, `jpeg`, atau `png`), kemudian aplikasi menampilkan kategori hasil klasifikasi, *confidence score*, dan grafik probabilitas untuk sembilan kategori.

### Menjalankan Aplikasi

```bash
pip install -r requirements.txt
streamlit run app.py
```

### Struktur File Aplikasi

| File | Keterangan |
|---|---|
| `waste_classifier_cnn.keras` | Model CNN hasil pelatihan |
| `class_names.json` | Daftar nama kategori (urutan sama dengan output model) |

---

## 🚀 Saran Pengembangan

- Menambah data sampah yang diambil langsung dari lingkungan kampus dengan latar, cahaya, dan sudut yang beragam.
- Menambah jumlah gambar kategori yang sering salah (Metal dan Paper).
- Menambah kelas "bukan salah satu kategori" agar gambar di luar domain tidak dipaksa masuk ke empat kategori.
- Mencoba variasi arsitektur CNN (jumlah blok, jumlah filter, dan teknik regularisasi) sebagai pembanding.
- Mengembangkan antarmuka aplikasi agar model dapat digunakan langsung oleh pengguna.

---

## 📚 Kesimpulan

Penerapan Transfer Learning berbasis MobileNetV2 dengan TensorFlow berhasil mengklasifikasikan sembilan kategori sampah pada dataset RealWaste dengan akurasi **85,95%** setelah fine-tuning. Model dapat membedakan jenis sampah berdasarkan karakteristik visualnya, dengan kesalahan klasifikasi yang paling banyak terjadi pada kategori Miscellaneous Trash. Hasil klasifikasi dapat dimanfaatkan melalui aplikasi web untuk membantu proses pemilahan sampah di lingkungan kampus, sebagai dukungan terhadap SDG 12.


## Referensi

- Kaggle, [RealWaste Dataset](https://www.kaggle.com/datasets/joebeachcapital/realwaste).
  
- IEEE DataPort, [RealWaste (dataset resmi, lisensi CC BY-NC-SA 4.0)](https://ieee-dataport.org/documents/realwaste).

- United Nations, [SDG 12: Responsible Consumption and Production](https://sdgs.un.org/goals/goal12).

- Single, S., Iranmanesh, S., & Raad, R. (2023). RealWaste: A novel real-life data set for landfill waste classification using deep learning (sumber dataset). *Information*, 14(12), 633. [https://doi.org/10.3390/info14120633](https://doi.org/10.3390/info14120633)

- Wandi, F. A., Kesuma, M. A., Nugraha, C. A., Cahyani, O. I., Umar, I., Septiarini, A., Widians, J. A., & Irsyad, A. (2026). Komparasi ResNet50, MobileNetV2 dan Custom CNN dalam klasifikasi sampah organik dan anorganik. *JATI (Jurnal Mahasiswa Teknik Informatika)*, 10(4), 6475–6481. [https://ejournal.itn.ac.id/jati/article/download/18566/9866/](https://ejournal.itn.ac.id/jati/article/download/18566/9866/)

- Bahagia, G. A., & Akbar, M. (2024). Klasifikasi sampah organik dan anorganik menggunakan metode Convolutional Neural Network (CNN). *JATI (Jurnal Mahasiswa Teknik Informatika)*, 8(5), 10349–10355. [https://ejournal.itn.ac.id/jati/article/download/11038/6267/](https://ejournal.itn.ac.id/jati/article/download/11038/6267/)

- Husnawati, H., Malyan, A. B. J., Putra, R. R., & Agustri, S. (2024). Smart trash box technology of computer vision to support Ecogreen campus. In N. L. Husni et al. (Eds.), *Proceedings of the 7th FIRST 2023 International Conference on Global Innovations (FIRST-ESCSI 2023)* (Advances in Engineering Research, Vol. 232, pp. 220–229). Atlantis Press. [https://doi.org/10.2991/978-94-6463-386-3_25](https://doi.org/10.2991/978-94-6463-386-3_25)

- Budi, B. S., & Fatma, Y. (2026). Metode systematic literature review arsitektur Convolutional Neural Network untuk klasifikasi sampah berbasis citra. *Jurnal Teknik Informatika dan Teknologi Informasi*, 6(2), 297–319. [https://doi.org/10.55606/jutiti.v6i2.7329](https://doi.org/10.55606/jutiti.v6i2.7329)

- Shorten, C., & Khoshgoftaar, T. M. (2019). A survey on image data augmentation for deep learning. *Journal of Big Data*, 6, 60. [https://doi.org/10.1186/s40537-019-0197-0](https://doi.org/10.1186/s40537-019-0197-0)

- Ioffe, S., & Szegedy, C. (2015). Batch normalization: Accelerating deep network training by reducing internal covariate shift. *Proceedings of the 32nd International Conference on Machine Learning (ICML)*. [https://arxiv.org/abs/1502.03167](https://arxiv.org/abs/1502.03167)

- Srivastava, N., Hinton, G., Krizhevsky, A., Sutskever, I., & Salakhutdinov, R. (2014). Dropout: A simple way to prevent neural networks from overfitting. *Journal of Machine Learning Research*, 15(56), 1929–1958. [https://jmlr.org/papers/v15/srivastava14a.html](https://jmlr.org/papers/v15/srivastava14a.html)

- Kingma, D. P., & Ba, J. (2015). Adam: A method for stochastic optimization. *3rd International Conference on Learning Representations (ICLR)*. [https://arxiv.org/abs/1412.6980](https://arxiv.org/abs/1412.6980)
