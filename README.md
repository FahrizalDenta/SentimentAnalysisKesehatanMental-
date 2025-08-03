# SentimentAnalysisKesehatanMental

# 🧠 Menggali Insight Kesehatan Mental Remaja Pendekatan AI dengan IBM Granite Model

## 📌 Project Overview

Proyek Capstone ini bertujuan untuk menganalisis dan mengklasifikasikan status kesehatan mental remaja Indonesia berdasarkan pernyataan teks publik. Masalah ini krusial karena analisis manual terhadap data teks berskala besar tidak efisien dan rentan kesalahan, sehingga menunda insight penting dalam konteks kesehatan mental remaja.

---

## 📊 Dataset

- **Jumlah data:** 53.043 pernyataan berbahasa Inggris
- **Fitur utama:**  
  - `statement`: teks pernyataan  
  - `status`: label (Normal, Depression, Suicidal, Anxiety, Stress, Bipolar, Personality Disorder)
- **Sumber Dataset:** [🔗 https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health]
- **Distribusi Label:**  
  - `Normal`: 16.351  
  - `Depression`: 15.404  
  - `Stress`: 2.669  
  - `Personality Disorder`: 1.201  
  (Dataset sangat tidak seimbang)

---

## 🧪 Metodologi

### Tools & Teknologi:
- **Google Colab**: untuk coding & runtime
- **Python (Pandas, Matplotlib, NLTK)**: eksplorasi & preprocessing
- **Replicate API + IBM Granite LLM**: untuk klasifikasi berbasis AI

### Alur Analisis:
1. **Persiapan Lingkungan:** Instalasi library & verifikasi GPU T4
2. **Memuat Dataset & EDA:** Identifikasi struktur dan distribusi data
3. **Preprocessing:** Pembersihan teks, normalisasi
4. **Integrasi Granite Model:** via Replicate API (`ibm-granite/granite-3.3-8b-instruct`)
5. **Prompt Engineering (Few-Shot):** Menyusun 20 contoh dan instruksi klasifikasi
6. **Evaluasi Performa:** Menggunakan akurasi, F1-score, dan confusion matrix

---

## 🤖 AI Support Explanation

Model **IBM Granite** digunakan sebagai **Large Language Model (LLM)** untuk klasifikasi teks multi-kelas. Proses ini melibatkan:
- **Prompt Engineering:** Model menerima teks pernyataan dan mengklasifikasikannya ke dalam 7 kategori berdasarkan 20 contoh yang diberikan (Few-Shot Learning).
- **Kelebihan:** Efisien untuk ribuan data, tidak perlu training dari nol.
- **Manfaat:** Mempercepat proses klasifikasi dan memungkinkan insight mendalam terhadap ekspresi emosi pengguna.

---

## 📈 Hasil & Insight Utama

### 🎯 Akurasi Model:
- **Akurasi keseluruhan:** 65%
- **F1-score tertinggi:**  
  - `Normal` (F1: 0.85)  
  - `Bipolar` (F1: 0.69)  
  - `Suicidal` (F1: 0.66)  
- **F1-score terendah:**  
  - `Personality Disorder` (F1: 0.22)  
  - `Stress` (F1: 0.29)

### 🔍 Insight:
- Model sering bingung antara label yang mirip, seperti `Anxiety` vs `Depression`.
- Prompt Engineering sangat membantu dalam klasifikasi minoritas, meski tidak sempurna karena imbalance.

---

## 💡 Rekomendasi

1. **Pengembangan Alat Skrining AI:**
   - Fokus pada deteksi `Depression`, `Suicidal`, dan `Bipolar`.
   - Untuk intervensi dini dan deteksi risiko.

2. **Peningkatan Akurasi Jangka Panjang:**
   - Lakukan fine-tuning LLM dengan dataset yang lebih seimbang.
   - Targetkan akurasi >80% untuk aplikasi nyata.

---

## 🧠 Pembelajaran Kunci

- **Prompt Engineering efektif** untuk klasifikasi cepat tanpa pelatihan model tambahan.
- **LLM memiliki batasan** dalam klasifikasi data yang sangat tidak seimbang.
- **Manual labeling dan fine-tuning** tetap dibutuhkan jika ingin performa optimal.

---

## 🚀 Cara Menjalankan Proyek Ini

1. **Dapatkan API Token**  
   - Daftar di [Replicate.com](https://replicate.com)  
   - Simpan token dengan nama `api_token` di Google Colab Secrets (🔒 ikon kunci)

2. **Buka Notebook Google Colab**  
   - `ProjekHacktive8.ipynb`

3. **Atur Runtime**  
   - Runtime > Change runtime type > GPU (T4)

4. **Unggah Dataset**  
   - `Sentiment Analysis for Mental Health.csv` ke sesi Colab

5. **Jalankan Sel**  
   - Jalankan semua sel kode secara berurutan

---


