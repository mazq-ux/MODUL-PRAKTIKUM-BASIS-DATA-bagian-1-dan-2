



# **Modul Praktikum Basis Data**

Dokumentasi dan Notebook Praktikum

Repositori ini berisi rangkuman materi dan notebook praktikum yang digunakan untuk memahami konsep fundamental dalam perancangan dan implementasi basis data relasional. Materi mencakup analisis Entity Relationship Diagram (ERD), konversi menjadi skema relasi, serta implementasi SQL mulai dari dasar hingga implementasi struktur tabel menggunakan DDL.

Dokumentasi ini disusun agar dapat digunakan sebagai referensi pembelajaran mandiri maupun pendamping praktikum di kelas.

---

## **Tujuan Pembelajaran**

* Memahami konsep dasar model data konseptual menggunakan ERD.
* Mengidentifikasi entitas, atribut, relasi, serta struktur kunci.
* Mengetahui aturan formal konversi ERD menjadi skema relasi.
* Mengimplementasikan skema relasi ke dalam tabel fisik menggunakan SQL.
* Menggunakan SQL untuk manipulasi data dan pembuatan laporan sederhana.
* Menghubungkan desain konseptual, desain logis, dan implementasi fisik basis data.

---

## **Daftar Pertemuan Praktikum**

| Pertemuan       | Modul Praktikum     | Deskripsi                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Pertemuan 1** |https://colab.research.google.com/drive/1Zh_tDravzGNwio69R6k4GStO5u_rA5zy| Materi pada pertemuan ini mengulas **BAB 1**, yaitu proses lengkap konversi ERD ke skema relasi. Pembahasan meliputi entitas, jenis atribut, domain, primary key, foreign key, weak entity, relationship, cardinality (1:1, 1:N, N:M), relasi unary, ternary, serta generalisasi–spesialisasi. Studi kasus sistem apotek digunakan untuk menghasilkan 13 tabel relasi sesuai aturan formal konversi. |
| **Pertemuan 2** | https://colab.research.google.com/drive/106fyKxybt6ZWIs3-rCgtsUnAT3GlHv3Q | Materi **BAB 2** membahas implementasi basis data menggunakan SQL. Topik meliputi DDL (CREATE, ALTER, DROP) dan DML (INSERT, UPDATE, DELETE). Juga dibahas query SELECT dengan WHERE, LIKE, BETWEEN, ORDER BY, fungsi agregasi, GROUP BY, HAVING, serta JOIN. Studi kasus apotek digunakan untuk implementasi tabel fisik dan constraint.                                                            |
| **Pertemuan 3** | https://colab.research.google.com/drive/1qAZhjcKzd4gvq0g0M_P8YPgCKHoLmA7u | Materi **BAB 3** berfokus pada Data Definition Language (DDL). Pembahasan mencakup pembuatan database, implementasi tabel menggunakan CREATE TABLE, tipe data, constraint (PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK, DEFAULT, AUTO_INCREMENT), relasi antar tabel, penggunaan ALTER TABLE, serta penghapusan tabel menggunakan DROP dan TRUNCATE.                                           |

---

# **Ringkasan Materi**

## **BAB 1 — Konversi ERD ke Skema Relasi**

Materi BAB 1 menjelaskan konsep dasar pemodelan basis data menggunakan ERD sebelum diubah ke dalam bentuk relasi. Pembahasan meliputi:

* Definisi entitas, atribut, domain.
* Jenis atribut: simple, composite, multivalued, derived.
* Penjelasan primary key, foreign key, karakteristik, dan perannya dalam integritas data.
* Relationship serta cardinality (1:1, 1:N, N:M).
* Weak entity dan aturan pembentukan key.
* Aturan formal konversi ERD ke skema relasi:

  * Entitas → tabel
  * Relasi 1:N → FK di sisi N
  * Relasi 1:1 → FK pada salah satu entitas
  * Relasi N:M → tabel baru
  * Unary relationship → self-reference FK atau tabel baru
  * Ternary relationship → tabel baru dengan 3 FK
* Generalisasi dan spesialisasi.
* Studi kasus sistem apotek menghasilkan 13 tabel relasi sesuai proses konversi.

---

## **BAB 2 — Bahasa SQL Dasar (DDL & DML)**

BAB 2 membahas implementasi skema relasi menggunakan SQL sebagai dasar manipulasi dan akses data:

* Pembuatan database menggunakan CREATE DATABASE.
* Pembuatan dan modifikasi tabel menggunakan CREATE TABLE dan ALTER TABLE.
* Penghapusan tabel menggunakan DROP TABLE dan TRUNCATE.
* Pengelolaan data menggunakan INSERT, UPDATE, DELETE.
* Query SELECT dengan filter WHERE dan operator logika.
* LIKE dan pola pencarian.
* Sorting menggunakan ORDER BY.
* Fungsi agregasi (COUNT, SUM, AVG, MAX, MIN).
* GROUP BY dan HAVING.
* JOIN antar tabel (INNER, LEFT, RIGHT JOIN).
* Studi kasus sistem apotek digunakan untuk implementasi constraint seperti PK, FK, UNIQUE, CHECK, dan DEFAULT.

---

## **BAB 3 — Data Definition Language (DDL)**

BAB 3 membahas bagaimana struktur fisik database dibangun sesuai skema relasi:

* Penggunaan dasar DDL:

  * CREATE
  * ALTER
  * DROP
  * TRUNCATE
* Pembuatan database dan pemilihan aktif dengan USE.
* Pembuatan tabel sesuai skema relasi menggunakan CREATE TABLE.
* Pemilihan tipe data yang tepat (INT, CHAR, VARCHAR, DATE, DECIMAL, dll.).
* Implementasi constraint untuk integritas data:

  * PRIMARY KEY
  * FOREIGN KEY
  * UNIQUE
  * NOT NULL
  * DEFAULT
  * CHECK
  * AUTO_INCREMENT
* Penerapan relasi antar tabel menggunakan foreign key sesuai konversi ERD.
* Modifikasi struktur tabel menggunakan ALTER TABLE.
* Penghapusan tabel menggunakan DROP TABLE dan pengosongan data menggunakan TRUNCATE TABLE.
* Studi kasus apotek digunakan untuk membuat struktur tabel lengkap yang saling berelasi.

---

## **Penutup**

Repository ini merupakan dokumentasi yang terus berkembang seiring bertambahnya materi pada setiap bab berikutnya. Hingga saat ini mencakup BAB 1 (konversi ERD), BAB 2 (SQL dasar), dan BAB 3 (DDL untuk pembangunan tabel fisik). Materi lanjutan seperti normalisasi, SQL tingkat lanjut, indexing, view, trigger, hingga optimasi query akan ditambahkan pada bab selanjutnya.

Struktur dokumentasi akan tetap konsisten agar mudah dipahami meskipun konten terus bertambah. Jika di kemudian hari terdapat revisi atau tambahan materi, repository ini akan diperbarui secara bertahap.

Repository ini terbuka untuk pengembangan lebih lanjut. Jika terdapat saran, pertanyaan, atau permintaan penambahan materi, silakan membuka *issue* atau *pull request*. Dokumentasi selanjutnya akan dilanjutkan pada BAB-BAB berikutnya.

---


Cukup bilang **"lanjutkan"**.
