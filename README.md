Berikut adalah **README.md** lengkap untuk GitHub repository proyek kamu, termasuk dokumentasi cara menjalankan kodenya dan versi library yang digunakan:

---


# 🧠 Voice-Based Respiratory Sound Recognition with CNN

Proyek ini bertujuan untuk mengembangkan sistem klasifikasi suara napas menggunakan **Convolutional Neural Network (CNN)** dan ekstraksi fitur **MFCC** (Mel-Frequency Cepstral Coefficients). Sistem ini diharapkan dapat membantu identifikasi dini penyakit pernapasan berdasarkan rekaman suara pasien.

---

## 📁 Dataset

Dataset yang digunakan adalah:
**[Respiratory Sound Database - KaggleHub (vbookshelf)](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database)**

Berisi:
- File audio `.wav`
- File segmentasi `.txt`
- Metadata diagnosis pasien `.csv`

---

## 🛠️ Library dan Versi

| Library        | Versi     |
|----------------|-----------|
| TensorFlow     | 2.18.0    |
| Scikit-learn   | 1.6.1     |
| Seaborn        | 0.13.2    |
| Matplotlib     | 3.10.0    |
| NumPy          | 2.0.2     |
| Librosa        | 0.11.0    |
| Pandas         | 2.2.2     |
| KaggleHub      | 0.3.12    |

---

## 📦 Instalasi & Persiapan

1. **Clone repository:**
   ```bash
   git clone https://github.com/yourusername/voicefix-recognition.git
   cd voicefix-recognition


2. **(Opsional) Buat environment baru:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   ```

3. **Install dependency:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Unduh dataset menggunakan KaggleHub:**

   ```python
   import kagglehub
   path = kagglehub.dataset_download("vbookshelf/respiratory-sound-database")
   ```

---

## 🚀 Cara Menjalankan

1. **Ekstrak label diagnosis:**

   * File: `patient_diagnosis.csv` → dict `{Patient_ID: Diagnosis}`

2. **Segmentasi Audio:**

   * Potong file `.wav` berdasarkan waktu awal/akhir dari file `.txt`
   * Simpan dalam folder `segmented_audio/`

3. **Ekstraksi Fitur MFCC:**

   * Ubah semua segmen audio menjadi 3 detik.
   * Ekstrak 40-koefisien MFCC → dirata-rata.

4. **Encode Label:**

   * Gunakan `LabelEncoder` + one-hot encoding.

5. **Latih Model CNN:**

   * Arsitektur: Dense → Conv1D → MaxPooling → GAP → Dense Softmax
   * Optimizer: Adam, Loss: categorical\_crossentropy

6. **Evaluasi:**

   * Tampilkan akurasi, precision, F1 score, dan confusion matrix.

---

## 📊 Output

* Grafik akurasi dan loss tiap epoch.
* Confusion matrix hasil prediksi.
* Model terbaik disimpan dalam file `best_model.h5`.

---

## 🧪 Hasil Evaluasi

```text
--- Model Performance Metrics ---
Accuracy: 87.55%
Precision (Weighted): 0.88
F1 Score (Weighted): 0.88
```

---

## 🧠 Catatan

* Semua file `.wav` dan `.txt` berada di dalam satu folder sebelum diproses.
* File segmentasi akan dipotong otomatis menggunakan waktu dari `.txt`.
* Disarankan menggunakan Google Colab untuk menghindari masalah kompatibilitas dan untuk GPU support.

---

## 📜 Lisensi

MIT License

---

## 🤝 Kontribusi

Pull request sangat terbuka! Untuk perubahan besar, silakan buka *issue* terlebih dahulu.

---

## 🙌 Terima Kasih

Proyek ini terinspirasi oleh kompetisi pengenalan suara medis dan kontribusi komunitas AI di Indonesia.



---

### 🔧 `requirements.txt` (jika diperlukan)

```txt
tensorflow==2.18.0
scikit-learn==1.6.1
seaborn==0.13.2
matplotlib==3.10.0
numpy==2.0.2
librosa==0.11.0
pandas==2.2.2
kagglehub==0.3.12
````

---

Jika kamu ingin file `README.md` dan `requirements.txt` disiapkan langsung dalam format file yang bisa diunduh, tinggal beri tahu.
