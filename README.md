# Aplikasi Manajemen SSB Baturetno

## 📝 Kata Pengantar & Latar Belakang

Pendidikan olahraga sejak usia dini merupakan pilar penting dalam pembentukan karakter, kedisiplinan, dan sportivitas generasi muda. Sekolah Sepak Bola (SSB) Baturetno telah berkomitmen penuh selama bertahun-tahun dalam membina talenta-talenta muda di bidang sepak bola. Namun, seiring dengan bertambahnya jumlah siswa didik dan kompleksitas kurikulum kepelatihan, manajemen pencatatan data administrasi, kurikulum latihan, serta penilaian performa fisik dan teknik siswa yang masih bersifat manual sering kali menghadapi tantangan efisiensi dan transparansi data.

Untuk menjawab tantangan tersebut, **Ashvin Labs** bekerja sama dengan **SSB Baturetno** merancang dan membangun sistem aplikasi manajemen terintegrasi berbasis web. Aplikasi ini dirancang tidak hanya untuk menyederhanakan tugas administrasi internal staf dan mempermudah pelatih dalam menginput penilaian perkembangan murid secara dinamis, tetapi juga untuk menyediakan akses informasi perkembangan anak secara real-time bagi orang tua siswa dengan cara yang aman dan interaktif tanpa kerumitan proses login.

---

## 📌 Status Proyek: Tahap Perencanaan (Planning Phase)
Saat ini proyek berada dalam **Tahap Perencanaan Teknis & Analisis Kebutuhan**. Seluruh dokumen spesifikasi arsitektur, basis data, diagram alur sistem, dan rancangan antarmuka (wireframe) telah dirumuskan secara matang sebelum memasuki fase implementasi kode program.

---

## 🚀 Tumpukan Teknologi (Tech Stack)

Aplikasi ini dibangun menggunakan tumpukan teknologi modern berkinerja tinggi:
* **Framework Utama:** [Next.js](https://nextjs.org/) (React + TypeScript)
* **Styling & UI:** [Tailwind CSS](https://tailwindcss.com/) & [shadcn/ui](https://ui.shadcn.com/)
* **Database:** [PostgreSQL](https://www.postgresql.org/) (diinang pada [Supabase](https://supabase.com/))
* **ORM:** [Prisma ORM](https://www.prisma.io/)
* **Visualisasi Grafik:** [Recharts](https://recharts.org/) / [Chart.js](https://www.chartjs.org/)
* **Sistem Email:** [Resend API](https://resend.com/)
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

---

## ⚖️ Hak Cipta & Lisensi

**Intellectual Property of Ashvin Labs Indonesia**  
*Copyright © 2026 Ashvin Labs. All Rights Reserved.*  
Seluruh rancangan, kode sumber, dan dokumentasi ini merupakan properti intelektual milik Ashvin Labs Indonesia dan hanya ditujukan untuk penggunaan resmi SSB Baturetno. Penggandaan, distribusi, atau pemakaian di luar ketentuan kontrak kerja sama tanpa izin tertulis dari Ashvin Labs adalah dilarang.
