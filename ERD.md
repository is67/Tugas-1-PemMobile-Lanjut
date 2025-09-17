ERD: Aplikasi Pemesanan Lapangan Olahraga
Entitas & Atribut
1. Lapangan

lapangan_id (PK)
nama_lapangan (String) – contoh: Futsal, Badminton, Voli
lokasi (String, optional)
deskripsi (String, optional)

2. Pemesanan

pemesanan_id (PK)
lapangan_id (FK → Lapangan.lapangan_id)
nama_pemesan (String)
tanggal (Date)
waktu_mulai (Time)
waktu_selesai (Time)
status (Enum: aktif, selesai, dibatalkan)

Diagram Relasi (Markdown ASCII Style)
+-----------------+             +--------------------+
|    LAPANGAN     |             |     PEMESANAN      |
+-----------------+             +--------------------+
| lapangan_id (PK)|<----------->| lapangan_id (FK)   |
| nama_lapangan   |   1   --- n | pemesanan_id (PK)  |
| lokasi          |             | nama_pemesan       |
| deskripsi       |             | tanggal            |
+-----------------+             | waktu_mulai        |
                                | waktu_selesai      |
                                | status             |
                                +--------------------+

Penjelasan Relasi

Lapangan 1 : n Pemesanan
Satu lapangan bisa punya banyak pemesanan.
Misal: Lapangan Futsal → bisa ada 10 booking di tanggal yang berbeda.