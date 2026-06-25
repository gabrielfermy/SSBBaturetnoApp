# User Flows & Page Map - Aplikasi SSB Baturetno

Dokumen ini mendeskripsikan peta halaman (sitemap) dan alur perjalanan pengguna (User Journey) untuk setiap peran di aplikasi SSB Baturetno.

---

## 1. Peta Halaman (Sitemap)

```
[Aplikasi SSB Baturetno]
 ├── / (Landing Page & Public Info)
 ├── /login (Masuk Staf/Admin/Guru)
 ├── /setup-password?token=[token] (Halaman Set Password dari Undangan Email)
 ├── /rapor (Portal Akses Rapor Orang Tua)
 │    ├── /rapor/verify-step2 (Langkah 2: Verifikasi Tanggal Lahir)
 │    ├── /rapor/view (Halaman Rapor Murid jika lolos verifikasi)
 │    └── /rapor/download-pdf (Ekspor PDF terproteksi sandi)
 └── /dashboard (Halaman Dasbor Internal - Butuh Login)
      ├── /dashboard/users (Kelola User - Khusus Super Admin)
      ├── /dashboard/students (Kelola Siswa - Super Admin, Admin)
      │    ├── /students/add
      │    └── /students/edit/[id]
      ├── /dashboard/parameters (Kelola Parameter Nilai - Super Admin, Admin)
      ├── /dashboard/grades (Kelola & Input Nilai - Guru, Admin, Super Admin)
      │    └── /grades/input?ku=[KU]
      └── /dashboard/curriculum (Kelola Kurikulum - Semua Peran Internal)
```

---

## 2. Alur Pengguna (User Flows)

### A. Alur Undangan Pengguna Baru (Super Admin & Penerima)
1. **Super Admin** masuk ke halaman `/dashboard/users`.
2. Super Admin mengklik tombol "Undang Pengguna Baru", lalu memasukkan email dan memilih peran (Admin / Guru).
3. Sistem membuat baris baru di tabel `users` dengan status `pending` dan menghasilkan `invitation_token`.
4. Sistem mengirimkan email ke penerima.
5. **Penerima** membuka kotak masuk emailnya, lalu mengklik tautan:
   `https://ssbbaturetno.com/setup-password?token=XYZ_TOKEN`
6. Penerima diarahkan ke halaman pembuatan password, memasukkan password baru, dan mengklik "Aktifkan Akun".
7. Akun aktif, pengguna diarahkan ke `/login`.

### B. Alur Pengelolaan Siswa (Admin)
1. **Admin** mengakses `/dashboard/students` dan mengklik "Tambah Siswa Baru".
2. Admin mengisi data diri siswa termasuk **Nomor Pelajar (NIS)**, Nama, Tanggal Lahir, Kontak Orang Tua, Email Orang Tua, dll., lalu menyimpannya.
3. Siswa baru tersimpan di database dan langsung masuk ke kategori umur (KU) yang sesuai.

### C. Alur Penilaian & Pemantauan (Guru/Pelatih)
1. **Guru** masuk ke `/dashboard/grades`.
2. Guru memilih Kategori Umur (misal: KU-12) dan memilih tanggal penilaian.
3. Sistem menampilkan daftar siswa KU-12 dan kolom input dinamis berdasarkan parameter aktif saat ini.
4. Guru mengisi skor (1-100) dan catatan singkat untuk masing-masing siswa, lalu klik "Simpan Penilaian".
5. Perubahan nilai langsung tersimpan dan siap diakses.

### D. Alur Akses Rapor (Orang Tua Siswa)
1. **Orang Tua** mengunjungi Homepage utama dan mengklik link/tombol **"Lihat Rapor"**.
2. Orang Tua diarahkan ke halaman `/rapor` (Step 1). Mereka memasukkan salah satu dari: **Nama Siswa**, **Email Orang Tua**, atau **Nomor Pelajar (NIS)**.
3. Sistem memproses pencarian:
   - Jika data ditemukan, sistem menampilkan formulir Step 2 (`/rapor/verify-step2`) untuk meminta input **Tanggal Lahir Siswa**.
   - Jika data tidak ditemukan, menampilkan pesan error "Identitas Siswa tidak ditemukan".
4. Orang Tua memasukkan **Tanggal Lahir Siswa**.
5. Sistem mencocokkan input Tanggal Lahir dengan data murid yang dicari di Step 1:
   - Jika cocok, sistem membuka sesi akses rapor dan mengarahkan ke `/rapor/view`.
   - Jika tidak cocok, menampilkan pesan error "Tanggal lahir tidak sesuai".
6. Di halaman `/rapor/view`, Orang Tua dapat melihat profil anak, grafik radar/line nilai, dan mengklik tombol **"Download PDF"**.
7. Sistem menghasilkan file PDF yang **terkunci/terproteksi sandi** (password-protected). Kata sandi untuk membuka PDF adalah tanggal lahir anak (format: `DDMMYYYY`, contoh: `15052015`).
