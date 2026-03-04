# 🎵 Database Manajemen Musik (SQL Join Practice)

Proyek ini berisi dokumentasi latihan manipulasi database relasional menggunakan **MariaDB**. Fokus utama dari latihan ini adalah mengimplementasikan hubungan antar tabel (*Foreign Key*) dan mempraktikkan berbagai tipe **JOIN** untuk menggabungkan data.

## 📊 Struktur Database

[cite_start]Database ini bernama `db_musik` [cite: 1] dan terdiri dari dua tabel utama yang saling berelasi:

### 1. Tabel `tb_artis`
Digunakan untuk menyimpan data musisi atau band.
- [cite_start]`id_artis`: Primary Key (Auto Increment)[cite: 3].
- [cite_start]`nama_artis`: Nama dari musisi tersebut[cite: 3].

### 2. Tabel `tb_lagu`
Digunakan untuk menyimpan daftar lagu yang terhubung ke artis tertentu.
- [cite_start]`id_lagu`: Primary Key (Auto Increment)[cite: 4].
- [cite_start]`judul_lagu`: Judul lagu[cite: 4].
- [cite_start]`id_artis`: **Foreign Key** yang merujuk pada `tb_artis(id_artis)`[cite: 4].

---

## 🚀 Implementasi Query

### 1. Membuat Database & Tabel
```sql
CREATE DATABASE db_musik; [cite: 1]
USE db_musik; [cite: 2]

CREATE TABLE tb_artis(
    id_artis INT PRIMARY KEY AUTO_INCREMENT,
    nama_artis VARCHAR(50)
); [cite: 3]

CREATE TABLE tb_lagu(
    id_lagu INT PRIMARY KEY AUTO_INCREMENT,
    judul_lagu VARCHAR(100),
    id_artis INT,
    FOREIGN KEY (id_artis) REFERENCES tb_artis(id_artis)
); [cite: 4]
