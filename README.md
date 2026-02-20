# Penentuan Keanggotaan Gugus Bintang NGC 7790 dengan Machine Learning 

## Deskripsi Proyek
Proyek ini mengimplementasikan dan membandingkan algoritma *machine learning* untuk menentukan keanggotaan gugus bintang terbuka NGC 7790 menggunakan data astrometri presisi tinggi dari Gaia DR3. Karena pengamatan astronomi sering kali mencakup bintang latar (*field stars*) yang tidak berasosiasi secara fisik, pendekatan *machine learning* digunakan untuk memisahkan anggota gugus secara efisien berdasarkan parameter posisi, paralaks, dan gerak diri (*proper motion*) bintang.

## Metode yang Digunakan
Proyek ini mengevaluasi kinerja pendekatan *supervised* dan *unsupervised learning*:
- **Supervised Learning**: Random Forest dan Support Vector Machine (SVM). Dilatih menggunakan dataset transfer learning berlabel dari NGC 1624 yang memiliki karakteristik serupa.
- **Unsupervised Learning**: K-Means dan HDBSCAN.

Berdasarkan analisis, **HDBSCAN** terbukti menjadi metode yang paling optimal untuk mengidentifikasi keanggotaan gugus bintang tanpa ketergantungan pada data berlabel. Metode ini sangat sesuai untuk data astronomi karena kemampuannya mendeteksi klaster berbasis kepadatan dan ketahanannya terhadap *noise*.

## Struktur File
- `laporan.pdf`: Laporan lengkap penelitian yang mencakup tinjauan pustaka, metodologi, hasil evaluasi *confussion matrix*, dan analisis.
- `main-notebook.ipynb`: *Jupyter Notebook* yang memuat kode *preprocessing* data, pemodelan, serta evaluasi hasil algoritma.
- `data_ngc7790-7788`: Data sumber mentah dan olahan yang digunakan dalam perhitungan klasterisasi.
- `data_star-cluster-problabeled.csv`: Dataset berlabel yang digunakan sebagai *training data* untuk melatih algoritma *supervised learning* (Random Forest dan SVM) dalam mengenali pola anggota gugus bintang.

## Hasil Utama
- **Random Forest**: Berhasil mengidentifikasi 84 anggota gugus dan 327 *field stars*.
- **SVM**: Berhasil mengidentifikasi 127 anggota gugus dan 290 *field stars*.
- **K-Means**: Berhasil memisahkan klaster menjadi 3 bagian yang merepresentasikan NGC 7790, NGC 7788, dan bintang latar.
- **HDBSCAN**: Secara otomatis mengidentifikasi wilayah pusat gugus yang padat sesuai dengan posisi NGC 7790 pada katalog astronomi.

## Penulis
- Ulivia Embun Tresna Wardani 
- Fatiha Izza Tunisa 
- Luthfiana Sutarjo 

*Institut Teknologi Bandung, Fakultas Matematika dan Ilmu Pengetahuan Alam (2025)*
