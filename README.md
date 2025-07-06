# Dokumentasi Singkat Ekstraksi Fitur Gambar Buah

## Deskripsi Data
Dataset terdiri dari gambar buah-buahan (apel, alpukat, mangga, jeruk, semangka) yang tersimpan dalam subfolder berbeda di direktori `gambar_buah/`. Setiap subfolder mewakili satu kategori buah. Gambar diambil dari berbagai kondisi pencahayaan dan posisi.

## Langkah Feature Engineering (FE)

### Ekstraksi Histogram RGB
- Setiap gambar dikonversi ke RGB.
- Histogram tiap channel (R, G, B) dihitung (32 bin per channel).
- Histogram digabung dan dinormalisasi.
- Hasil akhir: vektor fitur histogram RGB per gambar.

### Ekstraksi HOG (Histogram of Oriented Gradients)
- Gambar dikonversi ke grayscale.
- Fitur HOG diekstrak dengan parameter: 9 orientasi, 8x8 pixels per cell, 2x2 cells per block.
- Hasil akhir: vektor fitur HOG per gambar.

### Penyimpanan Fitur
- Fitur histogram dan HOG disimpan ke file CSV (`fitur_histogram.csv`, `fitur_hog.csv`).

## Insight

### Distribusi Data
- Setiap kategori buah memiliki jumlah gambar yang seimbang, memudahkan analisis dan pelatihan model klasifikasi.

### Karakteristik Histogram RGB
- Histogram RGB tiap kategori menunjukkan pola warna dominan berbeda, misal apel cenderung memiliki puncak pada channel merah.

### Ciri Tekstur dari HOG
- Fitur HOG mampu menangkap pola garis dan tekstur khas pada masing-masing buah, membantu membedakan antar kategori.

### Potensi Klasifikasi
- Kombinasi fitur warna (histogram) dan tekstur (HOG) dapat digunakan untuk membangun model klasifikasi buah secara otomatis.

### Visualisasi
- Visualisasi histogram dan HOG memperlihatkan perbedaan signifikan antar kategori, baik dari sisi warna maupun tekstur.
