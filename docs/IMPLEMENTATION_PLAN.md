# Project Implementation Plan - Aplikasi SSB Baturetno

Dokumen ini menjelaskan tahapan implementasi teknis untuk membangun aplikasi manajemen SSB Baturetno.

---

## Tahap 1: Inisialisasi Proyek & Database
- Inisialisasi proyek Next.js dengan TypeScript, Tailwind CSS, dan shadcn/ui.
- Setup konfigurasi database PostgreSQL di **Supabase** menggunakan Prisma ORM.
- Membuat migrasi tabel: `users`, `students`, `assessment_parameters`, `grades`, dan `curriculums`.
- Implementasi script seeding untuk melengkapi parameter default (Passing, Shooting, Speed, Agility, dll) dan satu akun **Super Admin** bawaan pertama kali.

## Tahap 2: Autentikasi & Sistem Undangan Email
- Implementasi backend middleware JWT dan hashing password (bcrypt).
- Pengiriman email undangan menggunakan integrasi **Resend API**.
- Pembuatan halaman Frontend `/setup-password?token=...` untuk aktivasi akun.

## Tahap 3: Modul Administrasi (Siswa & Parameter Penilaian)
- Halaman Frontend `/dashboard/students` untuk CRUD siswa lengkap dengan pengelompokan Kategori Umur (KU-9, KU-10, KU-12, KU-15).
- Pembuatan tautan unik (UUID) otomatis untuk setiap siswa.
- Halaman Frontend `/dashboard/parameters` untuk menambah/mengedit parameter secara dinamis (khusus Admin & Super Admin).

## Tahap 4: Modul Penilaian (Rapor) & Kurikulum
- Halaman `/dashboard/grades` dengan antarmuka dinamis bagi Guru/Pelatih untuk memilih kelas KU, menampilkan daftar murid, dan memasukkan nilai.
- Modul Kurikulum: Unggah berkas/silabus latihan per kategori umur.

## Tahap 5: Portal Publik Rapor Orang Tua & Ekspor Laporan
- Halaman publik `/rapor/[secure_token]` yang memuat radar/line chart (menggunakan Recharts / Chart.js).
- Integrasi pustaka pembuat PDF (`jsPDF` / `html2pdf.js` di sisi client) agar rapor dapat diunduh orang tua dengan rapi.
- Implementasi ekspor data rekap murid dan rekap nilai dalam format Excel (.xlsx) menggunakan `exceljs` atau `xlsx` untuk Super Admin/Admin.

## Tahap 6: Portal Website Publik (Homepage, About, Contact, Blog) & CMS
- Implementasi halaman publik:
  - Homepage (Hero section, info umum, ringkasan berita terbaru).
  - About Us (Visi, misi, profil pengurus & pelatih).
  - Contact Us (Form kontak, peta lokasi, link WhatsApp).
  - Berita / Blog (Daftar postingan berita SSB Baturetno).
- Implementasi CMS di dashboard internal (Super Admin / Admin):
  - Pengelolaan konten Homepage, About, & Contact melalui tabel `settings`.
  - CRUD manajemen berita (tabel `posts`) dengan status draft/published dan editor teks kaya (Rich Text Editor).
