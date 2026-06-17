# 📚 Sistem Perpustakaan

Sistem Perpustakaan adalah aplikasi berbasis web yang dibuat menggunakan **Django** dan **PostgreSQL** untuk memenuhi tugas akhir implementasi CRUD (Create, Read, Update, Delete). Aplikasi ini digunakan untuk mengelola data buku, data siswa, dan transaksi peminjaman buku.

## 🎯 Tujuan Proyek

Proyek ini dibuat untuk mempelajari dan mengimplementasikan:

* Framework Django.
* Database PostgreSQL.
* Operasi CRUD (Create, Read, Update, Delete).
* Relasi database menggunakan Foreign Key.
* Konsep Many-to-Many melalui tabel penghubung (Pivot Table).
* Penggunaan Raw SQL (`connection.cursor()`) pada Django.
* Pembuatan antarmuka web menggunakan Django Template.

---

## ✨ Fitur Aplikasi

### 📖 Manajemen Buku

* Menampilkan daftar buku.
* Menambahkan data buku.
* Melihat detail buku.
* Mengubah data buku.
* Menghapus data buku.

### 👨‍🎓 Manajemen Siswa

* Menampilkan daftar siswa.
* Menambahkan data siswa.
* Melihat detail siswa.
* Mengubah data siswa.
* Menghapus data siswa.
* Menampilkan status siswa (Aktif / Tidak Aktif).

### 📋 Manajemen Peminjaman

* Menampilkan daftar peminjaman buku.
* Menambahkan transaksi peminjaman.
* Menghubungkan data siswa dan buku menggunakan Foreign Key.
* Mengubah status peminjaman menjadi **Dikembalikan**.
* Menampilkan informasi tanggal pinjam dan jatuh tempo.

### 📊 Dashboard

* Total data buku.
* Total data siswa.
* Total transaksi peminjaman.
* Jumlah buku yang sedang dipinjam.
* Jumlah buku yang sudah dikembalikan.

---

## 🗄️ Struktur Database

Aplikasi ini menggunakan tiga tabel utama:

### 1. Buku

| Field        | Tipe Data   |
| ------------ | ----------- |
| id           | Serial (PK) |
| judul        | Varchar     |
| pengarang    | Varchar     |
| kategori     | Varchar     |
| penerbit     | Varchar     |
| tahun_terbit | Integer     |
| rak          | Varchar     |
| stok         | Integer     |
| deskripsi    | Text        |

### 2. Siswa

| Field     | Tipe Data        |
| --------- | ---------------- |
| id        | Serial (PK)      |
| nama      | Varchar          |
| kelas     | Varchar          |
| nis       | Varchar (Unique) |
| is_active | Boolean          |

### 3. Peminjaman

| Field          | Tipe Data    |
| -------------- | ------------ |
| id             | Serial (PK)  |
| siswa_id       | Integer (FK) |
| buku_id        | Integer (FK) |
| tanggal_pinjam | Date         |
| jatuh_tempo    | Date         |
| keperluan      | Text         |
| status         | Varchar      |

---

## 🔗 Relasi Database

* **Satu Siswa** dapat memiliki banyak data peminjaman (**One to Many**).
* **Satu Buku** dapat dipinjam berkali-kali (**One to Many**).
* Secara konsep, relasi antara **Siswa** dan **Buku** adalah **Many to Many**, yang dihubungkan melalui tabel **Peminjaman**.

---

## 🛠️ Teknologi yang Digunakan

* Python 3
* Django
* PostgreSQL
* Raw SQL (`connection.cursor()`)
* HTML5
* Tailwind CSS
---

## 🚀 Cara Menjalankan Proyek

### 1. Clone Repository

```bash
git clone https://github.com/username/sistem-perpustakaan.git
cd sistem-perpustakaan
```

### 2. Buat Virtual Environment

```bash
python -m venv venv
```

### 3. Aktifkan Virtual Environment

**Windows**

```bash
venv\Scripts\activate
```

**Linux / macOS**

```bash
source venv/bin/activate
```

### 4. Install Dependency

```bash
pip install -r requirements.txt
```

### 5. Konfigurasi Database PostgreSQL

Buat database baru, kemudian sesuaikan konfigurasi pada file `settings.py`.

### 6. Jalankan Server

```bash
python manage.py runserver
```

Buka browser dan akses:

```
http://127.0.0.1:8000/
```

---

## 📂 Struktur Folder

```text
perpus/
│
├── manage.py
│
├── perpus/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── data_perpus/
│   ├── __init__.py
│   ├── views.py
│   ├── urls.py
│   ├── forms.py
│   ├── admin.py
│   ├── apps.py
│   └── migrations/
│
└── templates/
    │
    ├── base.html
    ├── dashboard.html
    │
    ├── buku/
    │   ├── list.html
    │   ├── create.html
    │   ├── detail.html
    │   ├── update.html
    │   └── delete.html
    │
    ├── siswa/
    │   ├── list.html
    │   ├── create.html
    │   ├── detail.html
    │   ├── update.html
    │   └── delete.html
    │
    └── peminjaman/
        ├── list.html
        └── create.html
```


---

## 📝 Catatan

* Aplikasi ini menggunakan **Raw SQL** melalui `connection.cursor()` dan tidak menggunakan Django ORM sesuai ketentuan tugas.
* Seluruh form memiliki validasi input.
* Data dengan pilihan tetap seperti **Kategori Buku**, **Rak Buku**, dan **Status Peminjaman** menggunakan dropdown.
* Tampilan dibuat menggunakan **Bootstrap** agar responsif dan mudah digunakan.

---

## 👨‍💻 Pengembang

**Nama:** *Farhat Syamil Pangestu*

**Proyek:** Tugas Akhir CRUD Django — Sistem Perpustakaan

**Tahun:** 2026

