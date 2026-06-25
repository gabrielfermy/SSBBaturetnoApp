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

---

## 2. Estimasi Biaya Pengembangan (One-Time Cost)

Estimasi jasa profesional pengembangan sistem oleh **Ashvin Labs** untuk cakupan kerja di atas:

| Keterangan Pekerjaan | Estimasi Biaya (IDR) |
| :--- | :--- |
| **UI/UX Design & Frontend Development** (Tailwind CSS, shadcn/ui, Responsive Layout) | Rp 3.000.000 |
| **Backend & Database Integration** (Next.js Server Actions, Supabase Postgres, Prisma ORM, Security JWT) | Rp 3.500.000 |
| **System Integrations** (Resend Email API, Generator PDF Locked, Export Excel Engine) | Rp 1.500.000 |
| **Testing, Quality Assurance (QA), & Deployment** (Setup Vercel, Hosting, DNS) | Rp 1.000.000 |
| **Training & Dokumentasi Penggunaan** (Pelatihan Staf Admin & Pelatih) | Rp 500.000 |
| **Total Estimasi Biaya Pengembangan (Skema Portfolio/Kemitraan)** | **Rp 9.500.000** |

---

## 3. Estimasi Biaya Operasional (Tahunan / Recurring Yearly Cost)

Berikut adalah perkiraan biaya operasional pihak ketiga (infrastruktur cloud) yang diperlukan untuk menjaga aplikasi tetap berjalan secara optimal di server produksi dengan standar performa tinggi (**Pro Tier**):

| Komponen Layanan | Detail Spesifikasi (Pro Tier) | Estimasi Biaya Tahunan (IDR / USD) |
| :--- | :--- | :--- |
| **Database Supabase** | PostgreSQL Pro Tier (Backup terjadwal, penyimpanan lebih besar, prioritas performa) | $300 / tahun (Sekitar Rp 4.800.000) |
| **Hosting Vercel** | Next.js Hosting Pro Tier (Kapasitas bandwidth lebih tinggi & performa produksi komersial) | $240 / tahun (Sekitar Rp 3.840.000) |
| **Resend Email Service** | Pengiriman email aktivasi & undangan (Free Tier up to 3k email/bulan - Cukup untuk operasional) | Rp 0 / tahun |
| **Domain Kustom** | Domain web resmi (.com / .id / .my.id) | Rp 150.000 - Rp 250.000 / tahun |
| **Total Estimasi Biaya Operasional** | **Infrastruktur Produksi Pro & Domain** | **Sekitar Rp 8.890.000 / tahun** |

---

## 4. Ketentuan Pembayaran (Term of Payment) - Rekomendasi
Untuk menjamin kelancaran pengerjaan proyek:
1.  **Term 1 (DP 30%):** Pembayaran awal setelah persetujuan rencana kerja (Milestone 1).
2.  **Term 2 (Progress 40%):** Pembayaran setelah Milestone 3 selesai (Manajemen Murid, Staf, & Kurikulum aktif).
3.  **Term 3 (Pelunasan 30%):** Pembayaran akhir setelah sistem selesai diuji, dideploy ke server produksi, dan diserahterimakan (Milestone 6).
