# Aplikasi Manajemen SSB Baturetno

Aplikasi berbasis web modern untuk mengelola data siswa, nilai perkembangan siswa (rapor fisik & teknik), kurikulum latihan, serta portal berita/blog resmi Sekolah Sepak Bola (SSB) Baturetno.

Aplikasi ini menggunakan desain bertema premium dengan visualisasi grafik interaktif untuk memudahkan pelatih memantau perkembangan anak didik dan memberikan akses transparan bagi orang tua siswa.

---

## 🚀 Tumpukan Teknologi (Tech Stack)

Aplikasi ini dibangun menggunakan ekosistem JavaScript modern dengan performa tinggi:
* **Frontend & Backend:** [Next.js](https://nextjs.org/) (React + TypeScript)
* **Styling & UI:** [Tailwind CSS](https://tailwindcss.com/) & [shadcn/ui](https://ui.shadcn.com/)
* **Database:** [PostgreSQL](https://www.postgresql.org/) (diinang pada [Supabase](https://supabase.com/))
* **ORM:** [Prisma ORM](https://www.prisma.io/)
* **Visualisasi Grafik:** [Recharts](https://recharts.org/) / [Chart.js](https://www.chartjs.org/)
* **Hosting:** [Vercel](https://vercel.com/)

---

## 📂 Struktur Dokumentasi Proyek

Semua rencana dan analisis kebutuhan sistem didokumentasikan secara lengkap dalam folder `/docs`:
1. **[Technical Requirements Document (TRD)](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/TRD.md)** – Mendefinisikan fitur utama, peran pengguna, dan diagram alur sistem.
2. **[Database Schema Design](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/DATABASE_SCHEMA.md)** – Rancangan model database relasional dan diagram ERD.
3. **[User Flows & Sitemap](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/USER_FLOWS.md)** – Alur perjalanan pengguna dari login hingga portal rapor.
4. **[API Specification](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/API_SPECIFICATION.md)** – Penjelasan endpoint REST API beserta payload request/response.
5. **[Wireframe Layouts](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/WIREFRAMES.md)** – Panduan visual rancangan tata letak antarmuka pengguna.
6. **[Technology Stack Specification](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/TECH_STACK.md)** – Detail spesifikasi komponen platform teknologi yang digunakan.
7. **[Implementation Plan](file:///k:/Personal/SSBBaturetno/SSBBaturetnoApp/docs/IMPLEMENTATION_PLAN.md)** – Peta jalan (milestone) tahapan pengembangan aplikasi.

---

## 🛠️ Cara Mulai Pengembangan (Untuk Developer)

### 1. Prasyarat
Pastikan Anda memiliki:
* **Node.js** (versi 18.x ke atas)
* **npm** atau **yarn**

### 2. Kloning Repositori & Instalasi
```bash
git clone <url-repo-ssb-baturetno>
cd SSBBaturetnoApp
npm install
```

### 3. Konfigurasi Environment Variables
Buat file `.env` di direktori utama (root) dan masukkan kredensial Supabase PostgreSQL Anda:
```env
DATABASE_URL="postgresql://postgres:password@db.supabase.co:5432/postgres?schema=public"
JWT_SECRET="rahasia_super_aman_anda"
RESEND_API_KEY="re_your_resend_api_key_here"
```

### 4. Sinkronisasi Database (Prisma)
Jalankan migrasi database dan seed data awal:
```bash
npx prisma migrate dev --name init
npx prisma db seed
```

### 5. Menjalankan Server Pengembangan
```bash
npm run dev
```
Aplikasi dapat diakses melalui browser di alamat [http://localhost:3000](http://localhost:3000).
