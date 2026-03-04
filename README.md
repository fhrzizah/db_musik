# 🎵 Database Musik

Proyek ini berisi latihan database menggunakan **MariaDB**. Fokus utama dari latihan ini adalah mengimplementasikan hubungan antar tabel (*Foreign Key*) dan mempraktikkan berbagai tipe **JOIN** untuk menggabungkan data.

## 📊 Struktur Database

Database ini bernama `db_musik` dan terdiri dari dua tabel utama yang saling berelasi:

### 1. Tabel `tb_artis`
Digunakan untuk menyimpan data musisi atau band.
- `id_artis`: Primary Key (Auto Increment).
- `nama_artis`: Nama dari musisi tersebut.

### 2. Tabel `tb_lagu`
Digunakan untuk menyimpan daftar lagu yang terhubung ke artis tertentu.
- `id_lagu`: Primary Key (Auto Increment).
- `judul_lagu`: Judul lagu.
- `id_artis`: **Foreign Key** yang merujuk pada `tb_artis(id_artis)`.

---

## 🚀 Implementasi Query

### 1. Membuat Database & Tabel
```sql
CREATE DATABASE db_musik; 
USE db_musik; 

CREATE TABLE tb_artis(
    id_artis INT PRIMARY KEY AUTO_INCREMENT,
    nama_artis VARCHAR(50)
);

CREATE TABLE tb_lagu(
    id_lagu INT PRIMARY KEY AUTO_INCREMENT,
    judul_lagu VARCHAR(100),
    id_artis INT,
    FOREIGN KEY (id_artis) REFERENCES tb_artis(id_artis)
);
