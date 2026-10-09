# Metode Anonimisasi

Data di folder `data/` aman untuk repo publik GitHub. Cara kerja:

1. **Nomor resi (AWB)** → `PKG-XXXXXX`, hasil SHA-1 dari (AWB + salt rahasia),
   diambil 6 karakter heksadesimal. Deterministik: AWB yang sama di file
   berbeda menghasilkan ID yang sama (berguna untuk analisis lintas file).
2. **Nama kurir** → `DRV_01` … `DRV_58`, pemetaan satu-satu konsisten di semua
   file. File pemetaan asli (`private/mapping_driver.txt`) dan salt
   (`private/salt.txt`) **tidak ikut di-push** — lihat `.gitignore`.
3. **Kolom yang dibuang** dari report: alamat pickup, koordinat, POD link,
   nomor invoice marketplace, Driver Code, Transaction_ID / Route_ID, dan
   kolom identitas lain. Yang dipertahankan hanya kolom analitis (waktu,
   status, zona, COD, seller).
4. Akun admin ikut dimask (`DRV_XX`) seperti kurir lain — tidak ada nama asli
   di data publik.

## Verifikasi (8 Okt 2026)

- Jumlah baris anonim = jumlah baris asli: 18.888 (report), 593 / 30 / 161
  (boman 10 Agus / 8 Sept / 5 Okt).
- Total COD per file anonim = total asli: Rp80.302.609 / Rp4.254.525 /
  Rp21.833.151 (selisih 0).
- Pencarian 200 nomor resi asli + 20 nama kurir asli di semua file anonim:
  **0 temuan**.
- Statistik agregat (per zona) dari data anonim identik dengan laporan
  operasional hari yang sama.

## Batasan yang jujur

Hash bersifat obfuscation, bukan enkripsi — format nomor resi bisa ditebak
secara brute force oleh pihak yang berniat. Karena itu repo ini hanya memuat
agregat dan ID anonim, tanpa nama perusahaan/kurir/penerima asli. Cukup untuk
portofolio publik.
