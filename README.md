# Estimasi Tingkat Pengaruh Penggunaan Music Streaming terhadap Produktivitas Belajar Mahasiswa Program Studi Statistika Universitas Mataram Menggunakan Two-Stage Cluster Sampling

Project UAS Mata Kuliah Metode Sampling — Program Studi Statistika, Universitas Mataram.

> ⚠️ **Status: Draft (Work in Progress)**
> Pengumpulan data masih berjalan. Hasil pada dokumen ini bersifat preliminary dan akan diperbarui seiring bertambahnya respon.

---

## 1. Latar Belakang

Musik dan platform *music streaming* (Spotify, Joox, dll) menjadi bagian dari kebiasaan belajar mahasiswa sehari-hari. Penelitian ini ingin mengestimasi **seberapa tinggi tingkat pengaruh** penggunaan music streaming terhadap produktivitas belajar mahasiswa Program Studi Statistika Universitas Mataram, menggunakan pendekatan survei sampling.

## 2. Tujuan

Mengestimasi tingkat (kategori Rendah/Sedang/Tinggi) pengaruh penggunaan music streaming terhadap produktivitas belajar mahasiswa Statistika Unram, beserta ukuran presisi estimasinya (SE, Design Effect, RSE).

## 3. Populasi dan Desain Sampling

- **Populasi (N):** 154 mahasiswa aktif Program Studi Statistika Unram, angkatan 2023–2025
  - 2023: 37 mahasiswa
  - 2024: 54 mahasiswa
  - 2025: 63 mahasiswa
- **Desain:** Two-Stage Cluster Sampling
  - **Tahap 1 (Kelas/Cluster):** unit cluster adalah angkatan. Karena hanya tersedia 3 cluster alami di prodi ini (tidak ada kelas paralel A/B), ketiga cluster diambil seluruhnya.
  - **Tahap 2 (Mahasiswa):** dari setiap cluster, ditarik sampel mahasiswa secara Simple Random Sampling (SRS) proporsional terhadap ukuran cluster.
- **Ukuran sampel (n):** 61, dihitung dengan rumus Slovin (margin of error 10%)
  - 2023: 15 | 2024: 21 | 2025: 25
- **Daftar cadangan** disiapkan untuk menggantikan responden yang non-respon, agar proporsi tiap angkatan tetap terjaga.

## 4. Instrumen

Kuesioner terdiri dari 15 item, dibagi menjadi:
- **Bagian A** — Data diri & screening (nama, jenis kelamin, angkatan, status aktif)
- **Bagian B** — Karakteristik penggunaan (platform, durasi, genre musik)
- **Bagian C** — Persepsi pengaruh terhadap produktivitas belajar (6 item skala Likert 1–5), termasuk 1 item negatif yang di-*reverse code* sebelum dihitung sebagai indeks komposit
- **Bagian D** — Pertanyaan terbuka (opsional)

## 5. Metode Estimasi

Karena Tahap 1 mengambil seluruh cluster (peluang inklusi cluster = 1), variasi sampling hanya bersumber dari Tahap 2. Estimator rata-rata populasi dihitung sebagai **rata-rata terbobot (weighted mean)**, dengan bobot dasar:

```
w_h = N_h / n_h
```

di mana `N_h` adalah jumlah populasi pada angkatan h, dan `n_h` jumlah responden pada angkatan h.

## 6. Metode Analisis

- Menghitung indeks komposit per responden (rata-rata 6 item skala Likert, setelah reverse-coding item negatif)
- Menghitung rata-rata terbobot indeks komposit di level populasi
- Menghitung Standard Error (SE) dan Relative Standard Error (RSE), dengan syarat kelayakan rilis RSE < 25%
- Menghitung Design Effect (Deff) untuk membandingkan efisiensi desain terhadap SRS murni
- Kategorisasi tingkat pengaruh menggunakan interval kelas (skala 1–5, 3 kategori):

| Kategori | Rentang Skor |
|---|---|
| Rendah | 1,00 – 2,33 |
| Sedang | 2,34 – 3,67 |
| Tinggi | 3,68 – 5,00 |

## 7. Hasil Sementara (Preliminary)

*Berdasarkan 23 responden valid dari target 61 sampel (data masih berjalan, per 2 Juli 2026).*

| Angkatan | n (respon) | N (populasi) | Rata-rata komposit |
|---|---|---|---|
| 2023 | 3 | 37 | 3,67 |
| 2024 | 12 | 54 | 3,39 |
| 2025 | 8 | 63 | 3,85 |

- **Rata-rata terbobot populasi:** 3,65 (skala 1–5)
- **Kategori tingkat pengaruh:** **Sedang**
- **RSE:** 3,37% (memenuhi syarat layak rilis, namun perlu diinterpretasikan hati-hati karena n per stratum masih kecil)

## 8. Kendala Lapangan

- Beberapa responden pada daftar sampel utama tidak bersedia mengisi (non-respon), penggantian dari daftar cadangan masih berjalan.
- Response rate lebih tinggi melalui pendekatan personal (chat langsung) dibanding broadcast grup.

## 9. Rencana Selanjutnya

- Melanjutkan pengumpulan data hingga mendekati target n=61
- Menghitung ulang bobot dengan koreksi non-respon final
- Membandingkan hasil estimasi, SE, dan Deff antara pendekatan SRS murni vs desain cluster/stratified yang digunakan
- Menyusun laporan akhir dengan Executive Summary

---

*Repositori ini merupakan draft untuk keperluan penilaian UAS Mata Kuliah Metode Sampling, Program Studi Statistika, Universitas Mataram.*
*_Author : Abyan Arkan Maulana (G1F02410013)_
