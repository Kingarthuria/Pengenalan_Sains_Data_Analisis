# Analisis Pendapatan Per Tahun (2024 dan 2025)

Notebook Python sederhana untuk menghitung pendapatan per tahun dari data transaksi POS.

## Hasil

| Tahun | Pendapatan |
|---|---:|
| 2024 | Rp 127.406.475 |
| 2025 | Rp 135.001.100 |

## Aturan perhitungan

- Hanya transaksi berstatus `SELESAI` yang dihitung. `BATAL` dan `RETUR` tidak dihitung.
- Rumus: `jumlah × harga_satuan × (1 − diskon_persen / 100)`.
- Jumlah harus 1 sampai 12. Jumlah negatif dan angka sangat besar dianggap salah input.
- Duplikat dihapus.
- Missing value hanya ada di `kode_kasir` (261 baris), diisi `TIDAK_DIKETAHUI`.

## Isi repo

```
├── analisis_pendapatan_pos.ipynb   # notebook utama
├── data/
│   └── paket_a_transaksi_pos_2024_2025.csv
├── hasil/
│   ├── pendapatan_per_tahun.csv
│   └── pendapatan_per_tahun.png
├── requirements.txt
└── README.md
```

## Cara menjalankan

```bash
pip install -r requirements.txt
jupyter notebook analisis_pendapatan_pos.ipynb
```

Jalankan Jupyter dari folder root repo ini agar path `data/` dan `hasil/` terbaca.
