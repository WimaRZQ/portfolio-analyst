# Studi Kasus: Paket Beralamat Kode & Risiko COD

## Latar

Sebagian seller e-commerce mengirim paket dengan **alamat tujuan berupa kode**
(contoh: "BLOK MA", "BLOK SK"), bukan alamat jalan asli. Kode ini hanya
dikenali oleh pihak internal — kurir yang tidak hafal daerahnya berisiko
salah antar (misroute), paket gagal terkirim berulang, dan nilai COD yang
dibawa kurir ikut berisiko.

Di hub ini, pola alamat kode teridentifikasi pada seller dengan volume tinggi:
paket dikumpulkan di runsheet admin lalu dialokasikan ke kurir — dalam satu
kasus, **151 paket dialokasikan ke satu kurir sekaligus**.

## Pertanyaan

1. Seberapa besar nilai COD yang berisiko pada batch paket beralamat kode?
2. Bagaimana pola misroute terjadi pada paket-paket ini?
3. Rekomendasi operasional apa yang mengurangi risiko failed & COD macet?

## Temuan (terverifikasi dari data)

| Batch | Paket | Total COD (Rp) |
|-------|------:|---------------:|
| 5 Agustus 2026 | 81 | 25.029.621 |
| 10 Agustus 2026 | 593 | 80.302.609 |
| 8 September 2026 | 30 | 4.254.525 |
| 28 September 2026 | 9 | 9.470.314 |
| 5 Oktober 2026 | 161 | 21.833.151 |
| **Total 5 batch** | **874** | **140.890.220** |

- Identifikasi paket kode: 100% paket seller terkait (non-cancel) memakai pola
  alamat kode — terkonfirmasi dari pencocokan manual dengan info CS.
- Data report 8 Okt 2026: 51 paket seller terkait terdeteksi, 47 sudah
  delivered, 4 masih out-for-delivery.
- Contoh misroute: paket tujuan Limo/Meruyung ter-assign ke kurir zona Grogol.

> TODO (sesi 9 Okt): breakdown status per batch, analisis pola misroute per
> zona, hitung estimasi COD tertahan, tulis rekomendasi operasional.

## Rekomendasi

> TODO (sesi 9 Okt): ditulis bareng — kandidat: daftar pemetaan kode → titik
> antar aktual, assign ke kurir zona yang hafal daerah, checklist verifikasi
> sebelum alokasi massal.

## Data

`../data/boman_mask_05agustus_anonim.csv`, `../data/boman_mask_10agustus_anonim.csv`,
`../data/boman_mask_08september_anonim.csv`, `../data/boman_mask_28september_anonim.csv`,
`../data/boman_mask_05oktober_anonim.csv` — kolom: `Package_ID`, `COD_amount`.
