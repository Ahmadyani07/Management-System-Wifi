# Management System Wifi

Aplikasi manajemen sistem Wifi berbasis Laravel.

## Sistem Requirement

- PHP 8.2
- MySQL
- XAMPP (Apache + MySQL)

## Fitur Utama

- Login Multi User
- Dashboard
- Data Klien
- Paket Internet
- Data Admin
- Data Tagihan
- Rekapitulasi
- Logout
- dan lainnya

## Panduan Instalasi

1. Download dan install XAMPP dan Composer di komputer.
2. Ekstrak folder project ke dalam `htdocs`.
3. Aktifkan Apache dan MySQL pada XAMPP.
4. Buka `http://localhost/phpmyadmin`.
5. Buat database baru dengan nama `internet`.
6. Import file database aplikasi ke dalam database `internet`.
7. Buka terminal di folder project dan jalankan:

```bash
composer install
cp .env.example .env
php artisan key:generate
```

8. Perbarui konfigurasi database di file `.env`:

```env
DB_DATABASE=internet
DB_USERNAME=root
DB_PASSWORD=
```

9. Jalankan migrasi:

```bash
php artisan migrate
```

10. Jalankan aplikasi:

```bash
php artisan serve
```

11. Buka browser dan akses `http://127.0.0.1:8000`.

## Default Login

- Email: `admin@mail.com`
- Password: `secret`

## Catatan

- Pastikan folder `storage` dan `bootstrap/cache` dapat ditulis.
- Jangan sertakan file `.env` ke dalam repository.
- Jika belum ada dependensi, jalankan `composer install`.

## Deploy ke Railway

1. Buat project baru di Railway dan hubungkan dengan repository GitHub Anda.
2. Tambahkan service MySQL di Railway untuk database.
3. Di Railway, atur environment variables untuk Laravel:

```env
APP_ENV=production
APP_DEBUG=false
APP_URL=https://<railway-app-url>
DB_CONNECTION=mysql
DB_HOST=<railway-mysql-host>
DB_PORT=<railway-mysql-port>
DB_DATABASE=<railway-database>
DB_USERNAME=<railway-username>
DB_PASSWORD=<railway-password>
```

4. Railway akan menjalankan `composer install` secara otomatis. Jika command start perlu ditentukan, gunakan `Procfile` berikut:

```text
web: php artisan serve --host=0.0.0.0 --port=${PORT}
```

5. Jika aplikasi tidak bisa terhubung ke database, cek kembali konfigurasi MySQL dan pastikan service Railsnya sudah aktif.

6. Untuk preview, akses URL Railway yang diberikan setelah deployment selesai.