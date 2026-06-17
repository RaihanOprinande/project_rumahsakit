# Project 9 Rumah Sakit 🏥

Tugas Kuliah: **Implementasi API dan CRUD pada Aplikasi Mobile menggunakan Flutter & PHP/MySQL**

Project ini adalah aplikasi mobile berbasis Flutter yang bertujuan untuk menampilkan data Provinsi, Kabupaten, Rumah Sakit, serta detail ketersediaan Kamar secara dinamis. Aplikasi ini dirancang untuk mendemonstrasikan bagaimana aplikasi mobile (Flutter) dapat berkomunikasi dengan backend server (PHP & MySQL) melalui REST API.

## 🚀 Fitur Utama
- **Menampilkan Daftar Provinsi**: Mengambil data provinsi dari database dan menampilkannya dalam bentuk daftar.
- **Menampilkan Daftar Kabupaten**: Menampilkan data kabupaten/kota berdasarkan provinsi yang dipilih.
- **Daftar Rumah Sakit**: Menampilkan rumah sakit yang tersedia pada kabupaten terkait, lengkap dengan gambar dan lokasinya.
- **Detail Ketersediaan Kamar**: Menampilkan data *real-time* ketersediaan kamar pada rumah sakit yang dipilih.
- **Integrasi Peta (Google Maps)**: Menampilkan lokasi titik rumah sakit secara visual (membutuhkan API Key dari Google Cloud Platform).

## 🛠️ Teknologi yang Digunakan
* **Frontend**: Flutter (Dart)
* **Backend**: PHP (Native)
* **Database**: MySQL (dijalankan via Laragon/XAMPP)
* **Packages Unggulan**:
  * `http`: Untuk melakukan request API (GET/POST) ke backend.
  * `google_maps_flutter`: Untuk merender peta interaktif.
  * `permission_handler`: Untuk mengatur izin akses lokasi/storage.

## ⚙️ Persyaratan Sistem
Sebelum menjalankan project ini, pastikan Anda telah menginstal:
1. **Flutter SDK** (Versi 3.3.0 ke atas)
2. **Laragon / XAMPP** (Untuk menjalankan Apache dan MySQL)
3. **DBeaver / phpMyAdmin** (Untuk manajemen database)
4. **Google Maps API Key** (Dibutuhkan untuk menampilkan peta)

## 📋 Panduan Instalasi & Konfigurasi

### 1. Setup Database (Backend)
1. Buka aplikasi Laragon/XAMPP, lalu jalankan **Start All** (Apache & MySQL).
2. Buka DBeaver atau phpMyAdmin, buat database baru dengan nama:
   `db_rumahsakit`
3. Jalankan script SQL berikut untuk membuat tabel dan data dummy:
   *(Anda bisa mengeksekusi script SQL yang tersedia pada instruksi sebelumnya untuk membuat tabel `provinsi`, `kabupaten`, `rumahsakit`, dan `kamar`).*
4. Pastikan folder API PHP (misal: `rumahsakitDB`) berada di dalam folder `C:\laragon\www\` atau `D:\laragon\www\`.

### 2. Setup Aplikasi (Frontend Flutter)
1. Buka folder project ini di VS Code atau Android Studio.
2. Jalankan perintah berikut di terminal untuk mengunduh semua package:
   ```bash
   flutter pub get
   ```
3. Sesuaikan alamat IP pada source code Flutter. Buka file-file di folder `lib/screen_page/` dan ubah `192.168.100.13` menjadi alamat IP IPv4 laptop Anda (cek menggunakan `ipconfig` di CMD).

### 3. Konfigurasi Google Maps API Key
Agar fitur peta tidak *crash* dan tampil dengan benar:
1. Buat project di [Google Cloud Console](https://console.cloud.google.com/).
2. Aktifkan **Maps SDK for Android**.
3. Buat *Credentials* (API Key).
4. Buka file `android/app/src/main/AndroidManifest.xml` pada project Flutter Anda, dan tambahkan kode berikut di dalam tag `<application>` sebelum `</application>`:
   ```xml
   <meta-data android:name="com.google.android.geo.API_KEY"
              android:value="MASUKKAN_API_KEY_ANDA_DISINI"/>
   ```

### 4. Jalankan Aplikasi
Hubungkan HP Anda ke komputer (pastikan terhubung ke jaringan WiFi yang sama dengan laptop), lalu jalankan:
```bash
flutter run
```

---
*Dibuat untuk memenuhi tugas kuliah Pemrograman Mobile Lanjut.*
