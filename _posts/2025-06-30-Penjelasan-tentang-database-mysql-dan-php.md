---
layout: post
title: "HTML link dan list"
---

### Penjelasan tentang database mysql dan PHP.

<img src="/assets/images/php dan mysql.png" alt="Visual Studio Code" width="500" height="400">

## MySQL
MySQL adalah sistem manajemen basis data relasional (RDBMS) yang menggunakan bahasa SQL (Structured Query Language). MySQL digunakan untuk menyimpan, mengelola, dan mengambil data secara efisien. MySQL sangat populer dalam pengembangan aplikasi web karena gratis (open source), ringan, dan cepat.


## PHP
PHP (Hypertext Preprocessor) adalah bahasa pemrograman sisi server yang dirancang khusus untuk pengembangan web. PHP dapat digunakan untuk menghubungkan aplikasi web dengan database, seperti MySQL.

---

**Hubungan antara PHP dan MySQL**
PHP digunakan untuk mengakses dan memanipulasi data dalam MySQL. Contohnya:

- Menyimpan data dari formulir HTML ke database
- Menampilkan data dari database ke halaman web
- Memperbarui atau menghapus data dalam database

### Proses Umum PHP Mengakses MySQL
1. Koneksi ke Database
2. Menjalankan Query SQL
3. Mengambil atau memproses hasil
4. Menutup koneksi


## Contoh Kerja PHP dan Mysql
### 1. Membuat Koneksi ke database
<?php
$host = "localhost";
$user = "root";
$password = "";
$database = "bengkel";

$conn = mysqli_connect($host, $user, $password, $database);

if (!$conn) {
    die("Koneksi gagal: " . mysqli_connect_error());
}
echo "Koneksi berhasil!";
?>

### 2. Menjalankan Query Select
<?php
$query = "SELECT * FROM pelanggan";
$result = mysqli_query($conn, $query);

// Menampilkan data
while ($row = mysqli_fetch_assoc($result)) {
    echo "Nama: " . $row['nama'] . "<br>";
}
?>


### 3. Query Insert (Menambah Data)
<?php
$nama = "Andi";
$alamat = "Jakarta";
$sql = "INSERT INTO pelanggan (nama, alamat) VALUES ('$nama', '$alamat')";

if (mysqli_query($conn, $sql)) {
    echo "Data berhasil ditambahkan!";
} else {
    echo "Error: " . mysqli_error($conn);
}
?>

### 4. Menutup Koneksi
<?php
mysqli_close($conn);
?>

### Tips Penggunaan
- Gunakan prepared statements (mysqli atau PDO) untuk mencegah SQL Injection.

- Pastikan database dan tabel sudah dibuat sebelum digunakan dalam PHP.

- Selalu cek hasil koneksi dan hasil query untuk menangani error dengan baik.

### Tools Pendukung 
- XAMPP/Laragon: Paket instalasi PHP, MySQL, dan Apache untuk lokal development.

- phpMyAdmin: Antarmuka web untuk mengelola MySQL.

- VS Code: Editor kode yang umum digunakan untuk PHP + MySQL development.

---