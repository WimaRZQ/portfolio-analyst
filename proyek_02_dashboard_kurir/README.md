# Dashboard Performa Kurir per Zona

## Latar

Hub last-mile dengan 55 kurir (12 dedicated, 43 mitra) di 8 zona membutuhkan
pantauan harian: berapa paket ter-pickup, terkirim, masih jalan, dan gagal —
per zona dan per kurir — agar masalah terdeteksi sebelum jadi klaim.

Laporan ini dibangun dari data shipment mentah harian yang diolah menjadi
laporan hourly (Excel + visual) yang dibagikan ke grup operasional 3x sehari.

## Pertanyaan

1. Zona mana yang performanya paling rendah hari ini, dan kenapa?
2. Kurir mana yang jauh di bawah rata-rata (butuh coaching / redistribusi)?
3. Berapa beban ongoing yang dibawa ke shift berikutnya?

## Temuan (snapshot 8 Okt 2026, 18.682 shipment roster, data s/d ~14:23 WIB)

| Zona | Pickup | Delivered | Ongoing | Failed |
|------|-------:|----------:|--------:|-------:|
| CINERE | 3.460 | 3.022 | 429 | 9 |
| GANDUL | 1.865 | 1.615 | 250 | 0 |
| Grogol | 3.506 | 3.028 | 467 | 11 |
| Krukut | 2.306 | 1.953 | 345 | 8 |
| Limo | 1.694 | 1.451 | 237 | 6 |
| Meruyung | 2.215 | 1.903 | 304 | 8 |
| Pangkalan Jati Baru | 1.803 | 1.485 | 317 | 1 |
| Pangkalan Jati Lama | 1.833 | 1.567 | 266 | 0 |

- 9 kurir berstatus OFF (tanpa pickup) pada snapshot ini.
- Tidak ada zona dengan failed di atas 11; tidak ada kurir dengan failed di
  atas 5 pada snapshot ini.
- Paket aging (OFD sudah ganti hari & belum delivered): **0** — semua paket
  hari sebelumnya sudah clear.

> TODO (sesi 9 Okt): pilih visual (heatmap zona / bar chart per kurir),
> tambah tren harian kalau data multi-hari dipakai, tulis insight + action plan.

## Data

`../data/report_08okt2026_anonim.csv` (kolom terpilih, ID anonim) +
`../data/roster_kurir_anonim.csv` (`Driver_ID` → `Zone`, `Tipe`).
