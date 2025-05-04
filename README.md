
# Program Analisis Sentimen Komentar YouTube tentang Pak Jokowi

## Tujuan
Program ini bertujuan untuk menganalisis sentimen dari komentar-komentar di YouTube terkait Pak Jokowi menggunakan teknik pemrosesan bahasa alami (Natural Language Processing/NLP).

## Langkah-langkah Utama

### 1. Instalasi Library
- Menginstal library yang diperlukan seperti:
  - `Sastrawi` untuk stemming bahasa Indonesia
  - `VADER` untuk analisis sentimen
  - `NLTK` untuk preprocessing teks

### 2. Pengambilan Data
- Mengambil dataset komentar YouTube dari file `.csv`
- Menampilkan data mentah untuk eksplorasi awal

### 3. Pra-pemrosesan Data
- Mengganti emoji dengan kata-kata representatif
- Menghapus:
  - URL
  - Karakter khusus
  - Angka
- Mengubah teks menjadi huruf kecil
- Menghapus stopwords
- Melakukan stemming kata-kata ke bentuk dasar

### 4. Analisis Sentimen
- Menggunakan `VADER` untuk analisis sentimen komentar yang telah diproses
- Menghitung skor sentimen:
  - Positif
  - Negatif
  - Netral
  - Skor komposit (compound)

### 5. Pelatihan Model
- Melatih model klasifikasi sentimen menggunakan algoritma **Naive Bayes**
- Menggunakan fitur dari **TF-IDF Vectorizer**
- Mengukur akurasi model

### 6. Visualisasi
- Memvisualisasikan distribusi sentimen komentar menggunakan grafik batang untuk memberikan pemahaman visual

## Hasil
Program ini memberikan:
- Wawasan tentang sentimen umum masyarakat terhadap Pak Jokowi berdasarkan komentar YouTube
- Nilai akurasi dari model klasifikasi sentimen yang digunakan
