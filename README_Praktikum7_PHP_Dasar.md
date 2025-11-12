
# 🧩 Praktikum 7 - PHP Dasar

**Nama:** Andreas Ferdinand Parapat  
**NIM:** 312410383  
**Kelas:** TI.24.A3  
**Mata Kuliah:** Pemrograman Web  

---

## 🎯 Tujuan Praktikum
1. Memahami konsep dasar *Server Side Scripting (PHP)*  
2. Memahami dasar pemrograman PHP  
3. Memahami penggunaan variabel dan tipe data  
4. Menerapkan struktur kondisi dan perulangan  
5. Membuat program PHP sederhana  

---

## ⚙️ Persiapan Lingkungan
- Install **XAMPP**  
- Jalankan **Apache** dan **MySQL** dari XAMPP Control Panel  
- Buat folder:
  ```
  C:\xampp\htdocs\lab7_php_dasar
  ```

---

## 🧠 Langkah-langkah Praktikum

### 1️⃣ PHP Dasar
File: `php_dasar.php`
```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
```

**Output:**
```
Hello World
```

---

### 2️⃣ Variabel PHP
```php
<?php
$nim = "312410383";
$nama = "Andreas Ferdinand Parapat";
echo "NIM: $nim<br>";
echo "Nama: $nama";
?>
```

**Output:**
```
NIM: 312410383
Nama: Andreas Ferdinand Parapat
```

---

### 3️⃣ Form Input
```php
<!DOCTYPE html>
<html>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama:</label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>

<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

**Output:**
```
Selamat Datang Andreas
```

---

### 4️⃣ Struktur Kondisi
```php
<?php
$hari = date("l");
if ($hari == "Sunday") {
    echo "Minggu";
} elseif ($hari == "Monday") {
    echo "Senin";
} else {
    echo "Hari lainnya";
}
?>
```

---

### 5️⃣ Perulangan For & While
```php
<?php
for ($i=1; $i<=5; $i++) {
    echo "Perulangan ke-$i<br>";
}
?>
```

**Output:**
```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

---

## 🧾 6️⃣ Tugas Akhir – Program PHP Sederhana

File: `tugas_php.php`
```php
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Tugas PHP Dasar</title>
</head>
<body>
    <h2>Form Input Data</h2>
    <form method="post" action="">
        <label>Nama:</label><br>
        <input type="text" name="nama" required><br><br>

        <label>Tanggal Lahir:</label><br>
        <input type="date" name="tgl_lahir" required><br><br>

        <label>Pekerjaan:</label><br>
        <select name="pekerjaan" required>
            <option value="">-- Pilih Pekerjaan --</option>
            <option value="Programmer">Programmer</option>
            <option value="Desainer">Desainer</option>
            <option value="Guru">Guru</option>
            <option value="Dokter">Dokter</option>
            <option value="Mahasiswa">Mahasiswa</option>
        </select><br><br>

        <input type="submit" value="Kirim">
    </form>

    <hr>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = $_POST['nama'];
        $tgl_lahir = $_POST['tgl_lahir'];
        $pekerjaan = $_POST['pekerjaan'];

        // Hitung umur
        $tgl_lahir_obj = new DateTime($tgl_lahir);
        $hari_ini = new DateTime();
        $umur = $hari_ini->diff($tgl_lahir_obj)->y;

        // Gaji berdasarkan pekerjaan
        switch ($pekerjaan) {
            case "Programmer": $gaji = 10000000; break;
            case "Desainer": $gaji = 8000000; break;
            case "Guru": $gaji = 6000000; break;
            case "Dokter": $gaji = 15000000; break;
            case "Mahasiswa": $gaji = 0; break;
            default: $gaji = 0; break;
        }

        echo "<h3>Hasil Data:</h3>";
        echo "Nama: $nama<br>";
        echo "Tanggal Lahir: $tgl_lahir<br>";
        echo "Umur: $umur tahun<br>";
        echo "Pekerjaan: $pekerjaan<br>";
        echo "Gaji: Rp " . number_format($gaji, 0, ',', '.');
    }
    ?>
</body>
</html>
```

**Output:**
```
Nama: Andreas Ferdinand Parapat
Tanggal Lahir: 2003-04-15
Umur: 22 tahun
Pekerjaan: Programmer
Gaji: Rp 10.000.000
```

---

## 🗂️ Struktur Folder
```
C:\xampp\htdocs\lab7_php_dasar\
│
├── php_dasar.php
├── latihan2.php
├── tugas_php.php
└── README.md
```

---

## 📤 Cara Upload ke GitHub
1. Buat repository baru bernama **Lab7Web**  
2. Masuk ke folder project:
   ```bash
   cd C:\xampp\htdocs\lab7_php_dasar
   ```
3. Jalankan perintah:
   ```bash
   git init
   git add .
   git commit -m "Praktikum 7 - PHP Dasar"
   git branch -M main
   git remote add origin https://github.com/username/Lab7Web.git
   git push -u origin main
   ```
4. Upload selesai ✅
