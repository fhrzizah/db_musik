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
```
### 2. Menginput Value
```sql
insert into tb_artis
    -> (id_artis, nama_artis) values
    -> ('', 'Dewa 19'),
    -> ('', 'Sheila On 7'),
    -> ('', 'My Chemical Romance'),
    -> ('', 'Avenged Sevenfold'),
    -> ('', 'Taylor Swift');
Query OK, 5 rows affected, 5 warnings (0.011 sec)
Records: 5  Duplicates: 0  Warnings: 5

select * from tb_artis;
+----------+---------------------+
| id_artis | nama_artis          |
+----------+---------------------+
|        1 | Dewa 19             |
|        2 | Sheila On 7         |
|        3 | My Chemical Romance |
|        4 | Avenged Sevenfold   |
|        5 | Taylor Swift        |
+----------+---------------------+
5 rows in set (0.002 sec)

insert into tb_lagu
    -> (id_lagu, judul_lagu, id_artis) values
    -> ('', 'Cinta Gila', 1),
    -> ('', 'Hari Bersamanya', 2),
    -> ('', 'This Is How I Disappear', 3),
    -> ('', 'Seize The Day', 4);
    -> ('', 'Gunslinger', 4);

Query OK, 5 rows affected, 5 warnings (0.011 sec)
Records: 5  Duplicates: 0  Warnings: 5

select * from tb_lagu;
+---------+-------------------------+----------+
| id_lagu | judul_lagu              | id_artis |
+---------+-------------------------+----------+
|       1 | Cinta Gila              |        1 |
|       2 | Hari Bersamanya         |        2 |
|       3 | This Is How I Disappear |        3 |
|       4 | Seize The Day           |        4 |
|       5 | Gunslinger              |        4 |
+---------+-------------------------+----------+
5 rows in set (0.001 sec)
```






