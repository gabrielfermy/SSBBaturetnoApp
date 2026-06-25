# Roadmap, Timeframe, dan Estimasi Biaya
## Proyek Pengembangan Aplikasi SSB Baturetno oleh Ashvin Labs

Dokumen ini menyajikan rencana kerja (roadmap), lini masa (timeframe), serta estimasi biaya pengembangan dan operasional untuk aplikasi manajemen Sekolah Sepak Bola (SSB) Baturetno.

---

## 1. Roadmap & Timeframe (Lini Masa Kerja)

Pengembangan aplikasi ini direncanakan berlangsung selama **10 Minggu** (sekitar 2,5 bulan), terbagi ke dalam 6 Milestone utama:
### Bagan Timeline Proyek (10 Minggu)

```mermaid
gantt
    title Lini Masa Pengerjaan Proyek (10 Minggu)
    dateFormat  YYYY-MM-DD
    axisFormat  W%W
    
    section Milestone 1
    M1: Analisis & Wireframe (W1) : active, m1, 2026-06-01, 2026-06-08
    
    section Milestone 2
    M2: Setup DB & Auth (W2-W3) : active, m2, 2026-06-08, 2026-06-22
    
    section Milestone 3
    M3: Siswa & Kurikulum (W4-W5) : active, m3, 2026-06-22, 2026-07-06
    
    section Milestone 4
    M4: Nilai & Portal Ortu (W6-W7) : active, m4, 2026-07-06, 2026-07-20
    
    section Milestone 5
    M5: Web Publik & CMS (W8-W9) : active, m5, 2026-07-20, 2026-08-03
    
    section Milestone 6
    M6: QA, Deploy & Training (W10) : active, m6, 2026-08-03, 2026-08-10
```


### Tabel Rangkuman Lini Masa (Timeframe Summary)

| Milestone | Durasi (Waktu) | Deskripsi Tahapan Pengembangan |
| :--- | :--- | :--- |
| **Milestone 1** | Minggu 1 | Analisis kebutuhan sistem & persetujuan desain wireframe awal. |
| **Milestone 2** | Minggu 2 - 3 | Inisialisasi Next.js, database Supabase, dan alur aktivasi email staf. |
| **Milestone 3** | Minggu 4 - 5 | Pengembangan modul pengelolaan data murid (KU 9, 10, 12, 15) & kurikulum. |
| **Milestone 4** | Minggu 6 - 7 | Modul penilaian guru & gerbang masuk verifikasi rapor orang tua. |
| **Milestone 5** | Minggu 8 - 9 | Halaman depan publik (Homepage, Blog/Berita) & CMS pengelola konten. |
| **Milestone 6** | Minggu 10 | Pengujian menyeluruh (QA), peluncuran produksi (Vercel), & pelatihan staf. |

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

## 2. Rincian Anggaran Biaya - Opsi A: Skema Kemitraan (Friend-to-Friend / Pro Bono)

Opsi ini ditujukan khusus sebagai skema kemitraan bersahabat dengan menggunakan spesifikasi server standar (*Free/Hobby Tier*) serta pemotongan jasa pengembangan oleh Ashvin Labs guna menambah portofolio:

### A. Anggaran Tahun Pertama (Opsi Kemitraan)
| Komponen Anggaran | Penjelasan Item | Estimasi Biaya (IDR) |
| :--- | :--- | :--- |
| **Jasa Pengembangan Aplikasi** | Biaya subsidi pengembangan UI/UX, Next.js, Postgres Database, integrasi Resend Email, Rapor PDF & Ekspor Excel | Rp 9.500.000 |
| **Biaya Operasional & Infrastruktur (Tahun 1)** | Pembelian Domain resmi (.com/.id), sewa database cloud & web hosting standar | Rp 2.000.000 |
| **Total Anggaran Tahun Pertama (Opsi A)** | **Pengembangan Sistem + Operasional Tahun Pertama** | **Rp 11.500.000** |

### B. Anggaran Tahun Kedua & Seterusnya (Opsi Kemitraan)
*   **Total Anggaran Tahunan (Mulai Tahun ke-2):** **Rp 2.000.000 / tahun**  
    *(Hanya mencakup perpanjangan sewa domain, sewa server web, dan kuota email standard/free tier - minus biaya pengembangan)*

---

## 3. Rincian Anggaran Biaya - Opsi B: Skema Standar Enterprise (Harga Pasar Normal)

Opsi ini mencerminkan estimasi harga pasar normal untuk pengerjaan skala industri komersial profesional dengan alokasi infrastruktur server performa tinggi (*Pro Tier* dengan dukungan *backup* otomatis harian dan keamanan tingkat tinggi):

### A. Anggaran Tahun Pertama (Opsi Enterprise)
| Komponen Anggaran | Penjelasan Item | Estimasi Biaya (IDR) |
| :--- | :--- | :--- |
| **Jasa Pengembangan Aplikasi** | Jasa pembuatan sistem profesional penuh oleh Ashvin Labs (UI/UX, Backend, DB integration, QA, Training, Deployment) | Rp 35.000.000 |
| **Biaya Operasional & Infrastruktur (Tahun 1)** | Pembelian Domain resmi, sewa database cloud PostgreSQL Pro Tier (Supabase Pro) & cloud hosting performa tinggi (Vercel Pro) | Rp 8.890.000 |
| **Total Anggaran Tahun Pertama (Opsi B)** | **Pengembangan Sistem + Operasional Pro Tier & Domain** | **Rp 43.890.000** |

### B. Anggaran Tahun Kedua & Seterusnya (Opsi Enterprise)
*   **Total Anggaran Tahunan (Mulai Tahun ke-2):** **Rp 8.890.000 / tahun**  
    *(Mencakup biaya sewa tahunan Supabase Pro Tier, Vercel Pro Tier, perpanjangan nama domain kustom, serta pemeliharaan sistem berkala)*

---

## 4. Ketentuan Pembayaran (Term of Payment)

Untuk menjamin kelancaran pengerjaan proyek, sistem pembayaran dibagi menjadi **2 Termin (50% / 50%)**:
1.  **Termin 1 (DP 50%):** Pembayaran uang muka (down payment) sebesar 50% setelah persetujuan rencana kerja & penandatanganan kesepakatan pengerjaan (Milestone 1).
2.  **Termin 2 (Pelunasan 50%):** Pembayaran akhir sebesar 50% setelah sistem selesai diuji, didemonstrasikan, dideploy ke server produksi (Vercel & Supabase), serta serah terima sistem secara penuh (Milestone 6).
