# Visualisasi Data dengan Matplotlib

Lanjutan Tugas 6. Memakai data transaksi POS yang sama (`paket_a_transaksi_pos_2024_2025.csv`) dan memvisualisasikan **tahun 2025** dalam **satu grid 2×2**.

## Isi folder

```
├── Tugas_Visualisasi_Matplotlib.ipynb   # notebook utama (penjelasan + insight di bawah tiap sel)
├── hasil/
│   └── visualisasi_grid_2x2.png         # grid 2x2 (4 chart)
└── Readme.md
```

Dataset dibaca dari `../Tugas_5/data/` (tidak disalin ulang). Jalankan notebook dari folder `Tugas_7/`.

## Tata letak grid 2×2

| | Kolom kiri | Kolom kanan |
|---|---|---|
| **Baris atas** | Bagian 1: penjualan per bulan (garis) | Bagian 2: 10 produk terlaris (batang) |
| **Baris bawah** | Bagian 3: proporsi status transaksi (pie) | Bagian 4: jumlah beli vs diskon (scatter + jitter) |

## Temuan utama (dari output notebook)

| Bagian | Temuan |
|---|---|
| 1 | Total 2025 ± Rp 151,5 juta. Tertinggi Maret (16,2 juta), terendah April (10,9 juta). Tidak ada tren naik/turun tegas. |
| 2 | RMT1408 teratas (141 unit). Top 10 menyumbang 20,7% unit, tetapi tidak ada satu produk yang dominan (produk teratas 2,3%). |
| 3 | SELESAI 2.365 (94,5%), BATAL 88 (3,5%), RETUR 49 (2,0%). |
| 4 | Rata-rata jumlah 2,59 (diskon 0%) sampai 2,40 (diskon 20%). Spearman ρ = −0,013, rentang 95% rata-rata saling tumpang tindih. |

Insight lengkap per chart ada di bagian **Insight** pada akhir notebook.

## Catatan penanganan data

- Pembersihan mengikuti Tugas 6: format harga dirapikan, `jumlah` negatif diubah ke nilai mutlak, `kode_kasir` kosong diisi `K_UNKNOWN`.
- **Berbeda dari Tugas 6:** duplikat dibuang dan `jumlah` > 12 dibuang (salah input, mis. 2.375 unit) supaya grafik tidak terdistorsi. Batas 12 mengikuti Tugas 5. Akibatnya angka bisa berbeda dari Tugas 6.
- Penjualan = `Total_Bersih` (setelah diskon, termasuk PPN 11%, sama seperti Tugas 6), hanya status `SELESAI`. Karena itu angkanya lebih besar daripada Tugas 5 yang tanpa PPN.
- "Terlaris" diukur dari total unit terjual, bukan omzet.
- Bagian 4: jitter hanya untuk tampilan. Rata-rata dan korelasi dihitung dari data asli.

## Batasan

Hubungan jumlah beli dan diskon bersifat asosiatif (data observasional), tidak membuktikan sebab-akibat. Kenaikan Desember belum bisa disebut pola musiman karena hanya satu tahun yang dilihat. Selisih peringkat di Bagian 2 kecil sehingga urutan bisa berubah jika data atau aturan pembersihan berubah.

## Cara menjalankan

```bash
pip install pandas matplotlib jupyter
jupyter notebook Tugas_Visualisasi_Matplotlib.ipynb
```
