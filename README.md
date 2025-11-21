# MODUL-PRAKTIKUM-BASIS-DATA-bagian-1-dan-2
Modul ini disusun untuk membantu mahasiswa memahami perancangan & implementasi basis data relasional mulai dari tahap konseptual (ERD) hingga fisik (SQL & tabel).
Setiap bab berisi penjelasan teori, petunjuk praktikum, dan contoh-contoh implementasi nyata.

---

#  **BAB 1 – REVIEW KONVERSI ENTITY RELATIONSHIP (ER) DIAGRAM KE SKEMA RELASI 



---

## **1. Deskripsi Singkat**

Bab ini menjelaskan bagaimana *Entity Relationship Diagram (ERD)* dikonversi menjadi *Skema Relasi* yang siap diimplementasikan pada DBMS seperti MySQL.
Materi ini adalah dasar paling penting dalam perancangan database relasional.

---

## **2. Komponen Dasar ERD**

**Entitas** → objek dunia nyata, menjadi tabel
**Atribut** → ciri entitas, menjadi kolom
**Atribut Komposit** → dipecah menjadi beberapa kolom
**Atribut Multivalue** → menjadi tabel baru
**Atribut Derived** → opsional untuk disimpan
**Entitas Lemah** → bergantung pada entitas kuat
**Relasi** → hubungan antar entitas
**Kardinalitas** → 1:1, 1:N, N:M

---

## **3. Aturan Konversi ERD → Skema Relasi**

### **🔷 1. Entitas Kuat → Tabel**

* Nama entitas = nama tabel
* Atribut = kolom
* Primary key tetap sebagai PK

### **🔷 2. Atribut Komposit**

* Dipecah menjadi kolom sederhana
  (misal: alamat → jalan, kota, provinsi)

### **🔷 3. Atribut Multivalue**

* Menjadi tabel baru
* PK entitas utama menjadi FK

### **🔷 4. Atribut Derived**

* Opsional disimpan (misal: umur)

### **🔷 5. Entitas Lemah**

* Tetap menjadi tabel
* Menggunakan PK dari entitas kuat sebagai FK
* PK biasanya gabungan

### **🔷 6. Relasi 1 : 1**

* FK diletakkan pada salah satu tabel (yang dependennya lebih kuat)

### **🔷 7. Relasi 1 : N**

* FK diletakkan pada tabel sisi **N**
  (“yang sedikit masuk ke yang banyak”)

### **🔷 8. Relasi 1 : N + Atribut Relasi**

* Jika relasi punya atribut → jadi tabel baru

### **🔷 9. Relasi N : M**

* Selalu menjadi 3 tabel:

  * Tabel A
  * Tabel B
  * Tabel Relasi (berisi 2 FK + atribut relasi)

### **🔷 10. Relasi Unary (Self-Join)**

* 1:N → tabel yang sama menambahkan FK
* N:M → tabel relasi baru

### **🔷 11. Relasi Ternary (3 Entitas)**

* Tidak boleh dipecah biner
* Menjadi tabel relasi yang berisi 3 FK

### **🔷 12. Generalisasi–Spesialisasi**

**Metode 1:** superclass + subclass sebagai tabel terpisah
**Metode 2:** superclass dilebur ke subclass

### **🔷 13. Agregasi**

* Relasi tingkat tinggi → tabel relasi berisi tiga atau lebih FK

---

## **4. Studi Kasus: Sistem Apotek**

ERD sistem apotek dalam modul dikonversi menjadi 13 tabel, contoh:

* **PASIEN**
* **PASIEN_BPJS**
* **PASIEN_NON_BPJS**
* **RESEP**
* **DETAIL_OBAT**
* **OBAT**
* **PEGAWAI**
* **PEMBAYARAN**
* **RETUR**
* **KATEGORI_OBAT**
* dll.

Setiap tabel mengandung PK, FK, dan atribut sesuai aturan konversi.

---

## **5. Kesimpulan**

Konversi ERD ke skema relasi adalah proses penting dalam desain database.
Aturan-aturan seperti konversi entitas kuat, entitas lemah, atribut multivalue, serta relasi 1:1, 1:N, dan N:M wajib dipahami agar menghasilkan database yang valid, konsisten, dan bebas anomali.

---

Berikut **ringkasan lengkap BAB 2** dari file *MODUL PRAKTIKUM BASIS DATA*, sudah disederhanakan dan diformat rapi agar bisa langsung kamu **copy–paste ke README GitHub**-mu.

(Sumber isi diambil dari bagian **“BAB II : REVIEW BAHASA SQL”** pada file modul) 

---

# 📘 **BAB 2 – PENGANTAR BASIS DATA-DDL

Bab ini membahas ulang dasar-dasar **SQL (Structured Query Language)** sebagai bahasa standar untuk mengelola dan mengakses data pada sistem basis data relasional. Materi di dalamnya berfokus pada *DDL*, *DML*, *DCL*, serta penggunaan constraint untuk menjaga integritas data.

---

 ## 🟦 **1. Pengertian SQL**

SQL adalah bahasa yang digunakan untuk:

* Membuat struktur database dan tabel
* Menambah, mengubah, menghapus data
* Mengambil data berdasarkan kriteria tertentu
* Mengatur hak akses dan keamanan database

---

# 🟦 **2. Kategori Perintah SQL**

## **🔹 A. Data Definition Language (DDL)**

Digunakan untuk membuat dan mengubah struktur database.

Perintah:

* `CREATE DATABASE` – membuat database
* `CREATE TABLE` – membuat tabel
* `ALTER TABLE` – mengubah struktur tabel
* `DROP TABLE` – menghapus tabel
* `DROP DATABASE` – menghapus database

---

## **🔹 B. Data Manipulation Language (DML)**

Digunakan untuk memanipulasi isi data.

Perintah:

* `INSERT` – menambahkan data
* `UPDATE` – mengubah data
* `DELETE` – menghapus data
* `SELECT` – mengambil data

---

## **🔹 C. Data Control Language (DCL)**

Mengatur hak akses user terhadap database.

Perintah:

* `GRANT` – memberi hak akses
* `REVOKE` – mencabut hak akses

---

# 🟦 **3. Struktur Dasar Tabel & Constraint**

Bab ini menjelaskan berbagai jenis **constraint** untuk menjaga integritas data dalam tabel.

### **1. PRIMARY KEY**

* Identitas unik setiap baris
* Tidak boleh NULL

### **2. FOREIGN KEY**

* Menghubungkan tabel satu dengan lainnya
* Menjamin relasi antar tabel tetap konsisten

### **3. UNIQUE**

* Data tidak boleh duplikat

### **4. NOT NULL**

* Kolom wajib memiliki nilai

### **5. DEFAULT**

* Menyediakan nilai otomatis jika tidak diisi

### **6. CHECK**

* Membatasi nilai tertentu (misal umur > 0)

---

# 🟦 **4. Contoh DDL & DML Dasar**

### **CREATE TABLE**

```sql
CREATE TABLE Mahasiswa (
    nim CHAR(8) PRIMARY KEY,
    nama VARCHAR(50) NOT NULL,
    alamat VARCHAR(100),
    prodi VARCHAR(30)
);
```

### **INSERT**

```sql
INSERT INTO Mahasiswa VALUES ('12345678', 'Budi', 'Jakarta', 'Informatika');
```

### **SELECT**

```sql
SELECT nim, nama FROM Mahasiswa;
```

### **UPDATE**

```sql
UPDATE Mahasiswa SET alamat = 'Bandung' WHERE nim = '12345678';
```

### **DELETE**

```sql
DELETE FROM Mahasiswa WHERE nim = '12345678';
```

---

# 🟦 **5. Kesimpulan BAB 2**

BAB ini memperkenalkan ulang pondasi SQL yang harus dikuasai sebelum mengerjakan praktikum berikutnya, seperti pembuatan tabel fisik, manipulasi data, join, transaksi, dan implementasi relasi dari ERD.

Mahasiswa diharapkan memahami:

* Cara membuat struktur database
* Cara membuat dan memodifikasi tabel
* Cara memasukkan, membaca, mengubah, dan menghapus data
* Cara menggunakan constraint untuk integritas data
* Dasar pengelolaan hak akses

---



