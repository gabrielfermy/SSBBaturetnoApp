# API Specification - Aplikasi SSB Baturetno

Dokumen ini mendeskripsikan spesifikasi REST API yang digunakan untuk komunikasi antara antarmuka web (Frontend) dan server data (Backend). Semua request dan response menggunakan format **JSON**.

---

## 1. Autentikasi & Manajemen User

### A. Undang User Baru
* **Endpoint:** `POST /api/users/invite`
* **Headers:** `Authorization: Bearer <token>` (Khusus Super Admin)
* **Request Body:**
```json
{
  "email": "coach.budi@gmail.com",
  "role": "guru"
}
```
* **Response (201 Created):**
```json
{
  "message": "Undangan berhasil dikirim ke email.",
  "invitation_token": "abcde12345token"
}
```

### B. Aktivasi Akun (Set Password)
* **Endpoint:** `POST /api/users/activate`
* **Request Body:**
```json
{
  "token": "abcde12345token",
  "password": "SecurePassword123"
}
```
* **Response (200 OK):**
```json
{
  "message": "Akun berhasil diaktifkan. Silakan login."
}
```

### C. Login Pengguna
* **Endpoint:** `POST /api/auth/login`
* **Request Body:**
```json
{
  "email": "coach.budi@gmail.com",
  "password": "SecurePassword123"
}
```
* **Response (200 OK):**
```json
{
  "token": "jwt-token-string",
  "user": {
    "id": "user-uuid",
    "email": "coach.budi@gmail.com",
    "role": "guru"
  }
}
```

---

## 2. Manajemen Siswa

### A. Tambah Siswa Baru
* **Endpoint:** `POST /api/students`
* **Headers:** `Authorization: Bearer <token>` (Super Admin / Admin)
* **Request Body:**
```json
{
  "student_number": "NIS-2026-001",
  "name": "Bambang Pamungkas",
  "date_of_birth": "2015-05-15",
  "height": 135,
  "weight": 35,
  "preferred_position": "Striker",
  "back_number": 20,
  "address": "Baturetno, Banguntapan, Bantul",
  "parent_contact": "081234567890",
  "parent_email": "ortu.bambang@gmail.com",
  "category_umur": "KU-12"
}
```
* **Response (201 Created):**
```json
{
  "message": "Siswa berhasil ditambahkan.",
  "student": {
    "id": "student-uuid",
    "student_number": "NIS-2026-001",
    "name": "Bambang Pamungkas",
    "category_umur": "KU-12"
  }
}
```

### B. Verifikasi Rapor Step 1
* **Endpoint:** `POST /api/public/rapor/verify-step1`
* **Request Body:**
```json
{
  "identifier": "NIS-2026-001" 
}
```
*(Catatan: `identifier` bisa berupa Nama Lengkap, Email Orang Tua, atau Nomor Pelajar / NIS)*
* **Response (200 OK):**
```json
{
  "success": true,
  "message": "Data siswa ditemukan. Silakan masukkan tanggal lahir.",
  "temp_session_token": "temp-token-string"
}
```

### C. Verifikasi Rapor Step 2 & Dapatkan Data Rapor
* **Endpoint:** `POST /api/public/rapor/verify-step2`
* **Request Body:**
```json
{
  "temp_session_token": "temp-token-string",
  "date_of_birth": "2015-05-15"
}
```
* **Response (200 OK):**
```json
{
  "success": true,
  "access_token": "rapor-access-jwt-token",
  "student": {
    "id": "student-uuid",
    "student_number": "NIS-2026-001",
    "name": "Bambang Pamungkas",
    "category_umur": "KU-12",
    "back_number": 20
  },
  "grades_history": [
    {
      "assessment_date": "2026-06-01",
      "scores": {
        "Dribbling": 85,
        "Passing": 80,
        "Speed": 75,
        "Stamina": 80
      },
      "notes": "Peningkatan yang sangat baik pada passing."
    }
  ]
}
```

### D. Download PDF Rapor Terkunci Sandi
* **Endpoint:** `GET /api/public/rapor/download-pdf`
* **Headers:** `Authorization: Bearer <rapor-access-jwt-token>`
* **Response:** File stream PDF. File PDF ini dienkripsi/dikunci secara otomatis dengan sandi berupa tanggal lahir siswa bersangkutan (format: `DDMMYYYY`, e.g. `15052015`).

---

## 3. Parameter Penilaian (Dinamis)

### A. Mendapatkan Semua Parameter
* **Endpoint:** `GET /api/parameters`
* **Response (200 OK):**
```json
[
  {
    "id": "param-uuid-1",
    "name": "Passing",
    "category": "technical",
    "description": "Kemampuan mengoper bola dengan akurasi tinggi"
  }
]
```

### B. Membuat/Mengubah Parameter
* **Endpoint:** `POST /api/parameters` (Atau `PUT /api/parameters/:id`)
* **Headers:** `Authorization: Bearer <token>`
* **Request Body:**
```json
{
  "name": "Agility",
  "category": "physical",
  "description": "Kelincahan dalam mengubah arah lari"
}
```
* **Response (201 Created):**
```json
{
  "message": "Parameter berhasil disimpan.",
  "parameter": {
    "id": "param-uuid-2",
    "name": "Agility",
    "category": "physical"
  }
}
```

---

## 4. Penilaian & Rapor

### A. Simpan/Update Nilai Siswa
* **Endpoint:** `POST /api/grades`
* **Headers:** `Authorization: Bearer <token>` (Admin / Guru)
* **Request Body:**
```json
{
  "student_id": "student-uuid",
  "assessment_date": "2026-06-25",
  "notes": "Bagus dalam latihan fisik minggu ini.",
  "scores": [
    {
      "parameter_id": "param-uuid-1",
      "score": 85
    },
    {
      "parameter_id": "param-uuid-2",
      "score": 90
    }
  ]
}
```
* **Response (200 OK):**
```json
{
  "message": "Nilai berhasil disimpan."
}
```
