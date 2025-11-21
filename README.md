# Kelompok_10_Machine_Learning

# Optimasi Prediksi Diagnosis Kanker Payudara Berbasis Biomarker Metabolik

### Penerapan Support Vector Machine (SVM) dengan Bayesian Optimization

Proyek ini bertujuan untuk membangun dan mengoptimalkan model *machine learning* untuk **prediksi diagnosis kanker payudara** menggunakan dataset *Breast Cancer Coimbra* (BCCD). Penelitian ini berfokus pada peningkatan efisiensi dan stabilitas model **Support Vector Machine (SVM)** menggunakan teknik optimasi hiperparameter otomatis **Bayesian Optimization (Optuna)**, sebagai pengembangan dari metode konvensional (*Grid Search*).

## Struktur Proyek

```bash
├── PaperJournal/      # Naskah akhir proyek (IMRAD) dalam format .docx dan .pdf
├── Proposal/          # Dokumen proposal revisi (Metode SVM + Bayesian Opt)
├── SourceCode/        # Notebook Jupyter (01_EDA, 02_Modeling_Optuna, 03_Evaluation)
├── Dataset/           # Dataset Breast Cancer Coimbra (.csv)
└── README.md          # Dokumentasi lengkap proyek
```

## Deskripsi Dataset

  * **Sumber:** [UCI Machine Learning Repository - Breast Cancer Coimbra Data Set](https://archive.ics.uci.edu/dataset/451/breast+cancer+coimbra)
  * **Jumlah Sampel:** 116 pasien (setelah eksklusi BMI \> 40 kg/m²)
  * **Jumlah Fitur:** 9 atribut biomarker metabolik + 1 Target
  * **Target:** Klasifikasi (1 = Sehat, 2 = Kanker Payudara)

**Fitur Utama (Biomarker):**

  * **Glucose** (Kadar Glukosa)
  * **Resistin** (Protein Resistin)
  * **Age** (Usia)
  * **BMI** (Indeks Massa Tubuh)
  * Fitur lainnya: Insulin, HOMA, Leptin, Adiponectin, MCP-1

## Metodologi

### 1\. Preprocessing

  * **Data Cleaning:** Eksklusi pasien dengan BMI \> 40 kg/m² (sesuai protokol medis Patrício et al., 2018).
  * **Encoding:** Mengubah label target menjadi biner (0/1).
  * **Normalisasi:** Menggunakan `StandardScaler` untuk menyamakan skala fitur numerik.
  * **Splitting:** Penerapan *Repeated Random Sub-sampling* untuk validasi.

### 2\. Modeling & Optimization

  * **Algoritma:** Support Vector Machine (Kernel RBF).
  * **Teknik Optimasi:** **Bayesian Optimization** menggunakan library `Optuna` (Tree-structured Parzen Estimator).
  * **Tujuan:** Mencari parameter terbaik ($C$ dan $\gamma$) secara otomatis dan efisien.

### 3\. Evaluasi & Visualisasi

  * **Metrik:** ROC-AUC, Akurasi, Sensitivitas, Spesifisitas.
  * **Uji Stabilitas (Robustness):** Pengujian berulang (20 iterasi) untuk mengukur konsistensi model.
  * **Visualisasi:**
      * ROC Curve (Robustness 20 Iterasi)
      * Confusion Matrix

## Hasil Utama

  * **Kinerja Model:** Model berhasil mencapai rata-rata **AUC 0.87** dan **Akurasi \~81%**.
  * **Stabilitas:** Grafik *Robustness* menunjukkan standar deviasi yang rendah ($\pm 0.06$), menandakan model sangat stabil terhadap variasi data.
  * **Efisiensi:** Metode *Bayesian Optimization* terbukti mampu menemukan parameter optimal lebih efisien dibandingkan metode *Grid Search* konvensional.

## Penulis

  * **Azmi Ittaqi Hammami** (241572010007)
  * **Shifi Amalia Zein** (241552010013)

## Institusi

**Sekolah Tinggi Manajemen Informatika dan Komputer Tazkia**
Program Studi Teknik Informatika dan Sistem Informasi
Mata Kuliah: Statistik dan Probabilitas / Data Mining (Sesuaikan)
Semester Genap – Tahun Akademik 2024/2025

**Dosen Pengampu:**
Bapak Hendri Kharisma, S.Kom., M.T.

## Lisensi & Referensi

  * **Dataset:** Creative Commons CC BY 4.0 (UCI Repository)
  * **Referensi Utama:** Patrício, M. et al. (2018). *BMC Cancer*.



*Proyek ini dibuat sebagai bagian dari Tugas Besar / UTS untuk mata kuliah Machine Learning yang diampu oleh Bapak Hendri Kharisma, S.Kom., M.T.*
>>>>>>> e614413 (UTS)
