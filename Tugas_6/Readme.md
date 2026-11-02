# Manipulasi Data dengan Python Pandas

Notebook untuk tugas manipulasi data pada data transaksi POS 2024–2025 (Paket A): indexing & selection, operasi aritmatika, filtering, sorting, serta grouping & agregasi.

## Isi folder

```
├── Tugas_Manipulasi_Data_Pandas.ipynb   # notebook utama (Task 1–5)
├── paket_a_transaksi_pos_2024_2025.csv  # dataset
└── README.md
```

## Hasil utama

- Task 3.1: 140 transaksi `SELESAI` dari gerai G05/G09 dengan `Total_Bersih` > Rp 100.000.
- Task 3.2: 39 transaksi gerai G10 dengan jumlah minimal 5 unit.
- Task 5.1: G11 memiliki omzet bersih tertinggi (± Rp 125,6 juta).

## Catatan penanganan data

- `harga_satuan` memiliki tiga format: `13000`, `7500,00`, dan `13.000`. Format titik-ribuan ditangani lebih dulu agar tidak terbaca sebagai 13,0.
- Jumlah negatif diubah menjadi positif (`.abs()`) dan `kode_kasir` kosong diisi `K_UNKNOWN`, sesuai soal.
- Baris dengan `jumlah` tidak wajar (> 12) dan baris duplikat **tidak dibuang** pada Task 1–5 karena soal tidak memintanya. Dampaknya dianalisis terpisah di bagian "Catatan Tambahan" pada notebook.
- Karena itu angka di sini berbeda dengan `analisis-pendapatan-pos`, yang membuang outlier dan duplikat serta tidak memakai PPN. Tugas ini menghitung `Total_Bersih` dengan PPN 11%.

## Cara menjalankan

```bash
pip install pandas jupyter
jupyter notebook Tugas_Manipulasi_Data_Pandas.ipynb
```
