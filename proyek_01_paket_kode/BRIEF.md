# BRIEF — Dashboard Performa Kurir (tren 1–8 Okt 2026)

## Tujuan dashboard
Monitoring harian performa 55 kurir (12 Dedicated, 43 Mitra) hub Cinere:
volume, delivery rate, dan failed — per tanggal, zona, dan driver.
Data: snapshot 8 Okt 2026 siang, 36.832 paket, 358 baris (tanggal x driver),
sudah dianonimkan (Driver_ID). File: `data/hourly_trend_01_08okt_anonim.csv`
kolom: ofd_date, Driver_ID, Zone, Tipe, total, delivered, ongoing, failed.

## Struktur Excel yang diminta (dashboard interaktif)
1. **Sheet "Dashboard"**: judul + tanggal update; dropdown pilih tanggal
   (data validation dari daftar 1–8 Okt); KPI cards pakai rumus
   (Total Paket, Delivered, Ongoing, Failed, Delivery Rate %) yang merespons
   dropdown; tabel ranking zona; chart volume harian; chart rate per zona.
2. **Sheet "Data"**: 358 baris dataset (paste dari CSV), header difreeze.
3. **Sheet "Ringkasan Driver"**: tabel per Driver_ID (total 8 hari, rate)
   pakai rumus dari sheet Data; conditional formatting merah untuk rate <90%.

## Angka kunci (terverifikasi, untuk KPI default = 8 hari)
- Total paket 36.832; delivered 34.173; ongoing 2.616; failed 43
- Volume harian: 1 Okt 4.501 | 2 Okt 4.857 | 3 Okt 4.251 | 4 Okt 4.322 |
  5 Okt 3.369 (Minggu, terendah) | 6 Okt 5.464 (Senin, tertinggi) |
  7 Okt 5.336 | 8 Okt 4.732 (data s/d siang — ongoing masih jalan)
- Delivery rate zona (1–7 Okt, hari selesai): terendah Pangkalan Jati Baru
  90,9% ... tertinggi CINERE 93,7%. Selisih hanya 2,8 poin — performa merata.
- Driver (min 200 paket, 1–7 Okt): terendah DRV_25 86,8% (400 paket);
  tertinggi 3 driver 100% (DRV_45 654 paket, DRV_49, DRV_57).
- Failed 43 semuanya di 8 Okt (hari berjalan) — wajar, paket hari
  sebelumnya sudah teresolusi.

## Insight untuk narasi dashboard
- Pola mingguan jelas: Minggu drop (3.369), Senin spike (5.464) — implikasi
  staffing & armada.
- Gap zona kecil (2,8 poin) = SOP merata; fokus coaching ke driver
  individual di bawah 90%, bukan ke zona.
- 8 Okt ongoing 2.616 paket = angka yang dimonitor real-time sore ini.

## Chart referensi (folder ini)
- chart_01_volume.png, chart_02_zona.png, chart_03_driver.png

## Atribusi
Wima Rizqullah — Last Mile Logistic Officer. Tools: Python (pandas),
Excel (SUMIFS, data validation, conditional formatting).
