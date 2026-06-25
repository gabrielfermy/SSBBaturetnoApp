# Technology Stack Specification - Aplikasi SSB Baturetno

Dokumen ini menjelaskan tumpukan teknologi (tech stack) yang dipilih untuk membangun aplikasi manajemen SSB Baturetno, beserta alasan pemilihan dan arsitektur pengembangannya.

---

## 1. Lapisan Inti (Core Stack)

| Komponen | Teknologi | Deskripsi / Alasan Pemilihan |
| :--- | :--- | :--- |
| **Framework Utama** | **Next.js (React & TypeScript)** | Menyediakan fitur Server-Side Rendering (SSR)/App Router untuk performa tinggi dan integrasi API Routes/Server Actions yang mudah. |
| **Bahasa Pemrograman** | **TypeScript** | Menjamin tipe data yang aman (type safety) untuk mengurangi potensi bug saat pengembangan. |
| **Database** | **Supabase (PostgreSQL)** | Layanan Database Relasional berbasis Cloud (Postgres) yang sangat andal, menyediakan pooling koneksi bawaan, dan mudah diintegrasikan. |
| **Hosting & Deployment**| **Vercel** | Platform cloud optimal untuk Next.js dengan fitur CI/CD otomatis dari repositori Git. |
| **Domain & DNS** | **Cloudflare / Registrar Lain**| Untuk manajemen domain kustom dan perlindungan keamanan tambahan. |

---

## 2. Lapisan Antarmuka (Frontend & UI/UX)

* **CSS Framework:** **Tailwind CSS**
  * Memungkinkan pembuatan desain UI modern dengan cepat melalui kelas utilitas yang fleksibel dan terstandarisasi.
* **Pustaka Komponen UI:** **shadcn/ui** (Radix UI + Tailwind CSS)
  * Kumpulan komponen UI premium yang sepenuhnya dapat disesuaikan (customizable) dan beraksen modern tanpa membebani ukuran bundle aplikasi.
* **Desain Estetika:** HSL tailored colors, Dark Mode toggle, Glassmorphism effects, dan micro-animations.
* **Tipografi:** Google Fonts (**Outfit** atau **Inter**).
* **Grafik Perkembangan Performa:** **Recharts** atau **Chart.js** (berbasis Canvas/SVG) untuk menyajikan visualisasi grafik radar (radar chart) dan garis (line chart) perkembangan penilaian murid.
* **Pustaka Ikon:** **Lucide React** (ikon modern dan minimalis).

---

## 3. Integrasi & Layanan Pihak Ketiga (Third-Party Services)

* **Pengiriman Email Undangan:**
  * **Nodemailer** (backend library).
  * Layanan SMTP gratis/berbayar (seperti **Resend**, **SendGrid**, atau **Mailtrap** untuk lingkungan pengujian/sandbox).
* **Pembuatan PDF & Excel (Rapor & Data Siswa):**
  * **html2pdf.js** atau **jsPDF** untuk konversi instan halaman rapor web menjadi dokumen PDF berkualitas tinggi siap unduh di sisi pengguna.
  * **exceljs** atau **xlsx (SheetJS)** di backend/frontend untuk melakukan ekspor data tabel rekap siswa dan nilai ke file Excel (.xlsx).
* **Autentikasi & Keamanan:**
  * Hashing password menggunakan **bcryptjs**.
  * Manajemen sesi pengguna menggunakan **JWT (JSON Web Token)** secara aman melalui HTTP-only cookies.
