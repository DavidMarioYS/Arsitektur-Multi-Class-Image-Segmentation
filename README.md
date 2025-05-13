
# 🔍 Komparasi Arsitektur Mobile U-Net dan BiSeNetV3 pada Dataset Original dan Augmentasi

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk membandingkan performa dua arsitektur model segmentasi citra: **Mobile U-Net** dan **BiSeNetV3**. Keduanya diuji pada dua jenis dataset:  
- Dataset **original** (tanpa teknik augmentasi)  
- Dataset dengan **augmentasi** (menggunakan rotasi, flipping, dsb)

Melalui proyek ini, kita ingin mengevaluasi pengaruh teknik augmentasi data terhadap performa model, serta membandingkan keunggulan masing-masing arsitektur dalam melakukan segmentasi gambar.

---

## 🎯 Tujuan

- Mengamati dampak augmentasi data terhadap kinerja segmentasi.
- Membandingkan akurasi dan efisiensi **Mobile U-Net** vs **BiSeNetV3**.
- Mendapatkan hasil segmentasi citra yang lebih baik melalui pendekatan arsitektur dan data yang tepat.
- Menyediakan eksperimen yang **standar** dan **reproducible**.

---

## 🧾 Definisi Istilah

| Istilah         | Definisi                                                                 |
|-----------------|--------------------------------------------------------------------------|
| **Segmentasi Citra** | Teknik membagi gambar ke dalam area-area bermakna berdasarkan objek atau fitur. |
| **Mobile U-Net** | Versi ringan dari U-Net yang dirancang untuk efisiensi, cocok untuk perangkat mobile. |
| **BiSeNetV3**    | Arsitektur segmentasi modern yang cepat dan akurat dengan pemisahan informasi spasial dan kontekstual. |
| **Augmentasi Data** | Teknik manipulasi citra untuk memperbanyak variasi data pelatihan, seperti rotasi, flip, zoom. |
| **Batch Size**   | Jumlah data yang diproses sebelum model memperbarui bobotnya.           |
| **Epoch**        | Satu kali seluruh dataset dilatih melalui model.                        |
| **IoU (Intersection over Union)** | Ukuran tumpang tindih antara prediksi segmentasi dan ground truth.         |
| **Dice Coefficient** | Metrik kesamaan antara dua set data, sering digunakan dalam segmentasi.         |

---

## 🧰 Bahan dan Persiapan

### 🗃️ Dataset
- Dataset citra dan mask (annotasi)
- Dibagi ke dalam dua versi:
  - **Original**: dataset asli tanpa augmentasi
  - **Augmentasi**: dataset dengan transformasi data (rotasi, flip, dsb)

### 💻 Tools dan Library
- **Python 3.x**
- **Google Colab** atau **Jupyter Notebook**
- Framework: `TensorFlow`, `Keras`
- Library tambahan:
  ```bash
  numpy
  matplotlib
  scikit-learn
  opencv-python
  ```
  
### 📋 Persiapan
- Semua model dijalankan dengan:
  - `Batch Size`: 8
  - `Epoch`: 100
  - Optimizer: Adam
  - Loss Function: Dice Loss / Categorical Crossentropy
- Data dibagi menjadi: 
  - **Train Set**
  - **Validation Set**
  - **Test Set**

---

## 📁 Struktur File

| File Notebook                                    | Dataset    | Arsitektur   |
|--------------------------------------------------|------------|--------------|
| `[STANDARISASI] ORI Mobile U-Net B8E100.ipynb`   | Original   | Mobile U-Net |
| `[STANDARISASI] ORI BiSeNetV3 B8E100.ipynb`      | Original   | BiSeNetV3    |
| `[STANDARISASI] AUG Mobile U-Net B8E100.ipynb`   | Augmentasi | Mobile U-Net |
| `[STANDARISASI] AUG BiSeNetV3 B8E100.ipynb`      | Augmentasi | BiSeNetV3    |

---

## 📈 Output & Evaluasi

### 🔬 Metrik Evaluasi:
- **Accuracy**: Persentase prediksi benar.
- **Loss**: Perbedaan antara output prediksi dan label.
- **IoU (Intersection over Union)**: Ukuran tumpang tindih prediksi dan ground truth.
- **Dice Coefficient**: Kesamaan antara area prediksi dan ground truth.

### 📊 Visualisasi:
- Plot **akurasi dan loss** selama pelatihan.
- Gambar prediksi segmentasi dengan **overlay mask**.
- Perbandingan visual antar model & dataset.

---

## 📌 Contoh Visualisasi

```
Citra Input → Mask Ground Truth → Prediksi Model
```
- Akan ditampilkan per model dan per jenis dataset.
- Membantu dalam evaluasi kualitatif hasil segmentasi.

---

## 📌 Kesimpulan yang Diharapkan

- Apakah augmentasi membantu meningkatkan performa model?
- Arsitektur mana yang lebih cocok untuk segmentasi citra pada dataset ini?
- Trade-off antara akurasi dan kecepatan inference dari masing-masing model.

---

## ✍️ Penutup

Proyek ini diharapkan menjadi referensi dalam memilih arsitektur segmentasi yang tepat serta memahami pentingnya augmentasi dalam pelatihan model deep learning. Semua hasil dan eksperimen dapat diperluas atau digunakan kembali untuk kebutuhan segmentasi citra lainnya di bidang medis, pertanian, atau industri.
