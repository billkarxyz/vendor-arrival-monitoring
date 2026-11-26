# Vendor Arrival Monitoring

Dashboard monitoring kedatangan vendor di receiving dock gudang — versi statis (satu file `index.html`, tanpa build step, tanpa backend, tanpa dependensi).

Tampilan mengikuti screenshot TWIS Receiving: papan biru **VENDOR ARRIVAL MONITORING** dengan jam live WIB, strip statistik, dan tabel jadwal kedatangan vendor.

## Cara membuka

- Buka file `index.html` langsung di browser, atau
- Aktifkan GitHub Pages: Settings → Pages → Branch `main`, folder `/ (root)`.

## Fitur

- **Jam live WIB** (Asia/Jakarta) beserta tanggal berbahasa Indonesia.
- **Strip statistik** Remaining / Delayed Plan / Overdue Arrival / On Schedule — klik salah satu untuk memfilter tabel berdasarkan status.
- **Tabel kedatangan**: No, Plan Time, Vendor Name, Truck Station, Rit, Plant, Arriv. Time, Item Received, Status Arrival.
- **Status dihitung live** dari plan time vs jam tiba:
  - `ON SCHEDULE` (hijau) — tiba sebelum/sesuai akhir plan time.
  - `DELAYED` (merah) — tiba setelah plan time, atau plan time sudah lewat < 60 menit tanpa kedatangan.
  - `OVERDUE` (kuning) — plan time sudah lewat ≥ 60 menit tanpa kedatangan, atau tanggal sudah lewat.
  - `SCHEDULED` (biru) — jadwal masih dalam/menunggu plan time.
- **Tambah / edit / hapus jadwal** lewat form (tanggal, plan time, vendor, truck station, rit, plant, jam tiba, item received).
- **Check-in kedatangan**: satu klik mencatat jam tiba otomatis (WIB).
- **Item Received**: klik kolomnya untuk mengisi/mengubah jumlah item langsung di tabel.
- **Filter**: tanggal, plant, status, dan pencarian nama vendor.
- **Data tersimpan di localStorage** (bertahan setelah reload). Tombol **Muat Data Contoh** (10 vendor dari screenshot, plant Karawang 1) dan **Hapus Semua Data**.

## Data contoh

10 vendor dari screenshot referensi (tanggal hari ini saat pertama dibuka):

| Plan Time | Vendor | Station |
|---|---|---|
| 07:50–08:20 | KANSAI PAINT INDONESIA | TS 01-01 |
| 07:50–08:20 | ROVI | TS 01-02 |
| 08:00–09:00 | SADIKUN NIAGAMAS RAYA | TS 01-03 |
| 08:05–08:35 | KANSAI PAINT INDONESIA | TS 01-09 |
| 08:15–08:45 | KANSAI PAINT INDONESIA | TS 01-07 |
| 08:30–09:00 | IWATANI INDUSTRI GAS | TS 01-06 |
| 08:30–09:00 | EXIS COLLECTION KERAJINAN | TS 01-01 |
| 08:30–09:00 | BERKAH | TS 01-02 |
| 09:00–09:30 | PT MURNI CAHAYA PRATAMA | TS 01-09 |
| 09:20–09:50 | NIPSEA PAINT AND CHEMICALS | TS 01-09 |

Dua vendor pertama sudah terisi jam tiba (07:45 dan 07:51) seperti pada screenshot.
