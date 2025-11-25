# Pert3_RPL - Sistem Manajemen Data Mahasiswa

Program Java berbasis MVC (Model-View-Controller) untuk mengelola data mahasiswa dengan database MySQL.

## 📋 Deskripsi Proyek

Aplikasi ini merupakan sistem CRUD (Create, Read, Update, Delete) untuk mengelola data mahasiswa. Program menggunakan arsitektur MVC untuk memisahkan logika bisnis, presentasi, dan akses data.

## 🏗️ Arsitektur Proyek

Proyek menggunakan pola **MVC (Model-View-Controller)**:

### Struktur Direktori
```
src/main/java/com/mycompany/pert3_4ia01_51422399/
├── model/
│   ├── ModelMahasiswa.java      # Model data mahasiswa
│   └── MahasiswaDAO.java        # Data Access Object (CRUD operations)
├── controller/
│   └── MahasiswaController.java # Logika kontrol aplikasi
├── view/
│   └── MahasiswaView.java       # Antarmuka pengguna (UI)
└── Pert3_4IA01_51422399.java   # Main class
```

## 📦 Komponen Aplikasi

### 1. **Model (ModelMahasiswa)**
- Menyimpan data mahasiswa dengan atribut:
  - `id`: ID unik mahasiswa
  - `npm`: Nomor Pokok Mahasiswa
  - `nama`: Nama lengkap mahasiswa
  - `semester`: Semester mahasiswa
  - `ipk`: Indeks Prestasi Kumulatif

### 2. **DAO (MahasiswaDAO)**
- Menangani operasi database MySQL
- Fitur utama:
  - `checkConnection()`: Verifikasi koneksi database
  - `addMahasiswa()`: Menambah data mahasiswa baru
  - `updateMahasiswa()`: Mengubah data mahasiswa
  - `deleteMahasiswa()`: Menghapus data mahasiswa
  - `getAllMahasiswa()`: Mengambil semua data mahasiswa

### 3. **Controller (MahasiswaController)**
- Menghubungkan View dan Model
- Menampilkan data ke pengguna
- Memproses perintah dari user

### 4. **View (MahasiswaView)**
- Antarmuka pengguna berbasis console
- Menampilkan menu operasi CRUD

## 🛠️ Teknologi & Dependencies

- **Java**: JDK 25
- **Build Tool**: Apache Maven
- **Database**: MySQL
- **JDBC Driver**: MySQL Connector Java 8.0.33

### Dependencies (pom.xml)
```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.33</version>
</dependency>
```

## ⚙️ Setup & Instalasi

### Prerequisites
- Java Development Kit (JDK) 25+
- Apache Maven
- MySQL Server
- Git

### Langkah Instalasi

1. **Clone Repository**
```bash
git clone https://github.com/rayinailham/Pert3_RPL.git
cd Pert3_RPL
```

2. **Buat Database MySQL**
```sql
CREATE DATABASE database_pert3_4ia01;

USE database_pert3_4ia01;

CREATE TABLE mahasiswa (
    id INT AUTO_INCREMENT PRIMARY KEY,
    npm VARCHAR(20) NOT NULL,
    nama VARCHAR(100) NOT NULL,
    semester INT NOT NULL,
    ipk FLOAT NOT NULL
);
```

3. **Konfigurasi Koneksi Database**
Edit file `MahasiswaDAO.java`:
```java
connection = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/database_pert3_4ia01", 
    "root",  // username
    ""       // password
);
```

4. **Build Project**
```bash
mvn clean compile
```

5. **Jalankan Aplikasi**
```bash
mvn exec:java@Pert3_4IA01_51422399
```

atau

```bash
mvn package
java -cp target/pert3_4IA01_51422399-1.0-SNAPSHOT.jar com.mycompany.pert3_4ia01_51422399.Pert3_4IA01_51422399
```

## 📝 Fitur Utama

### CRUD Operations
- ✅ **Create**: Tambah data mahasiswa baru
- ✅ **Read**: Tampilkan semua data mahasiswa
- ✅ **Update**: Ubah data mahasiswa yang ada
- ✅ **Delete**: Hapus data mahasiswa

### Fitur Tambahan
- Verifikasi koneksi database
- Validasi input data
- Tampilan data terformat dengan rapi
- Error handling untuk koneksi database

## 🎯 Cara Penggunaan

1. Jalankan program
2. Pilih menu operasi:
   - Lihat semua mahasiswa
   - Tambah mahasiswa baru
   - Update data mahasiswa
   - Hapus data mahasiswa
   - Cek koneksi database
   - Keluar

3. Ikuti instruksi yang ditampilkan di layar

## 📊 Contoh Output

```
===========================
ID          : 1
NPM         : 51422399
NAMA        : Rayi Na Ilham
SEMESTER    : 4
IPK         : 3.75
===========================
```

## 🐛 Troubleshooting

### Masalah Koneksi Database
- Pastikan MySQL server berjalan
- Periksa konfigurasi koneksi di `MahasiswaDAO.java`
- Verifikasi username dan password

### Masalah Build Maven
```bash
mvn clean install
mvn compile
```

### Driver JDBC Tidak Ditemukan
- Pastikan MySQL Connector Java sudah di-download
- Run `mvn dependency:resolve`

## 📝 Lisensi

Proyek ini merupakan tugas perkuliahan dan bebas digunakan untuk tujuan pendidikan.

## 👨‍💻 Penulis

- **Nama**: Rayi Na Ilham
- **NIM**: 51422399
- **Kelas**: 4IA01

## 📧 Kontak

Untuk pertanyaan atau saran, silakan hubungi atau buat issue di repository ini.

---

**Last Updated**: November 2025
