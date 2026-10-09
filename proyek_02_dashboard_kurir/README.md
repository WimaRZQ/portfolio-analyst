# Portofolio Analisis Data — Wima Rizqullah

Dua proyek portofolio berbasis data operasional last-mile nyata (hub Cinere),
dibangun dari pengalaman kerja sebagai Last Mile Logistic Officer.

> **Catatan privasi:** semua data di repo ini sudah dianonimkan — nomor resi
> asli diganti ID acak (`PKG-XXXXXX`) dan nama kurir diganti `DRV_XX`.
> Detail metode: lihat [`ANONIMISASI.md`](./ANONIMISASI.md).

## Proyek

| # | Proyek | Data | Status |
|---|--------|------|--------|
| 01 | [Studi Kasus: Paket Beralamat Kode & Risiko COD](./proyek_01_paket_kode/) | 874 paket kode — 81 (5 Agus) + 593 (10 Agus) + 30 (8 Sept) + 9 (28 Sept) + 161 (5 Okt) | Selesai 9 Okt — PDF 8 halaman di goal analyst-pivot-career-prep |
| 02 | [Dashboard Performa Kurir per Zona](./proyek_02_dashboard_kurir/) | 18.682 shipment, 55 kurir, 8 zona (8 Okt 2026) | Draft — bangun visual 9 Okt |

## Tools

Python (pandas, openpyxl), SQL (latihan via SQLite), Excel (COUNTIFS/VLOOKUP/rumus).
Dashboard bisa direbuild di Excel atau Python — data anonim siap di `data/`.

## Struktur

```
portfolio_analyst/
├── data/                        # dataset anonim (publik)
│   ├── report_08okt2026_anonim.csv
│   ├── boman_mask_05agustus_anonim.csv
│   ├── boman_mask_10agustus_anonim.csv
│   ├── boman_mask_08september_anonim.csv
│   ├── boman_mask_28september_anonim.csv
│   ├── boman_mask_05oktober_anonim.csv
│   ├── roster_kurir_anonim.csv  # Driver_ID -> Zona, Tipe
│   └── statistik_ringkas.json
├── private/                     # LOKAL SAJA — jangan di-push
├── proyek_01_paket_kode/
└── proyek_02_dashboard_kurir/
```
