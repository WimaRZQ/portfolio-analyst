# BRIEF — Studi Kasus: Paket Beralamat Kode & Risiko COD

## Konteks bisnis
Seller memasukkan paket dengan alamat berkode (kode MA/SK) — format alamat tidak
standar sehingga berisiko salah antar dan gagal bayar COD. Penulis (Last Mile
Logistic Officer, hub Cinere) menyusun rekap per batch untuk invoice/settlement
COD ke seller. Studi ini menganalisis 5 batch (Agu–Okt 2026).

## Data (sudah dianonimkan — no resi asli, no nama kurir asli)
- 874 paket, total COD Rp140.890.220, 5 batch
- Kolom: Batch, Package_ID (anonim), Driver_ID (anonim), Shipment_Status,
  OFD_Time, Buyer_District, COD_Amount
- Batch 5 Okt 2026 di-join dengan report harian untuk outcome aktual per 8 Okt

## Temuan kunci (angka final, terverifikasi)
1. **Eksposur COD Rp140,89 jt dari 874 paket** (5 batch, Agu–Okt 2026).
   Rata-rata Rp161.202/paket, median Rp136.912/paket.
2. **Batch 10 Agustus dominan**: 593 paket (67,9%), COD Rp80,30 jt (57,0%).
3. **Batch 28 September kecil tapi bernilai tinggi**: hanya 9 paket, COD Rp9,47 jt
   — rata-rata Rp1.052.257/paket (±7,7x rata-rata keseluruhan). Konsentrasi risiko.
4. **Konsentrasi geografis ekstrem**: 843 dari 874 paket (96,5%) bertujuan ke
   Kecamatan Limo. Pancoran Mas 28, Cinere 2, Beji 1.
5. **Outcome batch 5 Okt 2026 (live tracking)**: 161 paket, COD Rp21,83 jt —
   **100% delivered dalam 3 hari** (per 8 Okt 2026). Collection rate 100%.
6. **Anomali**: 1 paket bernilai COD Rp0; 1 paket bernilai Rp1.332.660 (tertinggi).
   Top-10 paket = 7,5% dari total nilai.

## Insight
- Pola batch tidak merata: batch besar (10 Agu) vs batch kecil bernilai tinggi
  (28 Sep) butuh perlakuan monitoring berbeda.
- Konsentrasi 96,5% di satu kecamatan = rute padat, efisien untuk dedicated run,
  tapi single-point-of-failure bila ada gangguan area.
- Rekap per batch + join ke report harian memungkinkan settlement COD
  terverifikasi (bukti 100% collection batch 5 Okt).

## Rekomendasi
1. **Prioritaskan batch bernilai tinggi** (seperti 28 Sep): eskalasi same-day
   follow-up untuk paket COD >Rp500 rb.
2. **Rute khusus Limo** untuk paket kode: mengingat 96,5% konsentrasi, dedicated
   run mengurangi risiko salah antar alamat berkode.
3. **Checklist anomali pra-invoice**: tandai otomatis paket COD Rp0 dan outlier
   >3x median sebelum invoice dikirim ke seller.
4. **Rekonsiliasi rutin**: join rekap batch vs report harian (seperti metode studi
   ini) sebagai SOP settlement, bukan manual cek satu-satu.

## Chart (di folder ini, embed ke PDF)
- chart_01_tren_batch.png — tren volume vs nilai COD per batch
- chart_02_distribusi_cod.png — distribusi COD per paket + garis median
- chart_03_distrik.png — konsentrasi kecamatan tujuan
- chart_04_outcome_okt.png — outcome 100% delivered batch 5 Okt

## Atribusi
Penulis: Wima Rizqullah — Last Mile Logistic Officer (pivot ke Data/Ops Analyst).
Tools: Python (pandas, matplotlib), Excel. Data: operasional hub Cinere, dianonimkan.
