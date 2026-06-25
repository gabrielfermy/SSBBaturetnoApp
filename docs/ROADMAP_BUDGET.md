# Roadmap, Timeframe, dan Estimasi Biaya
## Proyek Pengembangan Aplikasi SSB Baturetno oleh Ashvin Labs

Dokumen ini menyajikan rencana kerja (roadmap), lini masa (timeframe), serta estimasi biaya pengembangan dan operasional untuk aplikasi manajemen Sekolah Sepak Bola (SSB) Baturetno.

---

## 1. Roadmap & Timeframe (Lini Masa Kerja)

Pengembangan aplikasi ini direncanakan berlangsung selama **10 Minggu** (sekitar 2,5 bulan), terbagi ke dalam 6 Milestone utama:

*(Catatan: Tanggal di bawah adalah tanggal fiktif untuk mensimulasikan visualisasi timeline mingguan di mana 7 hari = 1 minggu)*

```mermaid
gantt
    title Timeline Proyek (10 Minggu)
    dateFormat  YYYY-MM-DD
    axisFormat  Minggu %W
    section Fase Desain
    Milestone 1 (Week 1) :active, m1, 2026-01-05, 7d
    section Fase Inti
    Milestone 2 (Week 2-3) : m2, 2026-01-12, 14d
    Milestone 3 (Week 4-5) : m3, 2026-01-26, 14d
    Milestone 4 (Week 6-7) : m4, 2026-02-09, 14d
    section Fase Integrasi & CMS
    Milestone 5 (Week 8-9) : m5, 2026-02-23, 14d
    section Fase QA & Rilis
    Milestone 6 (Week 10) : m6, 2026-03-09, 7d
```

### Rincian Milestone:

*   **Milestone 1: Analisis Kebutuhan & Finalisasi Wireframe (Minggu 1)**
    *   Penyelarasan dokumentasi TRD, skema database, dan wireframe halaman.
    *   Persetujuan desain antarmuka dasar.
*   **Milestone 2: Inisialisasi Proyek, Database, & User Management (Minggu 2 - 3)**
    *   Setup Next.js, Prisma, dan Supabase PostgreSQL.
    *   Pembuatan fitur undangan staf lewat email (Resend API) dan aktivasi password.
*   **Milestone 3: Pengelolaan Data Murid & Kurikulum (Minggu 4 - 5)**
    *   Pembuatan modul CRUD murid (KU-9, 10, 12, 15) dan generator nomor NIS otomatis.
    *   Pembuatan modul kurikulum per kelompok umur.
*   **Milestone 4: Input Nilai & Verifikasi Rapor Orang Tua (Minggu 6 - 7)**
    *   Antarmuka input nilai dinamis untuk guru/pelatih.
    *   Pengembangan alur verifikasi rapor orang tua 2-langkah (Nama/Email/NIS + Tanggal Lahir).
*   **Milestone 5: Web Publik (Homepage, Blog) & Ekspor PDF/Excel (Minggu 8 - 9)**
    *   Halaman depan publik (Homepage, About, Contact) dan sistem manajemen berita (CMS).
    *   Implementasi unduhan rapor PDF terproteksi sandi dan ekspor data ke file Excel.
*   **Milestone 6: Pengujian (QA), Deployment, & Serah Terima (Minggu 10)**
    *   Pengujian menyeluruh (keamanan token, ekspor laporan, integrasi email).
    *   Deployment final ke Vercel dan penyambungan domain kustom.
    *   Pelatihan (training) penggunaan sistem untuk staf SSB Baturetno.

## 2. Rincian Anggaran Biaya Tahun Pertama (First Year Budget)

Anggaran tahun pertama mencakup biaya pengembangan aplikasi oleh **Ashvin Labs** digabungkan dengan biaya sewa infrastruktur cloud dasar dan domain untuk 12 bulan pertama:

| Komponen Anggaran | Penjelasan Item | Estimasi Biaya (IDR) |
| :--- | :--- | :--- |
| **Jasa Pengembangan Aplikasi** | Pengembangan UI/UX, Next.js, Database Postgres, integrasi Resend Email, Rapor PDF & Ekspor Excel | Rp 9.500.000 |
| **Biaya Operasional & Infrastruktur (Tahun 1)** | Pembelian Domain resmi (.com/.id), kuota email sistem, sewa database cloud & web hosting | Rp 2.000.000 |
| **Total Anggaran Tahun Pertama** | **Pengembangan Sistem + Operasional & Domain Tahun Pertama** | **Rp 11.500.000** |

---

## 3. Rincian Anggaran Biaya Tahun Kedua & Seterusnya (Maintenance & Operational Only)

Mulai tahun kedua, biaya pengembangan ditiadakan (minus pengembangan). Anggaran hanya digunakan untuk perpanjangan domain dan kebutuhan sewa server/database agar sistem terus berjalan:

| Komponen Anggaran | Penjelasan Item | Estimasi Biaya Per Tahun (IDR) |
| :--- | :--- | :--- |
| **Biaya Operasional & Infrastruktur (Tahunan)** | Perpanjangan hak nama domain resmi, sewa database cloud, hosting Next.js, dan kuota email sistem | Rp 2.000.000 |
| **Total Anggaran Tahunan (Mulai Tahun ke-2)** | **Biaya Perpanjangan Operasional & Domain** | **Rp 2.000.000 / tahun** |

## 4. Ketentuan Pembayaran (Term of Payment) - Rekomendasi
Untuk menjamin kelancaran pengerjaan proyek:
1.  **Term 1 (DP 30%):** Pembayaran awal setelah persetujuan rencana kerja (Milestone 1).
2.  **Term 2 (Progress 40%):** Pembayaran setelah Milestone 3 selesai (Manajemen Murid, Staf, & Kurikulum aktif).
3.  **Term 3 (Pelunasan 30%):** Pembayaran akhir setelah sistem selesai diuji, dideploy ke server produksi, dan diserahterimakan (Milestone 6).
