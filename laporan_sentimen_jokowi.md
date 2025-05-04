
# Laporan Proyek Machine Learning - Amelia Gizzela Sheehan Auni

## Project Overview

Komentar-komentar publik di media sosial, khususnya YouTube, sering mencerminkan opini masyarakat terhadap figur publik. Salah satu figur yang banyak dibicarakan adalah Presiden Joko Widodo (Jokowi). Analisis sentimen terhadap komentar tentang Pak Jokowi dapat memberikan gambaran persepsi publik terhadap kebijakan atau citranya di masyarakat. Proyek ini menggunakan pendekatan pemrosesan bahasa alami (Natural Language Processing) untuk menganalisis komentar-komentar tersebut.

**Mengapa penting?**
- Opini publik dapat mempengaruhi kepercayaan masyarakat terhadap pemerintah.
- Sentimen negatif atau positif dapat menjadi indikator isu yang sedang berkembang.

**Referensi**:
- Hutto, C.J., & Gilbert, E. (2014). *VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text*. [Proceedings of ICWSM].
- R. Feldman, *Techniques and Applications for Sentiment Analysis*, Communications of the ACM, vol. 56, no. 4, pp. 82-89, 2013.

## Business Understanding

### Problem Statements
1. Bagaimana persepsi publik terhadap Pak Jokowi berdasarkan komentar YouTube?
2. Seberapa akurat model machine learning dalam mengklasifikasikan sentimen komentar tersebut?

### Goals
1. Mengidentifikasi distribusi sentimen (positif, netral, negatif) terhadap Pak Jokowi di komentar YouTube.
2. Membangun dan mengevaluasi model klasifikasi sentimen yang andal.

### Solution Approach
- **Solution 1**: Analisis sentimen berbasis aturan menggunakan VADER Sentiment.
- **Solution 2**: Klasifikasi sentimen berbasis supervised learning menggunakan Naive Bayes dan TF-IDF.

## Data Understanding

Dataset yang digunakan berupa file `.csv` yang berisi komentar-komentar YouTube tentang Pak Jokowi. Jumlah data tidak disebutkan secara eksplisit dalam awal notebook, namun diproses dengan library `pandas`.

**Beberapa fitur dalam dataset:**
- `komentar`: berisi teks komentar dari pengguna.
- Tidak ada label awal (unsupervised), namun digunakan pendekatan labeling dari VADER untuk keperluan supervised model.

## Data Preparation

Langkah-langkah preprocessing yang dilakukan meliputi:
1. **Pembersihan Teks**:
   - Mengganti emoji dengan kata.
   - Menghapus URL, angka, dan karakter spesial.
   - Menurunkan huruf menjadi lowercase.

2. **Tokenisasi dan Stopword Removal**:
   - Tokenisasi menggunakan NLTK.
   - Stopword Bahasa Indonesia dihapus menggunakan daftar dari NLTK dan tambahan manual.

3. **Stemming**:
   - Menggunakan pustaka `Sastrawi` untuk stemming bahasa Indonesia.

4. **Labeling Sentimen**:
   - Sentimen dihitung menggunakan VADER (`compound` score) dan dikategorikan ke dalam `positif`, `netral`, dan `negatif`.

## Modeling

Model klasifikasi yang digunakan adalah **Multinomial Naive Bayes**.

- Fitur teks dikonversi menjadi vektor numerik menggunakan **TF-IDF Vectorizer**.
- Dataset dibagi menjadi data latih dan data uji menggunakan `train_test_split`.

## Evaluation

**Metrik yang digunakan**: *Accuracy*

Hasil evaluasi menunjukkan bahwa model Naive Bayes mampu mengklasifikasikan sentimen dengan **akurasi yang cukup baik**, sesuai dengan kompleksitas teks dan preprocessing yang dilakukan.

> Metrik akurasi dihitung menggunakan:
> \[
> \text{Accuracy} = \frac{\text{Jumlah Prediksi Benar}}{\text{Total Jumlah Data Uji}}
> \]

## Kesimpulan

Proyek ini berhasil mengidentifikasi dan mengklasifikasikan sentimen masyarakat terhadap Presiden Jokowi berdasarkan komentar YouTube. Dengan menggunakan pendekatan NLP dan model supervised learning, didapatkan akurasi yang dapat diterima untuk tugas klasifikasi teks dalam bahasa Indonesia.
